# 数据操作指引


## 数据库导入/导出

### 新建数据库
create database magento default character set utf8mb4 collate utf8mb4_unicode_ci;

### 数据备份:
``` bin/cli mysqldump -h db -umagento -pmagento --databases magento > ./magento_backup.sql ```

### 数据导入:
``` bin/clinotty mysql -h db -u root -pmagento magento < dbdump.sql ```


## 数据卷宗(Volume)备份&恢复
### 使用工具
 [volume-backup](https://github.com/loomchild/volume-backup)
 
### 备份
docker run -v magento-xxhub_appdata:/volume --rm loomchild/volume-backup backup - > magento-xxhub_appdata.tar.bz2
docker run -v magento-xxhub_dbdata:/volume --rm loomchild/volume-backup backup - > magento-xxhub_dbdata.tar.bz2
docker run -v magento-xxhub_sockdata:/volume --rm loomchild/volume-backup backup - > magento-xxhub_sockdata.tar.bz2

### 恢复
cat magento-xxhub_appdata.tar.bz2 | docker run -i -v magento-xxhub_appdata:/volume --rm loomchild/volume-backup restore -
cat magento-xxhub_dbdata.tar.bz2 | docker run -i -v magento-xxhub_dbdata:/volume --rm loomchild/volume-backup restore -
cat magento-xxhub_sockdata.tar.bz2 | docker run -i -v magento-xxhub_sockdata:/volume --rm loomchild/volume-backup restore -
