
all: install config ping

software:
	
	sudo apt install ansible -y
	sudo apt install git curl npm -y
	

inventory_file := "[default] \nlocalhost    ansible_connection=local"

ansible_config_file := "[defaults] \ninventory = inventory \nhost_key_checking = False\
			\ndeprecation_warnings=False"


config:
	
	echo $(inventory_file) >> inventory
	echo $(ansible_config_file) >> ansible.cfg
ping:
	ansible all -m ping

install_jupyterhub:
	
	ansible-playbook  master.yml
	

install_docker:
	
	ansible-playbook  docker.yml
	#docker ps



clean:
	rm inventory *.cfg

remove:
	sudo apt remove docker -y
	sudo apt remove portainer -y
	sudo apt remove python3 -y
