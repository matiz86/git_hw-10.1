Домашнее задание к занятию "10.1 «Keepalived/vrrp»" - Skopkin Ilya


Задание 1
Разверните топологию из лекции и выполните установку и настройку сервиса Keepalived.
 
NODE 1

vrrp_instance zadanie_1 {

state MASTER

interface enp0s3

virtual_router_id 100

priority 110

advert_int 4

authentication {

auth_type AH

auth_pass 1111

}

unicast_peer {

192.168.0.105

}

virtual_ipaddress {

192.168.0.50 dev enp0s3 label enp0s3:vip

}

}

![alt text](https://github.com/matiz86/git_hw-10.1/blob/main/VirtualBox_zabbix_test_02_04_2023_11_13_02.png)


NODE 2

vrrp_instance zadanie_1 {

state BACKUP

interface enp0s3

virtual_router_id 100

priority 100

advert_int 4

authentication {

auth_type AH

auth_pass 1111

}

unicast_peer {

192.168.0.106

}

virtual_ipaddress {

192.168.0.50 dev enp0s3 label enp0s3:vip

}

}

![alt text](https://github.com/matiz86/git_hw-10.1/blob/main/VirtualBox_zabbix_test2_02_04_2023_11_13_32.png)
