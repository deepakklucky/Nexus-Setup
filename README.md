# Nexus-Setup

Prerequisites

1) EC2 instance with java

2) Implementation steps

3) Download and setup nexus stable version

4) cd /opt

5) wget https://sonatype-download.global.ssl.fastly.net/nexus/3/nexus-3.0.2-02-unix.tar.gz
tar -zxvf  nexus-3.0.2-02-unix.tar.gz

6) mv /opt/nexus-3.0.2-02 /opt/nexus


As a good security practice, it is not advised to run nexus service as root , 
so create new user called nexus and grant sudo access to manage nexus services

7) sudo adduser nexus

8) # visudo \\ nexus   ALL=(ALL)       NOPASSWD: ALL

9) sudo chown -R nexus:nexus /opt/nexus

10) Open /opt/nexus/bin/nexus.rc                            file, uncomment run_as_user parameter and set it as following.

11) vi /opt/nexus/bin/nexus.rc

12) run_as_user="nexus" (file shold have only this line)

13) Add nexus as a service at boot time


14) sudo ln -s /opt/nexus/bin/nexus /etc/init.d/nexus

15) Login as a nexus user and start service

16) su - nexus

17) service nexus start

18) Login nexus server from browser on port 8081

19) http://<Nexus_server>:8081

20) Use default credentials to login

21) username : admin
22) password : admin123

23) Troubleshooting

24) service is not starting?

25) make sure you are trying to start service with nexus user.
26) check java installation
27) Unable to access nexus URL?

28) make sure port 8081 is opened in security group.
