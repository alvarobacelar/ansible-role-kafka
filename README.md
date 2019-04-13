ansible-role-kafka
=========

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
log_dir_kafka: /var/log/kafka
enable_zoo_connect: true
zoo_host_server: localhost # host do zookeeper
zoo_port_server: 2181 # porta do zookeepr
```

Dependencias
------------

Por padrão essa role usa uma dependência para a instalação do zookeeper, para executar essa role é preciso primeiro baixar as roles dependentes com o seguinte comando: 
```bash
# ansible-galaxy install -r requeriments.yml
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
