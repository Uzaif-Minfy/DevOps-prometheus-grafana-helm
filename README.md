# DevOps-prometheus-grafana-helm

```
Minfy@DESKTOP-LM682CJ MINGW64 ~/Downloads (master)
$ ssh -i prometheus-grafana-uzaif.pem ubuntu@13.203.215.225
The authenticity of host '13.203.215.225 (13.203.215.225)' can't be established.
ED25519 key fingerprint is SHA256:rf+eXMMQAsDK+NXAZydVifGct4Qf2XoziHD/Gx3t8ZQ.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '13.203.215.225' (ED25519) to the list of known hosts.
Welcome to Ubuntu 24.04.2 LTS (GNU/Linux 6.8.0-1029-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Wed Jul  2 07:18:07 UTC 2025

  System load:  0.02               Processes:             117
  Usage of /:   12.6% of 13.49GB   Users logged in:       0
  Memory usage: 6%                 IPv4 address for enX0: 172.31.4.180
  Swap usage:   0%

Expanded Security Maintenance for Applications is not enabled.

0 updates can be applied immediately.

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


The list of available updates is more than a week old.
To check for new updates run: sudo apt update


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

ubuntu@ip-172-31-4-180:~$ sudo apt get update
E: Invalid operation get
ubuntu@ip-172-31-4-180:~$ sudo apt-get update
Hit:1 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble InRelease
Get:2 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates InRelease [126 kB]
Get:3 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports InRelease [126 kB]
Get:4 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 Packages [15.0 MB]
Get:5 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe Translation-en [5982 kB]
Get:6 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 Components [3871 kB]
Get:7 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 c-n-f Metadata [301 kB]
Get:8 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/multiverse amd64 Packages [269 kB]
Get:9 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/multiverse Translation-en [118 kB]
Get:10 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/multiverse amd64 Components [35.0 kB]
Get:11 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/multiverse amd64 c-n-f Metadata [8328 B]
Get:12 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/main amd64 Packages [1207 kB]
Get:13 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/main Translation-en [250 kB]
Get:14 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/main amd64 Components [161 kB]
Get:15 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/universe amd64 Packages [1098 kB]
Get:16 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/universe Translation-en [279 kB]
Get:17 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/universe amd64 Components [376 kB]
Get:18 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/universe amd64 c-n-f Metadata [26.0 kB]
Get:19 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/restricted amd64 Packages [1367 kB]
Get:20 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/restricted Translation-en [294 kB]
Get:21 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/restricted amd64 Components [212 B]
Get:22 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 Packages [22.1 kB]
Get:23 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/multiverse Translation-en [4972 B]
Get:24 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 Components [940 B]
Get:25 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 c-n-f Metadata [592 B]
Get:26 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/main amd64 Packages [39.2 kB]
Get:27 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/main Translation-en [8676 B]
Get:28 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/main amd64 Components [7080 B]
Get:29 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/main amd64 c-n-f Metadata [272 B]
Get:30 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/universe amd64 Packages [27.1 kB]
Get:31 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/universe Translation-en [16.5 kB]
Get:32 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/universe amd64 Components [16.4 kB]
Get:33 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/universe amd64 c-n-f Metadata [1304 B]
Get:34 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/restricted amd64 Components [216 B]
Get:35 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/restricted amd64 c-n-f Metadata [116 B]
Get:36 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/multiverse amd64 Components [212 B]
Get:37 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-backports/multiverse amd64 c-n-f Metadata [116 B]
Get:38 http://security.ubuntu.com/ubuntu noble-security InRelease [126 kB]
Get:39 http://security.ubuntu.com/ubuntu noble-security/main amd64 Packages [958 kB]
Get:40 http://security.ubuntu.com/ubuntu noble-security/main Translation-en [172 kB]
Get:41 http://security.ubuntu.com/ubuntu noble-security/main amd64 Components [21.5 kB]
Get:42 http://security.ubuntu.com/ubuntu noble-security/universe amd64 Packages [865 kB]
Get:43 http://security.ubuntu.com/ubuntu noble-security/universe Translation-en [189 kB]
Get:44 http://security.ubuntu.com/ubuntu noble-security/universe amd64 Components [52.2 kB]
Get:45 http://security.ubuntu.com/ubuntu noble-security/universe amd64 c-n-f Metadata [17.0 kB]
Get:46 http://security.ubuntu.com/ubuntu noble-security/restricted amd64 Packages [1322 kB]
Get:47 http://security.ubuntu.com/ubuntu noble-security/restricted Translation-en [285 kB]
Get:48 http://security.ubuntu.com/ubuntu noble-security/restricted amd64 Components [208 B]
Get:49 http://security.ubuntu.com/ubuntu noble-security/multiverse amd64 Packages [17.7 kB]
Get:50 http://security.ubuntu.com/ubuntu noble-security/multiverse Translation-en [3792 B]
Get:51 http://security.ubuntu.com/ubuntu noble-security/multiverse amd64 Components [208 B]
Get:52 http://security.ubuntu.com/ubuntu noble-security/multiverse amd64 c-n-f Metadata [380 B]
Fetched 35.1 MB in 31s (1125 kB/s)
Reading package lists... Done
ubuntu@ip-172-31-4-180:~$ sudo apt-get install -y docker.io
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  bridge-utils containerd dns-root-data dnsmasq-base pigz runc ubuntu-fan
Suggested packages:
  ifupdown aufs-tools cgroupfs-mount | cgroup-lite debootstrap docker-buildx
  docker-compose-v2 docker-doc rinse zfs-fuse | zfsutils
The following NEW packages will be installed:
  bridge-utils containerd dns-root-data dnsmasq-base docker.io pigz runc
  ubuntu-fan
0 upgraded, 8 newly installed, 0 to remove and 33 not upgraded.
Need to get 79.2 MB of archives.
After this operation, 300 MB of additional disk space will be used.
Get:1 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 pigz amd64 2.8-1 [65.6 kB]
Get:2 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/main amd64 bridge-utils amd64 1.7.1-1ubuntu2 [33.9 kB]
Get:3 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/main amd64 runc amd64 1.2.5-0ubuntu1~24.04.1 [8043 kB]
Get:4 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/main amd64 containerd amd64 1.7.27-0ubuntu1~24.04.1 [37.7 MB]
Get:5 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/main amd64 dns-root-data all 2024071801~ubuntu0.24.04.1 [5918 B]
Get:6 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/main amd64 dnsmasq-base amd64 2.90-2build2 [375 kB]
Get:7 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/universe amd64 docker.io amd64 27.5.1-0ubuntu3~24.04.2 [33.0 MB]
Get:8 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 ubuntu-fan all 0.12.16 [35.2 kB]
Fetched 79.2 MB in 1s (72.1 MB/s)
Preconfiguring packages ...
Selecting previously unselected package pigz.
(Reading database ... 70681 files and directories currently installed.)
Preparing to unpack .../0-pigz_2.8-1_amd64.deb ...
Unpacking pigz (2.8-1) ...
Selecting previously unselected package bridge-utils.
Preparing to unpack .../1-bridge-utils_1.7.1-1ubuntu2_amd64.deb ...
Unpacking bridge-utils (1.7.1-1ubuntu2) ...
Selecting previously unselected package runc.
Preparing to unpack .../2-runc_1.2.5-0ubuntu1~24.04.1_amd64.deb ...
Unpacking runc (1.2.5-0ubuntu1~24.04.1) ...
Selecting previously unselected package containerd.
Preparing to unpack .../3-containerd_1.7.27-0ubuntu1~24.04.1_amd64.deb ...
Unpacking containerd (1.7.27-0ubuntu1~24.04.1) ...
Selecting previously unselected package dns-root-data.
Preparing to unpack .../4-dns-root-data_2024071801~ubuntu0.24.04.1_all.deb ...
Unpacking dns-root-data (2024071801~ubuntu0.24.04.1) ...
Selecting previously unselected package dnsmasq-base.
Preparing to unpack .../5-dnsmasq-base_2.90-2build2_amd64.deb ...
Unpacking dnsmasq-base (2.90-2build2) ...
Selecting previously unselected package docker.io.
Preparing to unpack .../6-docker.io_27.5.1-0ubuntu3~24.04.2_amd64.deb ...
Unpacking docker.io (27.5.1-0ubuntu3~24.04.2) ...
Selecting previously unselected package ubuntu-fan.
Preparing to unpack .../7-ubuntu-fan_0.12.16_all.deb ...
Unpacking ubuntu-fan (0.12.16) ...
Setting up dnsmasq-base (2.90-2build2) ...
Setting up runc (1.2.5-0ubuntu1~24.04.1) ...
Setting up dns-root-data (2024071801~ubuntu0.24.04.1) ...
Setting up bridge-utils (1.7.1-1ubuntu2) ...
Setting up pigz (2.8-1) ...
Setting up containerd (1.7.27-0ubuntu1~24.04.1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /usr/lib/systemd/system/containerd.service.
Setting up ubuntu-fan (0.12.16) ...
Created symlink /etc/systemd/system/multi-user.target.wants/ubuntu-fan.service → /usr/lib/systemd/system/ubuntu-fan.service.
Setting up docker.io (27.5.1-0ubuntu3~24.04.2) ...
info: Selecting GID from range 100 to 999 ...
info: Adding group `docker' (GID 113) ...
Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /usr/lib/systemd/system/docker.service.
Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /usr/lib/systemd/system/docker.socket.
Processing triggers for dbus (1.14.10-4ubuntu4.1) ...
Processing triggers for man-db (2.12.0-4build2) ...
Scanning processes...
Scanning linux images...

