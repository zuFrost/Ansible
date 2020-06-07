# Ansible
## 1. install Ansible on Ubuntu-16 and CentOS-7
![install Ansible on Ubuntu-16 and CentOS-7](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/install%20ansible%20CentOS.jpg)
![install Ansible on Ubuntu-16 and CentOS-7](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/install%20ansible%20Ubuntu.jpg)
## 2. install Ansible on Amazon Linux via PIP
![install Ansible on Amazon Linux via PIP](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/install%20ansible%20on%20Amazon%20Linux%20via%20PIP.jpg)
## 3. Ansible connect to Amazon Linux Clients
![Ansible connect to Amazon Linux Clients](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/Ansible%20connect%20to%20Amazon%20Linux%20Clients.jpg)
## 4. Ansible connect to Amazon Windows Clients
![Ansible connect to Amazon Windows Clients](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/Ansible%20connect%20to%20Amazon%20Windows%20Clients.jpg)
## 5. Create example Ansible Inventory file 
![hosts.txt](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/hosts.txt)
## 6. Ansible. Runing Ad-Hoc commands



### 6.1 Запуск Ad-Hoc комманд
ansible all -m shell -a "ls -ls /home"
            -m ping
            -m setup
### 6.2 Копирование с Мастера на все Ноды
ansible prod_servers -m copy -a "src=privet.txt dest=/home mode=777" -b
### 6.3 удаление файла на всех Нодах
ansible all -m file -a "path=/home/privet.txt state=absent" -b
### 6.4 Загрузка файла с сайта
ansible all -m get_url -a "url=https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/install%20ansible%20Ubuntu.jpg dest=/home" -b
### 6.5 Удаление файла
ansible all -m file -a "path=/home/install%20ansible%20Ubuntu.jpg state=absent" -b
### 6.6 Подключиться к сайту
ansible all -m uri -a "url=http://www.adv-it.net"
### 6.7 Подключиться к сайту и прочитать контент
ansible all -m uri -a "url=http://www.adv-it.net return_content=yes"
### 6.8 Установка httpd
ansible all -m yum -a "name=httpd state=latest" -b
### 6.9 Запуск httpd и включение автозапуска при старте ОС
ansible all -m service -a "name=httpd state=started enabled=yes" -b
### 6.10 Удаление httpd
ansible all -m yum -a "name=httpd state=removed" -b
### 6.11 дебаггинг
ansible staging_servers -m shell -a "ls /var" -vvv
### 6.12 встроенный справочник
ansible-doc -l | grep ec2



## 7. Ansible - Правила Формата YAML
![myfile.yml](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/myfile.yml)


## 8. Ansible - Перенос переменных из Inventory файла hosts.txt в group_vars/
![hosts.txt](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/ansible/hosts.txt)

![group_vars директория](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/tree/master/ansible/group_vars) содержащая файлы с переменными 
![ALL_SERVERS_DB](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/ansible/group_vars/ALL_SERVERS_DB)

![PROD_SERVERS_WEB](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/ansible/group_vars/PROD_SERVERS_WEB)

![STAGING_SERVERS_WEB](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/ansible/group_vars/STAGING_SERVERS_WEB) 
результат проверяем коммандами:
ansible-inventory --list 
и
tree

## 9. Ansible - Playbooks
![Test Connection to my servers](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/playbooks/playbook1.yml)

![Install default Apache Web Server](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/playbooks/playbook2.yml)

![Install Apache and Upload my Web Page. Reload Apache when Web Page changed](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/playbooks/playbook3.yml)

## 10. Ansible - Playbook Variables Debag Set_fact Register
![Playbook Variables Debag Set_fact Register](https://github.com/zuFrost/Ansible-install-Ubuntu-and-CentOS/blob/master/playbooks/playbook_Variables_Debag_Set_fact_Register.yml)

