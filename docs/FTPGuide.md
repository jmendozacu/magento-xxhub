

[使用镜像](https://github.com/fauria/docker-vsftpd)

docker run -d -v /var/www:/home/vsftpd -p 20:20 -p 21:21 -p 21100-21110:21100-21110 -e FTP_USER=docker -e FTP_PASS=password -e PASV_ADDRESS=127.0.0.1 -e PASV_MIN_PORT=21100  -e PASV_ADDRESS_ENABLE=true -e PASV_MAX_PORT=21110 --name vsftpd --restart=always fauria/vsftpd

docker run -d -v /var/www:/home/vsftpd -p 20:20 -p 21:21 -p 21100-21110:21100-21110 -e FTP_USER=docker -e FTP_PASS=password -e PASV_ADDRESS=39.99.166.233 -e PASV_MIN_PORT=21100 -e PASV_ADDRESS_ENABLE=true -e PASV_MAX_PORT=21110 --name vsftpd --restart=always fauria/vsftpd