Running kernel seems to be up-to-date.

No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
ubuntu@ip-172-31-4-180:~$ sudo usermod -aG docker ${USER}
ubuntu@ip-172-31-4-180:~$ newgrp docker
ubuntu@ip-172-31-4-180:~$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
ubuntu@ip-172-31-4-180:~$ git clone https://github.com/KiranPolaki/docker-voting-app
Cloning into 'docker-voting-app'...
remote: Enumerating objects: 88, done.
remote: Counting objects: 100% (88/88), done.
remote: Compressing objects: 100% (71/71), done.
remote: Total 88 (delta 14), reused 82 (delta 10), pack-reused 0 (from 0)
Receiving objects: 100% (88/88), 2.04 MiB | 7.43 MiB/s, done.
Resolving deltas: 100% (14/14), done.
ubuntu@ip-172-31-4-180:~$ ls
docker-voting-app
ubuntu@ip-172-31-4-180:~$ cd docker-voting-app
ubuntu@ip-172-31-4-180:~/docker-voting-app$ ls
LICENSE                      docker-compose.yml  kind-cluster
MAINTAINERS                  docker-stack.yml    result
README.md                    healthchecks        seed-data
architecture.excalidraw.png  image.png           vote
docker-compose.images.yml    k8s-specifications  worker
ubuntu@ip-172-31-4-180:~/docker-voting-app$ chmod +x kind-cluster/install-kind.sh
chmod: cannot access 'kind-cluster/install-kind.sh': No such file or directory
ubuntu@ip-172-31-4-180:~/docker-voting-app$ chmod +x kind-cluster/install-kind.sh
chmod: cannot access 'kind-cluster/install-kind.sh': No such file or directory
ubuntu@ip-172-31-4-180:~/docker-voting-app$ cd kind-kluster
bash: cd: kind-kluster: No such file or directory
ubuntu@ip-172-31-4-180:~/docker-voting-app$ cd kind-cluster
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ ls
commands.md  dashboard-adminuser.yml  install_kubectl.sh
config.yml   install_kind.sh
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ chmod +x install_kind.sh
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ chmod +x install_kubectl.sh
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ install_kind.sh
install_kind.sh: command not found
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ cd ..
ubuntu@ip-172-31-4-180:~/docker-voting-app$ ./kind-cluster/install-kind.sh
bash: ./kind-cluster/install-kind.sh: No such file or directory
ubuntu@ip-172-31-4-180:~/docker-voting-app$ ./kind-cluster/install_kind.sh
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    97  100    97    0     0    322      0 --:--:-- --:--:-- --:--:--   323
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100 6304k  100 6304k    0     0  3198k      0  0:00:01  0:00:01 --:--:-- 18.9M
ubuntu@ip-172-31-4-180:~/docker-voting-app$ ./kind-cluster/install_kubectl.sh
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   138  100   138    0     0    481      0 --:--:-- --:--:-- --:--:--   482
100 49.0M  100 49.0M    0     0  63.2M      0 --:--:-- --:--:-- --:--:--  116M
Client Version: v1.30.0
Kustomize Version: v5.0.4-0.20230601165947-6ce0bf390ce3
kubectl installation complete.
ubuntu@ip-172-31-4-180:~/docker-voting-app$ kubectl get nodes
E0702 07:32:18.616951    2365 memcache.go:265] couldn't get current server API group list: Get "http://localhost:8080/api?timeout=32s": dial tcp 127.0.0.1:8080: connect: connection refused
E0702 07:32:18.617128    2365 memcache.go:265] couldn't get current server API group list: Get "http://localhost:8080/api?timeout=32s": dial tcp 127.0.0.1:8080: connect: connection refused
E0702 07:32:18.618894    2365 memcache.go:265] couldn't get current server API group list: Get "http://localhost:8080/api?timeout=32s": dial tcp 127.0.0.1:8080: connect: connection refused
E0702 07:32:18.619173    2365 memcache.go:265] couldn't get current server API group list: Get "http://localhost:8080/api?timeout=32s": dial tcp 127.0.0.1:8080: connect: connection refused
E0702 07:32:18.620414    2365 memcache.go:265] couldn't get current server API group list: Get "http://localhost:8080/api?timeout=32s": dial tcp 127.0.0.1:8080: connect: connection refused
The connection to the server localhost:8080 was refused - did you specify the right host or port?
ubuntu@ip-172-31-4-180:~/docker-voting-app$ cd kind-cluster
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kind create cluster --config=config.yml --name=my-cluster
Creating cluster "my-cluster" ...
 ✓ Ensuring node image (kindest/node:v1.30.0) 🖼
 ✓ Preparing nodes 📦 📦 📦
 ✓ Writing configuration 📜
 ✓ Starting control-plane 🕹️
 ✓ Installing CNI 🔌
 ✓ Installing StorageClass 💾
 ✓ Joining worker nodes 🚜
