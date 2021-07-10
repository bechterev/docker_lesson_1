root@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:/home/vitalii/Документы/docker# docker pull busybox
Using default tag: latest
latest: Pulling from library/busybox
b71f96345d44: Pull complete 
Digest: sha256:930490f97e5b921535c153e0e7110d251134cc4b72bbb8133c6a5065cc68580d
Status: Downloaded newer image for busybox:latest
docker.io/library/busybox:latest
root@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:/home/vitalii/Документы/docker# docker run  --name pinger busybox ping -c 7 netology.ru
PING netology.ru (172.67.43.83): 56 data bytes
64 bytes from 172.67.43.83: seq=0 ttl=54 time=26.219 ms
64 bytes from 172.67.43.83: seq=1 ttl=54 time=26.485 ms
64 bytes from 172.67.43.83: seq=2 ttl=54 time=27.326 ms
64 bytes from 172.67.43.83: seq=3 ttl=54 time=26.122 ms
64 bytes from 172.67.43.83: seq=4 ttl=54 time=25.795 ms
64 bytes from 172.67.43.83: seq=5 ttl=54 time=34.918 ms
64 bytes from 172.67.43.83: seq=6 ttl=54 time=100.440 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 25.795/38.186/100.440 ms
root@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:/home/vitalii/Документы/docker# docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                      PORTS     NAMES
eebafcc62ad4   busybox   "ping -c 7 netology.…"   17 seconds ago   Exited (0) 11 seconds ago             pinger
root@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:/home/vitalii/Документы/docker# docker logs pinger
PING netology.ru (172.67.43.83): 56 data bytes
64 bytes from 172.67.43.83: seq=0 ttl=54 time=26.219 ms
64 bytes from 172.67.43.83: seq=1 ttl=54 time=26.485 ms
64 bytes from 172.67.43.83: seq=2 ttl=54 time=27.326 ms
64 bytes from 172.67.43.83: seq=3 ttl=54 time=26.122 ms
64 bytes from 172.67.43.83: seq=4 ttl=54 time=25.795 ms
64 bytes from 172.67.43.83: seq=5 ttl=54 time=34.918 ms
64 bytes from 172.67.43.83: seq=6 ttl=54 time=100.440 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 25.795/38.186/100.440 ms
root@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:/home/vitalii/Документы/docker# docker start pinger
pinger
root@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:/home/vitalii/Документы/docker# docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                      PORTS     NAMES
eebafcc62ad4   busybox   "ping -c 7 netology.…"   About a minute ago   Exited (0) 53 seconds ago             pinger
root@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:/home/vitalii/Документы/docker# docker logs pinger
PING netology.ru (172.67.43.83): 56 data bytes
64 bytes from 172.67.43.83: seq=0 ttl=54 time=26.219 ms
64 bytes from 172.67.43.83: seq=1 ttl=54 time=26.485 ms
64 bytes from 172.67.43.83: seq=2 ttl=54 time=27.326 ms
64 bytes from 172.67.43.83: seq=3 ttl=54 time=26.122 ms
64 bytes from 172.67.43.83: seq=4 ttl=54 time=25.795 ms
64 bytes from 172.67.43.83: seq=5 ttl=54 time=34.918 ms
64 bytes from 172.67.43.83: seq=6 ttl=54 time=100.440 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 25.795/38.186/100.440 ms
PING netology.ru (172.67.43.83): 56 data bytes
64 bytes from 172.67.43.83: seq=0 ttl=54 time=22.839 ms
64 bytes from 172.67.43.83: seq=1 ttl=54 time=22.578 ms
64 bytes from 172.67.43.83: seq=2 ttl=54 time=63.152 ms
64 bytes from 172.67.43.83: seq=3 ttl=54 time=186.226 ms
64 bytes from 172.67.43.83: seq=4 ttl=54 time=92.541 ms
64 bytes from 172.67.43.83: seq=5 ttl=54 time=120.928 ms
64 bytes from 172.67.43.83: seq=6 ttl=54 time=150.041 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 22.578/94.043/186.226 ms
root@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:/home/vitalii/Документы/docker# docker rm  pinger
pinger
root@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:/home/vitalii/Документы/docker# docker rmi busybox
Untagged: busybox:latest
Untagged: busybox@sha256:930490f97e5b921535c153e0e7110d251134cc4b72bbb8133c6a5065cc68580d
Deleted: sha256:69593048aa3acfee0f75f20b77acb549de2472063053f6730c4091b53f2dfb02
Deleted: sha256:5b8c72934dfc08c7d2bd707e93197550f06c0751023dabb3a045b723c5e7b373
root@vitalii-VivoBook-ASUSLaptop-X570DD-M570DD:/home/vitalii/Документы/docker#
