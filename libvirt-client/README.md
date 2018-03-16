# Libvirt Client

Execute virsh commands on hypervisors like QEMU, KVM, or Xen of remote machine.

Build docker image by

```sh
$ docker build -t libvirt_client:v1 . 
```
Run docker image 

## Display remote virtual machines

```sh
$ docker container run libvirt_client:v1 qemu+ssh://<username>@<remote_ip>/system list
```
## Start a virtual machine

```sh
$ docker container run libvirt_client:v1 qemu+ssh://<username>@<remote_ip>/system start <domain_name>
```

## Shutdown a virtual machine

```sh
$ docker container run libvirt_client:v1 qemu+ssh://<username>@<remote_ip>/system shutdown <domain_name>
```
> SSH service should be running on the remote machine