Set kubectl context to "kind-my-cluster"
You can now use your cluster with:

kubectl cluster-info --context kind-my-cluster

Have a nice day! 👋
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl get nodes
NAME                       STATUS   ROLES           AGE   VERSION
my-cluster-control-plane   Ready    control-plane   65s   v1.30.0
my-cluster-worker          Ready    <none>          42s   v1.30.0
my-cluster-worker2         Ready    <none>          41s   v1.30.0
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl get all
NAME                 TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
service/kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP   4m12s
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ cd k8s-specifications/
bash: cd: k8s-specifications/: No such file or directory
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl apply -f .
clusterrolebinding.rbac.authorization.k8s.io/admin-user created
resource mapping not found for name: "" namespace: "" from "config.yml": no matches for kind "Cluster" in version "kind.x-k8s.io/v1alpha4"
ensure CRDs are installed first
Error from server (NotFound): error when creating "dashboard-adminuser.yml": namespaces "kubernetes-dashboard" not found
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ cd k8s_specifications/
bash: cd: k8s_specifications/: No such file or directory
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ ls
commands.md  dashboard-adminuser.yml  install_kubectl.sh
config.yml   install_kind.sh
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ cd ..
ubuntu@ip-172-31-4-180:~/docker-voting-app$ cd k8s_specifications/
bash: cd: k8s_specifications/: No such file or directory
ubuntu@ip-172-31-4-180:~/docker-voting-app$ cd k8s-specifications/
ubuntu@ip-172-31-4-180:~/docker-voting-app/k8s-specifications$ kubectl apply -f .
deployment.apps/db created
service/db created
deployment.apps/redis created
service/redis created
deployment.apps/result created
service/result created
deployment.apps/vote created
service/vote created
deployment.apps/worker created
ubuntu@ip-172-31-4-180:~/docker-voting-app/k8s-specifications$ kubectl get all
NAME                          READY   STATUS              RESTARTS   AGE
pod/db-597b4ff8d7-6kzq7       1/1     Running             0          13s
pod/redis-796dc594bb-k8r2c    1/1     Running             0          13s
pod/result-d8c4c69b8-j95mb    0/1     ContainerCreating   0          13s
pod/vote-69cb46f6fb-qqbtf     0/1     ContainerCreating   0          13s
pod/worker-5dd767667f-q2fk6   0/1     ContainerCreating   0          13s

