# Docker-compose MING (emqx) STACK

Docker-compose para hacer un deploy del siguiente Stack
1. MQTT (EMQX)
2. InfluxDB
3. Node-RED
4. Grafana


## 1. Crear volúmenes locales

### 1.1. Node-RED

```
mkdir -p /home/ubuntu/docker/nodered/data
```
### 1.2. Grafana

```
mkdir -p /home/ubuntu/docker/grafana/var/lib/grafana
```
### 1.3. InfluxDB
Volumen para versión 2.X
```
mkdir -p /home/ubuntu/docker/influxdb/var/lib/influxdb2 && mkdir -p /home/ubuntu/docker/influxdb/etc/influxdb2
```
Volumen para versión 1.X
```
mkdir -p /home/ubuntu/docker/influxdb/var/lib/influxdb && mkdir -p /home/ubuntu/docker/influxdb/etc/influxdb
```
### 1.4. EMQX

```
mkdir -p /home/ubuntu/docker/emqx/etc && mkdir -p /home/ubuntu/docker/emqx/data && mkdir -p /home/ubuntu/docker/emqx/log
```
```
touch /home/ubuntu/docker/emqx/etc/emqx.conf
```

## 2. Docker Compose
### 2.1. Network
Revisar nombre de la network de nginx. Cambiar en `networks:npm_proxy` si es necesario
```
docker network ls
```
### 2.2. User
Revisar el número de id y grupo del usuario. Cambiar en `user` si es necesario
```
whoami
id
```