# Final ESIEE Ansible Project  - Devops

The goal of this project is to deploy the webapp data-engineering, coded by Boris Ghidaglia, an ESIEE student.
This webapp displays crawled tripadvisors reviews. https://github.com/borisghidaglia/data-engineering

## What should the students do ?

- The students should deploy the webapp with Docker on 2 instances, behind a HAProxy. 
The webapp instances should be accessible at [http://192.168.201.10](http://192.168.201.10)

- HAProxy should display stats on /info

- The data are stored and indexed with Mongodb and Elasticsearch. Therefore,each of these apps should be deployed on separate instances.

## Vagrant

For this project, 5 Vagrant machines are provided:

- haproxy: 192.168.201.10
- app1: 192.168.201.11
- app2: 192.168.201.12
- mongodb: 192.168.201.13
- elasticsearch: 192.168.201.14

To create and boot the Vms, just run

```
$ cd ansible
$ vagrant up
```

To enter the Vms, just run

```
$ cd ansible
$ vagrant ssh <vm_name> (ex: vagrant ssh haproxy)
```

## How to run the project

```
$ cd ansible
$ vagrant up
$ ansible-playbook -i inventories deploy-app.yml
```

http://192.168.201.10/ to connect to haproxy

http://192.168.201.10:9000/info to look at the stats