NAME                 TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
service/db           ClusterIP   10.96.139.103   <none>        5432/TCP         13s
service/kubernetes   ClusterIP   10.96.0.1       <none>        443/TCP          11m
service/redis        ClusterIP   10.96.115.19    <none>        6379/TCP         13s
service/result       NodePort    10.96.236.114   <none>        5001:31001/TCP   13s
service/vote         NodePort    10.96.177.227   <none>        5000:31002/TCP   13s

NAME                     READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/db       1/1     1            1           13s
deployment.apps/redis    1/1     1            1           13s
deployment.apps/result   0/1     1            0           13s
deployment.apps/vote     0/1     1            0           13s
deployment.apps/worker   0/1     1            0           13s

NAME                                DESIRED   CURRENT   READY   AGE
replicaset.apps/db-597b4ff8d7       1         1         1       13s
replicaset.apps/redis-796dc594bb    1         1         1       13s
replicaset.apps/result-d8c4c69b8    1         1         0       13s
replicaset.apps/vote-69cb46f6fb     1         1         0       13s
replicaset.apps/worker-5dd767667f   1         1         0       13s
ubuntu@ip-172-31-4-180:~/docker-voting-app/k8s-specifications$ kubectl get all
NAME                          READY   STATUS    RESTARTS   AGE
pod/db-597b4ff8d7-6kzq7       1/1     Running   0          41s
pod/redis-796dc594bb-k8r2c    1/1     Running   0          41s
pod/result-d8c4c69b8-j95mb    1/1     Running   0          41s
pod/vote-69cb46f6fb-qqbtf     1/1     Running   0          41s
pod/worker-5dd767667f-q2fk6   1/1     Running   0          41s

