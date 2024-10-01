# Install Harbor With Ansible Or Command

In this repository, I am going to share with you how to install Harbor using Command and Ansible.
Harbor is one of the tools for storing project images and is considered as a Docker registry.
Its installation faces challenges that I want to remove these challenges in this repository and you can install it easily.


![image](https://github.com/user-attachments/assets/edb3313c-acf6-4894-92ea-bfa30f2b7ac2)

# Install Harbor with Command
First, you must have a Linux operating system and install these tools on it
```
apt-get update && apt install docker.io docker-compose git apt-transport-https ca-certificates curl software-properties-common
```
After this, you should download the latest version of Harbor from github and unzip it
```
wget https://github.com/goharbor/harbor/releases/download/v1.10.19-rc1/harbor-offline-installer-v1.10.19-rc1.tgz
tar zxvf harbor-offline-installer-v*.tgz
cd harbor
```

then edit harbor.yml with this changes
```
hostname: -> add your-ip or you domain
https -> block https hidden 
```

at the end run this command


```
./install.sh
```
at then end you can see this message
![image](https://github.com/user-attachments/assets/f6da6ba8-6ec8-4016-b1fa-ad62372741ac)

surprised , you can see harbor website
```
http://your-ip
or
http://your-domain
user: admin
password: Harbor12345
```

you can run on linux this command
```
docker login your-ip or your-domain
```

If you receive an insecure message or docker login fails to login successfully, give this change
```
nano /etc/docker/daemon.json
{
     "insecure-registries":["http://your-ip"]
}
systemctl restart docker
``` 
at the end test your harbor docker registry
```
docker login your-ip
docker pull httpd
docker tag httpd your-ip/test/httpd
docker push your-ip/test/httpd
```
