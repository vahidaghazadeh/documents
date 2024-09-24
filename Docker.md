## Set proxy with systemd
```shell
mkdir /etc/systemd/system/docker.service.d
```
```shell
vi /etc/systemd/system/docker.service.d/http-proxy.conf
```
```shell
cat <<EOF>> /etc/systemd/system/docker.service.d
[Service]
Environment="HTTPS_PROXY=127.0.0.1:2081"
EOF
```
```shell
systemctl daemon-reload && systemctl restart docker
```
Show docker environment
```shell
systemctl show docker --property Environment
```