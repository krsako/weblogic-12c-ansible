# weblogic-ansible
Ansible playbook for deploying a WebLogic 12c R2 Domain

You can connect to admin server on port 7001 using weblogic/welcome1

Server start manually, inside domain path bin folder:

NodeManager:  
nohup ./startNodeManager.sh > no_weblogic.log 2>&1 &

WebLogic:  
nohup ./startWebLogic.sh > no_weblogic.log 2>&1 &


Playbook includes the following roles:
- wls-prereq
- java
- weblogic
- wls-domain

wls-prereq:  
This role configures the Linux system with requirements to run the WebLogic domain

java:  
This role configures the Linux system with JDK8
JDK rpm file needs to be inside path: roles/java/files

weblogic:  
This role installs the Weblogic 12c R2 in Oracle Linux 7
Weblogic firmware needs to be inside path: roles/weblogic/files

wls-domain:  
This role creates and configures a Domain with Weblogic
Creates some initial configuration like boot.properties file
