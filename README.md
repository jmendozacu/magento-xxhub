## 内存设置
find . -name '.htaccess' -exec sed -i '' s/756M/2048M/g {} + && \
find . -name '.htaccess' -exec sed -i '' s/768M/2048M/g {} + && \
find . -name '.user.ini' -exec sed -i '' s/756M/2048M/g {} + && \
find . -name '.user.ini' -exec sed -i '' s/768M/2048M/g {} +


## 数据备份和导入

### 新建数据库
create database magento default character set utf8mb4 collate utf8mb4_unicode_ci;

### 数据备份:
``` bin/cli mysqldump -h db -umagento -pmagento --databases magento > ./magento_backup.sql ```

### 数据导入:

``` bin/clinotty mysql -h db -u root -pmagento magento < dbdump.sql ```



## 创建管理员账号
bin/magento admin:user:create --admin-user=admin --admin-password=password123 --admin-email=jacky850618@gmail.com --admin-firstname=yang  --admin-lastname=lei

## 清理缓存
bin/magento cache:clean
bin/magento cache:flush


## 备份&恢复volume
使用工具: https://github.com/loomchild/volume-backup

### 备份
docker run -v magento-xxhub_appdata:/volume --rm loomchild/volume-backup backup - > magento-xxhub_appdata.tar.bz2
docker run -v magento-xxhub_dbdata:/volume --rm loomchild/volume-backup backup - > magento-xxhub_dbdata.tar.bz2
docker run -v magento-xxhub_sockdata:/volume --rm loomchild/volume-backup backup - > magento-xxhub_sockdata.tar.bz2

### 恢复
cat magento-xxhub_appdata.tar.bz2 | docker run -i -v magento-xxhub_appdata:/volume --rm loomchild/volume-backup restore -
cat magento-xxhub_dbdata.tar.bz2 | docker run -i -v magento-xxhub_dbdata:/volume --rm loomchild/volume-backup restore -
cat magento-xxhub_sockdata.tar.bz2 | docker run -i -v magento-xxhub_sockdata:/volume --rm loomchild/volume-backup restore -

