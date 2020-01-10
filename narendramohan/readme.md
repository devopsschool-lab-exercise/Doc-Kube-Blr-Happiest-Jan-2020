# remove if earlier versions are available

sudo yum remove docker 

sudo yum remove docker docker-client 

sudo yum remove docker docker-client-latest 

sudo yum remove docker docker-common

sudo yum remove docker docker-latest 

sudo yum remove docker docker-latest-logrotate

sudo yum remove docker docker-logrotate 

sudo yum remove docker docker-selinux 

sudo yum remove docker docker-engine-selinux

sudo yum remove docker docker-engine


# How to install Docker Community Edition via YUM?
##Step 1 - Install required packages. yum-utils provides the yum-config-manager utility, and device-mapper-persistent-data and lvm2 are required by the devicemapper storage driver.

sudo -s

sudo yum install -y yum-utils device-mapper-persistent-data lvm2

## Step 2 - Use the following command to set up the stable repository

sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

## Step 3 - Install the latest version of Docker CE
sudo yum install –y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm

sudo yum-config-manager --enable rhui-REGION-rhel-server-extras

sudo yum install -y docker-ce

sudo yum install docker-ce

### Verify Docker Installations
docker -v


### Docker is installed but not started. The docker group is created, but no users are added to the group.

## Step 4 - Enable Docker

sudo systemctl enable docker

## Step 5 - Start Docker

sudo systemctl start docker

docker info

# commands plus 
What is Container?
        APP X
        Platform app run X
        Image whcih run on Docker - RIGHT
        Contains a APP which  need to be run - RIGHT
        VIRTAUL ISOLATED ENV - TO RUN A PARTICULAR APP - 
        VM  - NEED OS.
        --------------------

20 YEARS IN PAST --> 
1 APP --> PHYSCAL
20 APP -> 20 PHYSICAL
===================================
AVAILABILLITY -> LB -> NETWOROk -> OS -> KERNAL -> NAMESPACES -> NET

SCALABILITY -> MT -> NETWOROk -> OS -> KERNAL -> NAMESPACES -> NET

Security -> FIREWALL -> OS -> NAMESPACES

ISOLATION
===================================================

VMs --> HYPER

PC -> 

        PC ---> OS 
        
                NET - 1         FROM NET NS
                
                MNT - 1         FROM MTN NS
                
                PMAP - 1        FROM PMAP NS
                
                USER - UNLIMTED     FROM USER NS

========================================================================

# Container is nothing but a USER SPACE

                        EAch USER SPACE get
                        
                                OWN NETWOROk      FROM NET NAMESAPCE   --> KERNAL - OS
                                
                                OWN MNT             FROM MNT NAMESAPCE  --> KERNAL - OS  
                                
                                OWN PMAP            FROM PMAP NAMESAPCE   --> KERNAL - OS 



# Docker Components

        Docker --> Docker Client(HUMEN) ----REST-> DEAMON --> KERNAL

        Images --> FS + APP -- What you have in Image - You see inside a containrs
        
        Regirty - 
        
                PUB
                
                PVT

        COntainer

# Create VM -> Start -> Stop -> Start -> RESTART --> PAUSE -> UNPAUSE -->KILL -> REMOVE
======================================================================================  
 
 Containers

https://www.devopsschool.com/blog/simple-docker-workflow-quick-start/


docker create Image

docker start cont-id

docker stop cont-id

docker restart cont-id

docker puase cont-id

docker unpuase cont-id

docker kill cont-id

docker rm cont-id

========================================

DEMO - 13.234.75.229


RUN ===

PULL + CRAETE + START + ATTACH

#How to install Docker?

        https://www.devopsschool.com/tutorial/docker/install-config/
        https://www.devopsschool.com/tutorial/docker/install-config/docker-install-commuityedition-centos-rhel.html

#Verify what is container?

