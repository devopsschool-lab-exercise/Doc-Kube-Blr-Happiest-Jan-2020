
Install git inside container & new commit details
=================================
docker ps -a 

docker exec -it d0f77b11eb9c /bin/bash

apt-get update 

apt-get install git

exit

docker exec c7a35a5e9794 git

docker images

docker commit -a "rajeesh" -m"ub-git-ubuntu" c7a35a5e9794 ub-git-ubuntu

docker images
======================================
env variable for jenkins
======================================
docker run -itd jenkins

docker ps -a 

docker exec -it d7d2fb4994e5 /bin/bash

env

exit

DevOps
================
https://www.youtube.com/watch?v=-VaVmb_UOC8

What is Docker?
    Container mgmt tool

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
Container is nothing but a USER SPACE
                            EAch USER SPACE get
                                        OWN NETWOROk      FROM NET NAMESAPCE   --> KERNAL - OS
                                        OWN MNT             FROM MNT NAMESAPCE  --> KERNAL - OS  
                                        OWN PMAP            FROM PMAP NAMESAPCE   --> KERNAL - OS 



Docker Components
        Docker --> Docker Client(HUMEN) ----REST-> DEAMON --> KERNAL
        Images --> FS + APP -- What you have in Image - You see inside a containrs
        Regirty - 
                    PUB
                    PVT
        COntainer

Create VM -> Start -> Stop -> Start -> RESTART --> PAUSE -> UNPAUSE -->KILL -> REMOVE
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

How to install Docker?
https://www.devopsschool.com/tutorial/docker/install-config/
https://www.devopsschool.com/tutorial/docker/install-config/docker-install-commuityedition-centos-rhel.html

Verify what is container?
Container is nothing but a USER SPACE
                            EAch USER SPACE get
                                        OWN NETWOROk      FROM NET NAMESAPCE   --> KERNAL - OS
                                        OWN MNT             FROM MNT NAMESAPCE  --> KERNAL - OS  
                                        OWN PMAP            FROM PMAP NAMESAPCE   --> KERNAL - OS 

[root@ip-172-31-14-237 ec2-user]# history
    1  clear
    2  ls
    3  clear
    4  sudo yum install -y yum-utils device-mapper-persistent-data lvm2
    5  sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    6  sudo yum install –y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
    7  sudo yum-config-manager --enable rhui-REGION-rhel-server-extras
    8  sudo yum install -y docker-ce
    9  sudo yum install docker-ce
   10  docker -v
   11  clear
   12  clear
   13  ls
   14  ps -eaf | grep docker
   15  docker run -d jenkins
   16  sudo systemctl start docker
   17  clear
   18  docker run -d jenkins
   19  clear
   20  docker images
   21  docker ps
   22  docker run -d jenkins
   23  docker ps
   24  history
   25  clear
   26  docker ps
   27  clear
   28  ps -eaf | grep docker
   29  ps -eaf | grep 10714
   30  ps -eaf
   31  clear
   32  ls
   33  docker ps
   34  docker inspect 2c00eead0def | grep -i ip
   35  docker inspect 4ff178e8e41a | grep -i ip
   36  clear
   37  ls
   38  docker ps
   39  docker exec 2c00eead0def df -kh
   40  docker exec 4ff178e8e41a df -kh
   41  docker exec 4ff178e8e41a ls /
   42  docker ps
   43  docker exec 2c00eead0def ls /tmp
   44  docker exec 4ff178e8e41a ls /tmp
   45  docker exec 2c00eead0def touch /tmp/rajesh
   46  docker exec 2c00eead0def ls /tmp
   47  docker exec 4ff178e8e41a ls /tmp
   48  clear
   49  docker ps
   50  docker exec 2c00eead0def ps -eaf
   51  docker exec 4ff178e8e41a ps -eaf
   52  clear
   53  docker ps -a
   54  docker stop 2c00eead0def 4ff178e8e41a
   55  clear
   56  ls
   57  docker ps
   58  docker images
   59  docker ps
   60  docker ps -a
   61  docker rm 2c00eead0def 4ff178e8e41a
   62  clear
   63  docker ps
   64  docker ps -a
   65  docker images
   66  docker create jenkins
   67  docker ps
   68  docker ps -a
   69  clear
   70  docker ps -a
   71  docker start a54d46b3b1b7
   72  docker ps -a
   73  docker stop a54d46b3b1b7
   74  docker ps -a
   75  docker restart a54d46b3b1b7
   76  docker ps -a
   77  clear
   78  docker pause a54d46b3b1b7
   79  docker ps -a
   80  docker unpause a54d46b3b1b7
   81  docker ps -a
   82  docker kill a54d46b3b1b7
   83  docker ps -a
   84  docker rm a54d46b3b1b7
   85  clear
   86  docker ps -a
   87  history