NAME                 TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
service/db           ClusterIP   10.96.139.103   <none>        5432/TCP         41s
service/kubernetes   ClusterIP   10.96.0.1       <none>        443/TCP          12m
service/redis        ClusterIP   10.96.115.19    <none>        6379/TCP         41s
service/result       NodePort    10.96.236.114   <none>        5001:31001/TCP   41s
service/vote         NodePort    10.96.177.227   <none>        5000:31002/TCP   41s

NAME                     READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/db       1/1     1            1           41s
deployment.apps/redis    1/1     1            1           41s
deployment.apps/result   1/1     1            1           41s
deployment.apps/vote     1/1     1            1           41s
deployment.apps/worker   1/1     1            1           41s

NAME                                DESIRED   CURRENT   READY   AGE
replicaset.apps/db-597b4ff8d7       1         1         1       41s
replicaset.apps/redis-796dc594bb    1         1         1       41s
replicaset.apps/result-d8c4c69b8    1         1         1       41s
replicaset.apps/vote-69cb46f6fb     1         1         1       41s
replicaset.apps/worker-5dd767667f   1         1         1       41s
ubuntu@ip-172-31-4-180:~/docker-voting-app/k8s-specifications$ kubectl get all
NAME                          READY   STATUS    RESTARTS   AGE
pod/db-597b4ff8d7-6kzq7       1/1     Running   0          45s
pod/redis-796dc594bb-k8r2c    1/1     Running   0          45s
pod/result-d8c4c69b8-j95mb    1/1     Running   0          45s
pod/vote-69cb46f6fb-qqbtf     1/1     Running   0          45s
pod/worker-5dd767667f-q2fk6   1/1     Running   0          45s

NAME                 TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
service/db           ClusterIP   10.96.139.103   <none>        5432/TCP         45s
service/kubernetes   ClusterIP   10.96.0.1       <none>        443/TCP          12m
service/redis        ClusterIP   10.96.115.19    <none>        6379/TCP         45s
service/result       NodePort    10.96.236.114   <none>        5001:31001/TCP   45s
service/vote         NodePort    10.96.177.227   <none>        5000:31002/TCP   45s

NAME                     READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/db       1/1     1            1           45s
deployment.apps/redis    1/1     1            1           45s
deployment.apps/result   1/1     1            1           45s
deployment.apps/vote     1/1     1            1           45s
deployment.apps/worker   1/1     1            1           45s

