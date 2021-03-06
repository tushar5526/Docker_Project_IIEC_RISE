# Docker_Project_IIEC_RISE
This is a project done under IIEC RISE training by Vimal Daga, It contains a docker compose file which sets up a whole wordpress server on your computer with just one click

First Install docker

If you are using RHEL 7 

```
sudo yum remove docker docker-common docker-selinux docker-engine
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install docker-ce

```

If you are using RHEL 8, docker don't support RHEL 8 but you can still install it by bypassing a check

  Step 1 : Configure the repo file for docker, Open a terminal and type
  
  ```
    cd /etc/yum.repos.d/
    gedit docker.repo
    
  ```
  Editor will open in it type
  
  ```
  [docker]
  baseurl=https://download.docker.com/linux/centos/7/x86_64/stable/
  gpgcheck=0
  
  ```

  Step 2: Do yum install docker-ce

  ```
  yum install docker-ce
  
  ```

We have succesfully installed docker, now we insatll Docker compose in our system 

Install Docker Compose by using these commands

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

```

Do a check whether docker-compose is setup or not

``` 
docker-compose --version

```

Now we download the docker-compose.yml from the repo and place it in the /mycompose directory

```
mkdir /mycompose
cd /mycompos
ls
docker-compose.yml
```

While in the /mycompose directory type the following commads
```
docker-compose up

```

For the first time , it will take some time 
It will download the wordpress docker image, mysql docker image and create docker
After the first setup, we can launch wordpress in one second by using the docker-compose up

To start docker-compose in background

```
docker-compose up -d

```

To stop docker-compose

```
docker-compose stop

```
