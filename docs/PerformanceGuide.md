# 性能设置指引


## 内存设置
find . -name '.htaccess' -exec sed -i '' s/756M/2048M/g {} + && \
find . -name '.htaccess' -exec sed -i '' s/768M/2048M/g {} + && \
find . -name '.user.ini' -exec sed -i '' s/756M/2048M/g {} + && \
find . -name '.user.ini' -exec sed -i '' s/768M/2048M/g {} +

