vitalii@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:~/Документы/docker$ docker run -d -it -v data:/var/first/data --name first_node node:15.14 /bin/bash
0c4c04146a8c10b1ad6d626203354d9f3b7790b0d55a1c79c66ceeacc977ada2
vitalii@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:~/Документы/docker$ docker exec first_node bash -c "echo 'server_one' >> /var/first/data/first.md"
vitalii@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:~/Документы/docker$ docker docker run -d -it -v data:/var/second/data --name second_node node:15.14 /bin/bash
8a3e805aebf9c95330665b5483dd80b11551e74b06572f9b063036f1f84b56f6
vitalii@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:~/Документы/docker$ docker run -d -it -v /home/vitalii/Документы/docker/data:/var/second/data --name second_node node:15.14 /bin/bash
7d6dd78cf226bdade5c14fc4e63e4b3b0097f13527482813a9af40c00792caa7
vitalii@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:~/Документы/docker$ docker exec second_node bash -c "ls -l /var/second/data"
total 8
-rw-r--r-- 1 root root 11 Jul 10 10:10 first.md
-rw-rw-r-- 1 node node 10 Jul 10 09:59 host.md
vitalii@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:~/Документы/docker$ docker exec second_node bash -c "cat /var/second/data/first.md /var/second/data/host.md"
server_one
host file
vitalii@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:~/Документы/docker$ docker stop first_node 
first_node
vitalii@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:~/Документы/docker$ docker rm first_node 
first_node
vitalii@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:~/Документы/docker$ docker stop second_node 
second_node
vitalii@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:~/Документы/docker$ docker rm second_node 
second_node
vitalii@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:~/Документы/docker$ docker rmi node:15.14
Untagged: node:15.14
Untagged: node@sha256:608bba799613b1ebf754034ae008849ba51e88b23271412427b76d60ae0d0627
Deleted: sha256:3d3f41722daf1a77c34d6eade6676bbffa2d6a2a21095de2ab0c427a5c942fc9
Deleted: sha256:601382991a159cfc5013ad973158f30b7b7a913e8d7e547b3456deab3ad98022
Deleted: sha256:d5db49eecae8c02c9ea3a79f89c43ded9162bac118a0302a7b514d0df82aa112
Deleted: sha256:a2c1973858d0aad3de0927294602b17c8ef9050c30e0f461e0868997a08552a4
Deleted: sha256:a0153172017a08a521a8be971ca4dcb5fbc4b7227642c12bbb2da6265bd66b50
Deleted: sha256:f1123940e954d335d91b52a40fab4f8144f38ff113ade7d65663071d0f06da6f
Deleted: sha256:f1f4fbb0e7e6e0ce2d9eae1e577f9f6df0a719dd874bff00b2d08895c75c297d
Deleted: sha256:1eb455ab6d45fdbbd90fccff791ffa228080c052acf464f8da1b1d78650bd706
Deleted: sha256:1dbe832a694971a925d7d216f49b700c95f402bd72288f9d37eceb1d59dcf72d
Deleted: sha256:2f4ee6a2e1b5dfb9236cd262e788f9d39109242ca27a4aacb583c8af66ec3ff7