NAME                                DESIRED   CURRENT   READY   AGE
replicaset.apps/db-597b4ff8d7       1         1         1       45s
replicaset.apps/redis-796dc594bb    1         1         1       45s
replicaset.apps/result-d8c4c69b8    1         1         1       45s
replicaset.apps/vote-69cb46f6fb     1         1         1       45s
replicaset.apps/worker-5dd767667f   1         1         1       45s
ubuntu@ip-172-31-4-180:~/docker-voting-app/k8s-specifications$ cd ../kind-cluster/
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ chmod 700 get_helm.sh
./get_helm.sh
Downloading https://get.helm.sh/helm-v3.18.3-linux-amd64.tar.gz
Verifying checksum... Done.
Preparing to install helm into /usr/local/bin
helm installed into /usr/local/bin/helm
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm version
version.BuildInfo{Version:"v3.18.3", GitCommit:"6838ebcf265a3842d1433956e8a622e3290cf324", GitTreeState:"clean", GoVersion:"go1.24.4"}
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
"prometheus-community" has been added to your repositories
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm repo add stable https://charts.helm.sh/stable
"stable" has been added to your repositories
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm repo list
NAME                    URL
prometheus-community    https://prometheus-community.github.io/helm-charts
stable                  https://charts.helm.sh/stable
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm repo update
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "prometheus-community" chart repository
...Successfully got an update from the "stable" chart repository
Update Complete. ⎈Happy Helming!⎈
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl create namespace monitoring
namespace/monitoring created
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm install kind-prometheus prometheus-community/kube-prometheus-stack --namespace monitoring --set prometheus.service.type=NodePort --set prometheus.service.nodePort=30000 --set grafana.service.type=NodePort --set grafana.service.nodePort=31000 --set alertmanager.service.type=NodePort --set alertmanager.service.nodePort=32000
NAME: kind-prometheus
LAST DEPLOYED: Wed Jul  2 07:51:42 2025
NAMESPACE: monitoring
STATUS: deployed
REVISION: 1
NOTES:
kube-prometheus-stack has been installed. Check its status by running:
  kubectl --namespace monitoring get pods -l "release=kind-prometheus"

Get Grafana 'admin' user password by running:

  kubectl --namespace monitoring get secrets kind-prometheus-grafana -o jsonpath="{.data.admin-password}" | base64 -d ; echo

Access Grafana local instance:

  export POD_NAME=$(kubectl --namespace monitoring get pod -l "app.kubernetes.io/name=grafana,app.kubernetes.io/instance=kind-prometheus" -oname)
  kubectl --namespace monitoring port-forward $POD_NAME 3000

Visit https://github.com/prometheus-operator/kube-prometheus for instructions on how to create & configure Alertmanager and Prometheus instances using the Operator.
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl get pods -n monitoring
NAME                                                     READY   STATUS    RESTARTS   AGE
alertmanager-kind-prometheus-kube-prome-alertmanager-0   2/2     Running   0          30s
kind-prometheus-grafana-7565dc9bdf-ph8j8                 3/3     Running   0          42s
kind-prometheus-kube-prome-operator-df978f4df-smqz2      1/1     Running   0          42s
kind-prometheus-kube-state-metrics-698d8db8c5-h496q      1/1     Running   0          42s
kind-prometheus-prometheus-node-exporter-9tqv9           1/1     Running   0          42s
kind-prometheus-prometheus-node-exporter-lnpm8           1/1     Running   0          42s
kind-prometheus-prometheus-node-exporter-srvcp           1/1     Running   0          42s
prometheus-kind-prometheus-kube-prome-prometheus-0       1/2     Running   0          29s
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl create namespace monitoring-uzaif
namespace/monitoring-uzaif created
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm install kind-prometheus prometheus-community/kube-prometheus-stack --namespace monitoring --set prometheus.service.type=NodePort --set prometheus.service.nodePort=30000 --set grafana.service.type=NodePort --set grafana.service.nodePort=31000 --set alertmanager.service.type=NodePort --set alertmanager.service.nodePort=32000
Error: INSTALLATION FAILED: cannot re-use a name that is still in use
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm install kind-prometheus prometheus-community/kube-prometheus-stack --namespace monitoring-uzaif --set prometheus.service.type=NodePort --set prometheus.service.nodePort=30000 --set grafana.service.type=NodePort --set grafana.service.nodePort=31000 --set alertmanager.service.type=NodePort --set alertmanager.service.nodePort=32000
Error: INSTALLATION FAILED: Unable to continue with install: ClusterRole "kind-prometheus-grafana-clusterrole" in namespace "" exists and cannot be imported into the current release: invalid ownership metadata; annotation validation error: key "meta.helm.sh/release-namespace" must equal "monitoring-uzaif": current value is "monitoring"
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl delete namespace monitoring
namespace "monitoring" deleted
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl get namespace
NAME                 STATUS   AGE
default              Active   25m
kube-node-lease      Active   25m
kube-public          Active   25m
kube-system          Active   25m
local-path-storage   Active   25m
monitoring-uzaif     Active   3m42s
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm install kind-prometheus prometheus-community/kube-prometheus-stack --namespace monitoring-uzaif --set prometheus.service.type=NodePort --set prometheus.service.nodePort=30000 --set grafana.service.type=NodePort --set grafana.service.nodePort=31000 --set alertmanager.service.type=NodePort --set alertmanager.service.nodePort=32000
Error: INSTALLATION FAILED: Unable to continue with install: ClusterRole "kind-prometheus-grafana-clusterrole" in namespace "" exists and cannot be imported into the current release: invalid ownership metadata; annotation validation error: key "meta.helm.sh/release-namespace" must equal "monitoring-uzaif": current value is "monitoring"
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ ^C
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl create namespace monitoring-uzaif
Error from server (AlreadyExists): namespaces "monitoring-uzaif" already exists
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm install kind-prometheus prometheus-community/kube-prometheus-stack \
  --namespace monitoring-uzaif \
  --set prometheus.service.type=NodePort \
  --set prometheus.service.nodePort=30000 \
  --set grafana.service.type=NodePort \
  --set grafana.service.nodePort=31000 \
  --set alertmanager.service.type=NodePort \
  --set alertmanager.service.nodePort=32000
