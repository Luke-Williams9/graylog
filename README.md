# Overview

This is a mix of [graylog2 open-core](https://github.com/Graylog2/docker-compose/blob/main/open-core/docker-compose.yml) and [graylog2 docker install docs.](https://go2docs.graylog.org/5-0/downloading_and_installing_graylog/docker_installation.htm)

# Usage

```
docker compose up
```

Access graylog [here.](http://localhost:9000)



Secrets / Graylog
defult_admin_sha2.txt - the default password hash (admin) 
admin_sha2.txt - the password hash used in docker-compose.yml. A setup script can change this if need be


To generate a self signed certifacate:

openssl req -subj '/CN=myhost.local' -x509 -newkey rsa:4096 -nodes -keyout key.pem -out cert.pem -days 365



To make the admin password hash:


echo -n YourPassword | shasum -a 256



https://forums.lawrencesystems.com/t/graylog-5-docker-tutorial-commands/17611


To preserve the source IP addresses of incoming log data, disable userland-proxy in /etc/docker/daemon.json

{
    "userland-proxy": false
}

https://deavid.wordpress.com/2019/06/15/how-to-allow-docker-containers-to-see-the-source-ip-address/