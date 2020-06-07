# Ansible
## install Ansible on Ubuntu-16 and CentOS-7
![install Ansible on Ubuntu-16 and CentOS-7](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/install%20ansible%20CentOS.jpg)
![install Ansible on Ubuntu-16 and CentOS-7](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/install%20ansible%20Ubuntu.jpg)
## install Ansible on Amazon Linux via PIP
![install Ansible on Amazon Linux via PIP](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/install%20ansible%20on%20Amazon%20Linux%20via%20PIP.jpg)
## Ansible connect to Amazon Linux Clients
![Ansible connect to Amazon Linux Clients](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/Ansible%20connect%20to%20Amazon%20Linux%20Clients.jpg)
## Ansible connect to Amazon Windows Clients
![Ansible connect to Amazon Windows Clients](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/Ansible%20connect%20to%20Amazon%20Windows%20Clients.jpg)
## Create example Ansible Inventory file 
![hosts.txt](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/hosts.txt)
## Ansible. Runing Ad-Hoc commands



### Запуск Ad-Hoc комманд
ansible all -m shell -a "ls -ls /home"
            -m ping
            -m setup
### Копирование с Мастера на все Ноды
ansible prod_servers -m copy -a "src=privet.txt dest=/home mode=777" -b
### удаление файла на всех Нодах
ansible all -m file -a "path=/home/privet.txt state=absent" -b
### Загрузка файла с сайта
ansible all -m get_url -a "url=https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/install%20ansible%20Ubuntu.jpg dest=/home" -b
### Удаление файла
ansible all -m file -a "path=/home/install%20ansible%20Ubuntu.jpg state=absent" -b
### Подключиться к сайту
ansible all -m uri -a "url=http://www.adv-it.net"
### Подключиться к сайту и прочитать контент
ansible all -m uri -a "url=http://www.adv-it.net return_content=yes"
### Установка httpd
ansible all -m yum -a "name=httpd state=latest" -b
### Запуск httpd и включение автозапуска при старте ОС
ansible all -m service -a "name=httpd state=started enabled=yes" -b
### Удаление httpd
ansible all -m yum -a "name=httpd state=removed" -b
### дебаггинг
ansible staging_servers -m shell -a "ls /var" -vvv
### встроенный справочник
ansible-doc -l | grep ec2