Container is nothing but a USER SPACE

        EAch USER SPACE get
        
        OWN NETWOROk      FROM NET NAMESAPCE   --> KERNAL - OS
        
        OWN MNT             FROM MNT NAMESAPCE  --> KERNAL - OS  
        
        OWN PMAP            FROM PMAP NAMESAPCE   --> KERNAL - OS 


  history
 
 clear
  
  ls
  
  clear
  
  sudo yum install -y yum-utils device-mapper-persistent-data lvm2
  
  sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
  
  sudo yum install –y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
  
  sudo yum-config-manager --enable rhui-REGION-rhel-server-extras
  
  sudo yum install -y docker-ce
  
  sudo yum install docker-ce
  
  docker -v
  
  clear
  
  clear
  
  ls
  
  ps -eaf | grep docker
  
  docker run -d jenkins
  
  sudo systemctl start docker
  
  clear
  
  docker run -d jenkins
  
  clear
  
  docker images
  
  docker ps
  
  docker run -d jenkins
  
  docker ps
  
  history
  
  clear
  
  docker ps
  
  clear
  
  ps -eaf | grep docker
  
  ps -eaf | grep 10714
  
  ps -eaf
  
  clear
  
  ls
  
  docker ps
  
  docker inspect 2c00eead0def | grep -i ip
  
  docker inspect 4ff178e8e41a | grep -i ip
  
  clear
  
  ls
  
  docker ps
  
  docker exec 2c00eead0def df -kh
  
  docker exec 4ff178e8e41a df -kh
  
  docker exec 4ff178e8e41a ls /
  
  docker ps
  
  docker exec 2c00eead0def ls /tmp
  
  docker exec 4ff178e8e41a ls /tmp
  
  docker exec 2c00eead0def touch /tmp/rajesh
  
  docker exec 2c00eead0def ls /tmp
  
  docker exec 4ff178e8e41a ls /tmp
  
  clear
  
  docker ps
  
  docker exec 2c00eead0def ps -eaf
  
  docker exec 4ff178e8e41a ps -eaf
  
  clear
  
  docker ps -a
  
  docker stop 2c00eead0def 4ff178e8e41a
  
  clear
  
  ls
  
  docker ps
  
  docker images
  
  docker ps
  
  docker ps -a
  
  docker rm 2c00eead0def 4ff178e8e41a
  
  clear
  
  docker ps
  
  docker ps -a
  
  docker images
  
  docker create jenkins
  
  docker ps
  
  docker ps -a
  
  clear
  
  docker ps -a
  
  docker start a54d46b3b1b7
  
  docker ps -a
  
  docker stop a54d46b3b1b7
  
  docker ps -a
  
  docker restart a54d46b3b1b7
  
  docker ps -a
  
  clear
  
  docker pause a54d46b3b1b7
  
  docker ps -a
  
  docker unpause a54d46b3b1b7
  
  docker ps -a
  
  docker kill a54d46b3b1b7
  
  docker ps -a
  
  docker rm a54d46b3b1b7
  
  clear
  
  docker ps -a
  
  history

# How to use that container?
 =====================================
 
 How to go inside a container?
 
       EXEC WAY
                Exec is a way to RUN an EXECUTABLE inside a container.
                      with -it and /bin/bash - you can go inside.
        
        ATTACH WAY
        
                ATTACH IS A WAY TO GO inside a container and BECOME PID 1

 # How to access a container from outside?       
   
    docker run -d -p 8080:8080 jenkins
    
    docker run -d -p 8090:8080 jenkins
    
    docker run -d -p 80:8080 jenkins


   ls
   
   docker ps -a
   
   docker inspect e16d9976df76 | grep -i ip
   
   ping 172.17.0.2
   
   curl http://172.17.0.2:8080
   
   clear
   
   ls
   
   docker ps -a
   
   docker stop e16d9976df76
   
   docker ps
   
   docker ps -a
   
   docker rm a26a891dabea e16d9976df76
   
   clear
   
   docker ps -a
   
   clear
   
   docker run -d -p 8080:8080 jenkins
   
   docker run -d -p 8090:8080 jenkins
   
   docker ps -a
   
   curl http://http://13.234.75.229:8090/
   
   curl http://13.234.75.229:8090/
   
   docker run -d -p 80:8080 jenkins
   
   history

=============================================

