# Vagrant Docker ELK Grafana
A simply Vagrantfile for Docker, ELK stack & Grafana

### Prerequesits:
* Git
* Oracle Virtual box
* Vagrant

#

### Vagrantfile Job:
1. Creates an Ubuntu 18.04 VM with 2 CPU's and 2048 MB Ram memory
2. Installs Docker & Docker-compose on first startup (provision)
3. Clones a Git repository containing docker-compose.yml file which creates 3 services:
	* Elastic search
	* Kibana
	* Logstash
	* Grafana
4. Creates port forwarding for all services:
	* Port 9200 for Elastic search
	* Port 5601 for Kibana
	* Port 5000 for Logstash 
	* Port 3000 for Grafana
5. every startup (Vagrant up) the docker-compose file will run and start all services.


# 

### Initial setup:

    $ git clone https://github.com/Dgotlieb/Vagrant-Docker-ELK-Grafana.git 
    $ cd Vagrant-Docker-ELK-Grafana
    $ vagrant up
    
    
### How to use:
 
##### Elastic search: 

Post some data to localhost 9200.

for example:

    http://localhost:9200/my_app/user 
    
    {
    "name":"user",
    "id": 123
     }
    
    
 #
 
 ##### Kibana : 
 Enter localhost:5601
 
 #
 
 ##### Logstash
 Send data over TCP to localhost:5000
 To make it easier, run send.py file:
    
    $ Python send.py  
    
 #
 
 ##### Grafana
 Enter localhost:3000
     
     Username: admin
     Password: admin
 