Error: INSTALLATION FAILED: Unable to continue with install: ClusterRole "kind-prometheus-grafana-clusterrole" in namespace "" exists and cannot be imported into the current release: invalid ownership metadata; annotation validation error: key "meta.helm.sh/release-namespace" must equal "monitoring-uzaif": current value is "monitoring"
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ ^C
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl annotate clusterrole kind-prometheus-grafana-clusterrole \
  meta.helm.sh/release-name- \
  meta.helm.sh/release-namespace-
clusterrole.rbac.authorization.k8s.io/kind-prometheus-grafana-clusterrole annotated
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm install kind-prometheus prometheus-community/kube-prometheus-stack \                                --namespace monitoring-uzaif \
  --create-namespace \
  --set prometheus.service.type=NodePort \
  --set prometheus.service.nodePort=30000 \
  --set grafana.service.type=NodePort \
  --set grafana.service.nodePort=31000 \
  --set alertmanager.service.type=NodePort \
  --set alertmanager.service.nodePort=32000
Error: INSTALLATION FAILED: Unable to continue with install: ClusterRole "kind-prometheus-grafana-clusterrole" in namespace "" exists and cannot be imported into the current release: invalid ownership metadata; annotation validation error: missing key "meta.helm.sh/release-name": must be set to "kind-prometheus"; annotation validation error: missing key "meta.helm.sh/release-namespace": must be set to "monitoring-uzaif"
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ ^C
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl annotate clusterrole kind-prometheus-grafana-clusterrole \
  meta.helm.sh/release-name=kind-prometheus \
  meta.helm.sh/release-namespace=monitoring-uzaif \
  --overwrite
clusterrole.rbac.authorization.k8s.io/kind-prometheus-grafana-clusterrole annotated
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm install kind-prometheus prometheus-community/kube-prometheus-stack \
  --namespace monitoring-uzaif \
  --set prometheus.service.type=NodePort \
  --set prometheus.service.nodePort=30000 \
  --set grafana.service.type=NodePort \
  --set grafana.service.nodePort=31000 \
  --set alertmanager.service.type=NodePort \
  --set alertmanager.service.nodePort=32000
Error: INSTALLATION FAILED: Unable to continue with install: ClusterRole "kind-prometheus-kube-state-metrics" in namespace "" exists and cannot be imported into the current release: invalid ownership metadata; annotation validation error: key "meta.helm.sh/release-namespace" must equal "monitoring-uzaif": current value is "monitoring"
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ ^C
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl annotate clusterrole kind-prometheus-kube-state-metrics \
  meta.helm.sh/release-name=kind-prometheus \
  meta.helm.sh/release-namespace=monitoring-uzaif \
  --overwrite
