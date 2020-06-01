# 服务启停

使用由Websoft9提供的 GeoServer 部署方案，可能需要用到的服务如下：

## GeoServer

```shell
sudo systemctl start geoserver-server
sudo systemctl stop geoserver-server
sudo systemctl restart geoserver-server
sudo systemctl status geoserver-server

# you can use this debug mode if GeoServer service can't run
geoserver-server console
```

### MySQL

```shell
sudo systemctl start mysql
sudo systemctl stop mysql
sudo systemctl restart mysql
sudo systemctl status mysql
```

### Redis

```shell
systemctl start redis
systemctl stop redis
systemctl restart redis
systemctl status redis
```