How to use that container?
 =====================================
 How to go inside a container?
        EXEC WAY
                Exec is a way to RUN an EXECUTABLE inside a container.
                    with -it and /bin/bash - you can go inside.
        ATTACH WAY
                ATTACH IS A WAY TO GO inside a container and BECOME PID 1

 How to access a container from outside?       
        docker run -d -p 8080:8080 jenkins
        docker run -d -p 8090:8080 jenkins
        docker run -d -p 80:8080 jenkins


 128  ls
  129  docker ps -a
  130  docker inspect e16d9976df76 | grep -i ip
  131  ping 172.17.0.2
  132  curl http://172.17.0.2:8080
  133  clear
  134  ls
  135  docker ps -a
  136  docker stop e16d9976df76
  137  docker ps
  138  docker ps -a
  139  docker rm a26a891dabea e16d9976df76
  140  clear
  141  docker ps -a
  142  clear
  143  docker run -d -p 8080:8080 jenkins
  144  docker run -d -p 8090:8080 jenkins
  145  docker ps -a
  146  curl http://http://13.234.75.229:8090/
  147  curl http://13.234.75.229:8090/
  148  docker run -d -p 80:8080 jenkins
  149  history
=============================================

•	Docker Volumes
https://www.devopsschool.com/blog/understand-docker-volume-from-beginner-to-deep-dive-level/

- Docker volumes ----> /var/lib/docker/volumes
- Docker mounts ---> Host Machine
- Docker tmpfs --> Memory


 105  docker ps
  106  docker exec a26a891dabea ls
  107  docker exec a26a891dabea df
  108  docker exec a26a891dabea ps
  109  clear
  110  docker exec -it a26a891dabea /bin/bash
  111  docker ps
  112  docker attach a26a891dabea
  113  docker ps
  114  clear
  115  docker -s
  116  clear
  117  docker ps
  118  docker ps -a
  119  docker start e16d9976df76
  120  clear
  121  docker ps
  122  docker inspect e16d9976df76 | grep -ip
  123  docker inspect e16d9976df76 | grep -i -ip
  124  clear
  125  ls
  126  clear
  127  ls
  128  docker ps -a
  129  docker stop da40688dff44 a4ffc82fff7c 37a139cb7cba
  130  clear
  131  ls
  132  docker ps -a
  133  docker rm da40688dff44 a4ffc82fff7c 37a139cb7cba
  134  clear
  135  docker ps -a
  136  docker run ubuntu
  137  clear
  138  docker ps
  139  docker ps -a
  140  docker run -itd ubuntu
  141  docker ps
  142  clear
  143  docker ps -a
  144  docker ps
  145  docker exec -it d44d7527f877 /bin/bash
  146  ls
  147  cd /var/lib/docker
  148  ls
  149  find . -name devopsschool.com
  150  docker ps
  151  docker stop d44d7527f877
  152  find . -name devopsschool.com
  153  docker rm d44d7527f877
  154  find . -name devopsschool.com
  155  clear
  156  pwd
  157  cd volumes/
  158  pwd
  159  clear
  160  docker volume ls
  161  docker help volume
  162  docker volume prune
  163  clear
  164  ls
  165  docker volume ls
  166  docker help volume
  167  docker volume create raj
  168  ls
  169  docker volume ls
  170  clear
  171  docker volume ls
  172  docker ps -a
  173  docker rm 2e5b541567c1
  174  clea
  175  clear
  176  docker ps -a
  177  docker run -itd ubuntu
  178  docker
  179  clear
  180  docker ps
  181  docker run -itd -v raj:/opt/raja ubuntu
  182  docker ps
  183  docker exec 709e3bcc9344 df -kh
  184  docker attach 709e3bcc9344
  185  docker ps
  186  ls
  187  cd raj/
  188  ls
  189  cd _data/
  190  ls
  191  cd ..
  192  clear
  193  ls
  194  docker ps -a
  195  docker stop 709e3bcc9344 c4cfbf5d65d8
  196  docker rm 709e3bcc9344 c4cfbf5d65d8
  197  clear
  198  ls
  199  cd d
  200  cd _data/
  201  ls
  202  docker run -itd -v raj:/opt/raja ubuntu
  203  docker run -itd -v raj:/opt/raja ubuntu
  204  docker -s
  205  clear
  206  docker ps
  207  docker exec 3d1585232df2 ls /opt/raja
  208  docker exec 5cdfab909be8 ls /opt/raja
  209  ls
  210  vi raj1
  211  docker exec 5cdfab909be8 more /opt/raja/raj1
  212  ls
  213  pwd
  214  df -kh
  215  clear
  216  ls
  217  pwd
  218  history
  219  cd /opt/
  220  ls
  221  mkdir ff
  222  cd ff/
  223  clear
  224  ls
  225  pwd
  226  clear
  227  history
  228  clear
  229  docker ps -a
  230  s
  231  clear
  232  s
  233  clear
  234  ls
  235  docker ps
  236  ls
  237  docker stop 3d1585232df2 5cdfab909be8
  238  clear
  239  docker rm 3d1585232df2 5cdfab909be8
  240  ckear
  241  clear
  242  docker ps -a
  243  docker run -itd -v /opt/ff:/opt/raja ubuntu
  244  docker ps
  245  cd /opt/
  246  ls
  247  cd ff/
  248  ls
  249  touch fdsfd
  250  touch fdsfdfdfdfsf
  251  touch fdsfdfdfdfsffdsfsf
  252  ls
  253  docker ps
  254  docker exec b168d232ca82 ls /opt/raja
  255  history



