ansible-role-kafka
=========

[![Build Status](https://travis-ci.org/alvarobacelar/ansible-role-kafka.svg?branch=master)](https://travis-ci.org/alvarobacelar/ansible-role-kafka)

Installation of kafka broker on RadHat

Requiriments
------------

For run this role you must create file of inventory, or use the host_example.yml this repo, with groups **zookeeper** and **kafka_broker** with each host corresponding on its group.

The Apache Kafka require the cluster ZooKeeper. However, this role have dependecies on the ZooKeeper and Java role. Don't worry with this dependecies, when you download this role, will be download automatically all dependecies. For download use the command bellow: 

```shell
ansible-galaxy install alvarobacelar.ansible_role_kafka
```

Role Variables
--------------

This role have very much variables and it is availibles in the file _main.yml_ on directory _defaults_. If you want change propertiers of kafka broker, create on file of variables for playbook and set all key values on the your broker configuration.


Example of Playbook
----------------

The playbook this role must be the following:

    - hosts: kafkabroker
      become: true
      roles:
         - kafka

License
-------

BSD

About Author
------------------
Alvaro Bacelar - Infraestructure especialist, enthusiastic DevOps and Infra As Code
