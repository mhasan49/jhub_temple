
all: software install ping

software:

	yum update -y
	yum install epel-release -y
	yum install ansible -y
	yum install python3 -y
	
docker:
	
	ansible-playbook  docker.yml
#	ansible-playbook  portainer.yml
	docker ps
	

install_jupyterhub:
	
	ansible-playbook  master.yml


ping:
	ansible all -m ping



clean:
	rm inventory *.cfg

remove:
	
	yum remove epel-release -y
	yum remove ansible -y
	yum remove python3 -y
