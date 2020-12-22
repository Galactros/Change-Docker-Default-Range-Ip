# Change-Docker-Default-Range-Ip
Steps in linux for change default range ip in docker and docker-compose

1. Stop docker service

* `service docker stop`
* `systemctl stop docker`


2. Locate or Create a file called  **daemon.json** in **/etc/docker/** directory. 

* `nano /etc/docker/daemon.json`
* `vi /etc/docker/daemon.json`
* `vim /etc/docker/daemon.json`
* `touch /etc/docker/daemon.json`

3. Put this json in the file **daemon.json**

```json
{
  "debug" : true,
  "bip": "32.11.4.1/24",
  "default-address-pools" : [
    {
      "base" : "32.23.6.1/24",
      "size" : 24
    }
  ]
}
```
Debug key is optional.

Bip key is ip for docker and default-address-pools for docker-compose.

4. Start docker service 

* `service docker start`
* `systemctl start docker`
