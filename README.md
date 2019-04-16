ansible-role-kafka
=========

[![Build Status](https://travis-ci.org/alvarobacelar/ansible-role-kafka.svg?branch=master)](https://travis-ci.org/alvarobacelar/ansible-role-kafka)

Instalação do kafka nos servidores RedHat e/ou CentOS

Requesitos
------------

Para o kafka funcionar é necessário ter o zookeeper funcionando em um servidor onde deve ser informado qual é o endereço de acesso, que por padrão é o localhost (partindo da premissa que o zookeeper está instalado na máquina onde está sendo instalada o kafka)

Role Variáveis
--------------

Como dito anteriormente, é necessário passar a variável do host e porta do zookeeper, caso o mesmo esteja em servidor diferente. Se não informada o valor padrão desta variável é localhost, bem como as demais variáveis com os valores defaults abaixo:
```yml
path_kafka: /etc/kafka
user_kafka: kafkauser
version_kafka: 2.2.0
version_kafka_release: 2.12
port_kafka: 9092
num_partition: 1
num_threads: 8
default_replication: 1
offset_topic_replication: 1
log_dir_kafka: /var/log/kafka
pass_key_kafka: mypass
log_retention_hours: 60
enable_zoo_connect: true
zoo_host_server: localhost
zoo_port_server: 2181
client_port_zoo: 2181
xmx_limit: 2g
xms_limit: 2g
data_dir_zoo: /var/lib/zookeeper
port_exp_prom: 7072
```

Dependencias
------------

Por padrão essa role usa uma dependência para a instalação do zookeeper. Ao baixar essa role utilizando o ansible galaxy com comando abaixo, você vai baixar todas as suas dependências também:
```bash
# ansible-galaxy install alvarobacelar.ansible_role_kafka
``` 
As dependências são: 
 - java
 - zookeeper

Examplo de Playbook
----------------

Abaixo um exemplo basico de arquivo de playbook

    - hosts: servers
      roles:
         - kafka

License
-------

BSD

Informação do Autor
------------------
Alvaro Bacelar - Especialista em Infraestrutura, entusiasta DevOps e Infra As Code