# Docker Volumes
https://www.devopsschool.com/blog/understand-docker-volume-from-beginner-to-deep-dive-level/

        - Docker volumes ----> /var/lib/docker/volumes
        - Docker mounts ---> Host Machine
        - Docker tmpfs --> Memory


    docker ps
    
    docker exec a26a891dabea ls
    
    docker exec a26a891dabea df
    
    docker exec a26a891dabea ps
    
    clear
    
    docker exec -it a26a891dabea /bin/bash
    
    docker ps
    
    docker attach a26a891dabea
    
    docker ps
    
    clear
    
    docker -s
    
    clear
    
    docker ps
    
    docker ps -a
    
    docker start e16d9976df76
    
    clear
    
    docker ps
    
    docker inspect e16d9976df76 | grep -ip
    
    docker inspect e16d9976df76 | grep -i -ip
    
    clear
    
    ls
    
    clear
    
    ls
    
    docker ps -a
    
    docker stop da40688dff44 a4ffc82fff7c 37a139cb7cba
    
    clear
    
    ls
    
    docker ps -a
    
    docker rm da40688dff44 a4ffc82fff7c 37a139cb7cba
    
    clear
    
    docker ps -a
    
    docker run ubuntu
    
    clear
    
    docker ps
    
    docker ps -a
    
    docker run -itd ubuntu
    
    docker ps
    
    clear
    
    docker ps -a
    
    docker ps
    
    docker exec -it d44d7527f877 /bin/bash
    
    ls
    
    cd /var/lib/docker
    
    ls
    
    find . -name devopsschool.com
    
    docker ps
    
    docker stop d44d7527f877
    
    find . -name devopsschool.com
    
    docker rm d44d7527f877
    
    find . -name devopsschool.com
    
    clear
    
    pwd
    
    cd volumes/
    
    pwd
    
    clear
    
    docker volume ls
    
    docker help volume
    
    docker volume prune
    
    clear
    
    ls
    
    docker volume ls
    
    docker help volume
    
    docker volume create raj
    
    ls
    
    docker volume ls
    
    clear
    
    docker volume ls
    
    docker ps -a
    
    docker rm 2e5b541567c1
    
    clear
    
    docker ps -a
    
    docker run -itd ubuntu
    
    docker
    
    clear
    
    docker ps
    
    docker run -itd -v raj:/opt/raja ubuntu
    
    docker ps
    
    docker exec 709e3bcc9344 df -kh
    
    docker attach 709e3bcc9344
    
    docker ps
    
    ls
    
    cd raj/
    
    ls
    
    cd _data/
    
    ls
    
    cd ..
    
    clear
    
    ls
    
    docker ps -a
    
    docker stop 709e3bcc9344 c4cfbf5d65d8
    
    docker rm 709e3bcc9344 c4cfbf5d65d8
    
    clear
    
    ls
    
    cd d
    
    cd _data/
    
    ls
    
    docker run -itd -v raj:/opt/raja ubuntu
    
    docker run -itd -v raj:/opt/raja ubuntu
    
    docker -s
    
    clear
    
    docker ps
    
    docker exec 3d1585232df2 ls /opt/raja
    
    docker exec 5cdfab909be8 ls /opt/raja
    
    ls
    
    vi raj1
    
    docker exec 5cdfab909be8 more /opt/raja/raj1
    
    ls
    
    pwd
    
    df -kh
    
    clear
    
    ls
    
    pwd
    
    history
    
    cd /opt/
    
    ls
    
    mkdir ff
    
    cd ff/
    
    clear
    
    ls
    
    pwd
    
    clear
    
    history
    
    clear
    
    docker ps -a
    
    clear
    
    clear
    
    ls
    
    docker ps
    
    ls
    
    docker stop 3d1585232df2 5cdfab909be8
    
    clear
    
    docker rm 3d1585232df2 5cdfab909be8
    
    clear
    
    docker ps -a
    
    docker run -itd -v /opt/ff:/opt/raja ubuntu
    
    docker ps
    
    cd /opt/
    
    ls
    
    cd ff/
    
    ls
    
    touch fdsfd
    
    touch fdsfdfdfdfsf
    
    touch fdsfdfdfdfsffdsfsf
    
    ls
    
    docker ps
    
    docker exec b168d232ca82 ls /opt/raja
    
    history