•	Docker Networking

rajesh@scmgalaxy.com


Doc-Kube-Blr-Happiest-Jan-2020


1 3.6.126.223
2 52.66.143.139
3 52.66.245.244
4 15.206.178.196
5 52.66.245.247
6 13.235.83.86
7 13.127.66.47
8 13.127.72.116
9 13.232.36.116
10 13.233.145.128
11 13.233.59.73
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
UNDERSTANDING A IMAGE ANATOMY

  289  cd /var/lib/
  290  cd docker
  291  clear
  292  ls
  293  cd overlay2/
  294  ls
  295  docker inspect ubuntu
  296  clear
  297  ls
  298  du --sh --max-depth=1
  299  du -sh --max-depth=1
  300  du -s --max-depth=1
  301  du -h --max-depth=1
  302  clear
  303  du -h --max-depth=1
  304  cd ./f50968ffd1f2a7829071812ba67920814891d03151b36f173afab664c88faa29
  305  ls
  306  clear
  307  ls
  308  cd diff/
  309  clear
  310  ls
  311  cd ..
  312  ls
  313  cd ..
  314  ls
  315  clear
  316  du -h --max-depth=1
  317  cd ./f35bf180baaea3d1d4079c19e42f2add606214c90a3c734a56653c1ea85083b7
  318  ls
  319  cd diff/
  320  ls
  321  cd run/
  322  ls
  323  cd systemd/
  324  ls
  325  clear
  326  ls
  327  more container
  328  cd ..
  329  ls
  330  cd ..
  331  ls
  332  cd ..
  333  ls
  334  cd ..
  335  clear
  336  ls
  337  pwd
  338  docker history ubuntu
  339  clear
  340  ls
  341  clear
  342  df -kh
  343  docker run -itd ubuntu
  344  docker ps
  345  ls
  346  df -kh
  347  docker run -itd ubuntu
  348  df -kh
  349  ls
  350  cd ..
  351  ls
  352  cd containers/
  353  ls
  354  ddf -kh
  355  df -kh
  356  cleatr
  357  clear
  358  ls
  359  cd ..
  360  ls
  361  cd overlay2/
  362  clear
  363  ls
  364  docker ps -a
  365  docker stop  d0f77b11eb9c bb9861e9f15d
  366  clear
  367  ls
  368  df -kh
  369  clear
  370  ls


How to create docker image?
Lazy WAY - Using Existing Container
 382  docker ps
  383  docker exec -it d0f77b11eb9c /bin/bash
  384  clear
  385  docker ps
  386  docker exec d0f77b11eb9c git
  387  clear
  388  git
  389  docker exec d0f77b11eb9c git
  390  clear
  391  docker exec d0f77b11eb9c git
  392  clear
  393  ls
  394  docker images
  395  docker ps
  396  docker commit -a "Rajeshkumar" -m"ub-git-up" d0f77b11eb9c ub-git-up
  397  docker images
  398  docker history ubuntu
  399  docker history ub-git-up
  400  docker run -itd ubuntu
  401  docker run -itd ub-git-up
  402  docker ps -a


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