clusterrole.rbac.authorization.k8s.io/kind-prometheus-kube-state-metrics annotated
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl get clusterroles -o=jsonpath="{range .items[*]}{.metadata.name}{'\t'}{.metadata.annotations['meta.helm.sh/release-namespace']}{'\n'}{end}" | grep monitoring
system:monitoring
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm uninstall kind-prometheus --namespace monitoring
Error: uninstall: Release not loaded: kind-prometheus: release: not found
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl get clusterroles | grep kind-prometheus
kubectl get clusterrolebindings | grep kind-prometheus
kind-prometheus-grafana-clusterrole                                    2025-07-02T07:51:55Z
kind-prometheus-kube-prome-operator                                    2025-07-02T07:51:55Z
kind-prometheus-kube-prome-prometheus                                  2025-07-02T07:51:55Z
kind-prometheus-kube-state-metrics                                     2025-07-02T07:51:55Z
kind-prometheus-grafana-clusterrolebinding                      ClusterRole/kind-prometheus-grafana-clusterrole                                    17m
kind-prometheus-kube-prome-operator                             ClusterRole/kind-prometheus-kube-prome-operator                                    17m
kind-prometheus-kube-prome-prometheus                           ClusterRole/kind-prometheus-kube-prome-prometheus                                  17m
kind-prometheus-kube-state-metrics                              ClusterRole/kind-prometheus-kube-state-metrics                                     17m
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl delete clusterrole kind-prometheus-grafana-clusterrole
kubectl delete clusterrole kind-prometheus-kube-state-metrics
kubectl delete clusterrolebinding kind-prometheus-kube-state-metrics
clusterrole.rbac.authorization.k8s.io "kind-prometheus-grafana-clusterrole" deleted
clusterrole.rbac.authorization.k8s.io "kind-prometheus-kube-state-metrics" deleted
clusterrolebinding.rbac.authorization.k8s.io "kind-prometheus-kube-state-metrics" deleted
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm install kind-prometheus prometheus-community/kube-prometheus-stack \
  --namespace monitoring-uzaif \
  --set prometheus.service.type=NodePort \
  --set prometheus.service.nodePort=30000 \
  --set grafana.service.type=NodePort \
  --set grafana.service.nodePort=31000 \
  --set alertmanager.service.type=NodePort \
  --set alertmanager.service.nodePort=32000
Error: INSTALLATION FAILED: Unable to continue with install: ClusterRole "kind-prometheus-kube-prome-operator" in namespace "" exists and cannot be imported into the current release: invalid ownership metadata; annotation validation error: key "meta.helm.sh/release-namespace" must equal "monitoring-uzaif": current value is "monitoring"
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ ^C
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
Helm v3.18.3 is already latest
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
"prometheus-community" already exists with the same configuration, skipping
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm repo list
NAME                    URL
prometheus-community    https://prometheus-community.github.io/helm-charts
stable                  https://charts.helm.sh/stable
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl get namaspaces
error: the server doesn't have a resource type "namaspaces"
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl get namespaces
NAME                 STATUS   AGE
default              Active   40m
kube-node-lease      Active   40m
kube-public          Active   40m
kube-system          Active   40m
local-path-storage   Active   40m
monitoring-uzaif     Active   19m
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ helm install kind-prometheus prometheus-community/kube-prometheus-stack --namespace monitoring-uzaif --set prometheus.service.type=NodePort --set prometheus.service.nodePort=30000 --set grafana.service.type=NodePort --set grafana.service.nodePort=31000 --set alertmanager.service.type=NodePort --set alertmanager.service.nodePort=32000
Error: INSTALLATION FAILED: Unable to continue with install: ClusterRole "kind-prometheus-kube-prome-operator" in namespace "" exists and cannot be imported into the current release: invalid ownership metadata; annotation validation error: key "meta.helm.sh/release-namespace" must equal "monitoring-uzaif": current value is "monitoring"
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl get pods -n monitoring
No resources found in monitoring namespace.
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$ kubectl get pods -n monitoring-uzaif
No resources found in monitoring-uzaif namespace.
ubuntu@ip-172-31-4-180:~/docker-voting-app/kind-cluster$
```