# Docker Networking

rajesh@scmgalaxy.com


## Doc-Kube-Blr-Happiest-Jan-2020


1 3.6.126.223
2 52.66.143.139
3 52.66.245.244
4 15.206.178.196
5 52.66.245.247
6 13.235.83.86
# 7 13.127.66.47
8 13.127.72.116
9 13.232.36.116
10 13.233.145.128
# 11 13.233.59.73
12 35.154.224.43
13 3.6.126.187
14 35.154.187.93
15 13.233.23.143
16 13.126.193.192
17 13.127.101.148
18 52.66.250.100
19 15.206.187.31
20 13.232.234.220
21 13.126.225.49
22 13.234.76.69
23 13.232.229.115
24 15.206.163.154
25 13.232.192.24
26 13.235.79.163
27 13.233.23.6
28 13.235.49.122
29 35.154.221.233

ec2-user

KEY
https://www.devopsschool.com/notes/docker/2019/

PUTTY - 	rajesh-mumbai.ppk
SSH - 	rajesh-mumbai.pem

==============================================

# UNDERSTANDING A IMAGE ANATOMY

   cd /var/lib/
   cd docker
   clear
   ls
   cd overlay2/
   ls
   docker inspect ubuntu
   clear
   ls
   du --sh --max-depth=1
   du -sh --max-depth=1
   du -s --max-depth=1
   du -h --max-depth=1
   clear
   du -h --max-depth=1
   cd ./f50968ffd1f2a7829071812ba67920814891d03151b36f173afab664c88faa29
   ls
   clear
   ls
   cd diff/
   clear
   ls
   cd ..
   ls
   cd ..
   ls
   clear
   du -h --max-depth=1
   cd ./f35bf180baaea3d1d4079c19e42f2add606214c90a3c734a56653c1ea85083b7
   ls
   cd diff/
   ls
   cd run/
   ls
   cd systemd/
   ls
   clear
   ls
   more container
   cd ..
   ls
   cd ..
   ls
   cd ..
   ls
   cd ..
   clear
   ls
   pwd
   docker history ubuntu
   clear
   ls
   clear
   df -kh
   docker run -itd ubuntu
   docker ps
   ls
   df -kh
   docker run -itd ubuntu
   df -kh
   ls
   cd ..
   ls
   cd containers/
   ls
   ddf -kh
   df -kh
   cleatr
   clear
   ls
   cd ..
   ls
   cd overlay2/
   clear
   ls
   docker ps -a
   docker stop  d0f77b11eb9c bb9861e9f15d
   clear
   ls
   df -kh
   clear
   ls


How to create docker image?
Lazy WAY - Using Existing Container
    docker ps
    docker exec -it d0f77b11eb9c /bin/bash
    clear
    docker ps
    docker exec d0f77b11eb9c git
    clear
    git
    docker exec d0f77b11eb9c git
    clear
    docker exec d0f77b11eb9c git
    clear
    ls
    docker images
    docker ps
    docker commit -a "Rajeshkumar" -m"ub-git-up" d0f77b11eb9c ub-git-up
    docker images
    docker history ubuntu
    docker history ub-git-up
    docker run -itd ubuntu
    docker run -itd ub-git-up
    docker ps -a


AUtomated Way - Using Dockerfile

FROM ubuntu
MAINTAINER Rajesh Kumar DevopS@Rajeshkumar.xyz
RUN apt-get update 
RUN apt-get install git -y

docker build -t new-image .


jenkins
    openjdk:8-jdk
        buildpack-deps:stretch-scm
                buildpack-deps:stretch-curl
                    debian:stretch
                            scratch



FROM ubuntu
MAINTAINER Rajesh Kumar DevopS@Rajeshkumar.xyz
RUN touch /opt/rajesh1.txt && touch /opt/rajesh3.txt && touch /opt/rajesh2.tx
RUN touch /opt/rajesh4.txt

docker build -f doc1 -t new1 .




TROUBLESHOOTING
https://www.devopsschool.com/blog/docker-error-requires-container-selinux-22-74/


https://www.devopsschool.com/videos/



