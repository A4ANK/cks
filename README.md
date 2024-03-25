# Set up K8s cluster environment for CKS on Vagrant with VirtualBox locally.

### Setup Vagrant
- Download and install Vagrant & VirtualBox.

Uses ubuntu/focal64 (Ubuntu - 20.04 LTS)

```
vagrant init
vagrant up
```


### Manager/Primary/Control-Plane Node:-
```
vagrant ssh master
```

```
sudo -i
bash <(curl -s https://raw.githubusercontent.com/A4ANK/cks/master/control-plane.sh)
```
- After complete setup up of master and worker nodes. We can label worker node also.
```
kubectl label node worker node-role.kubernetes.io/worker=worker
```

### Secondary/worker Node:-
```
vagrant ssh worker
```

```
sudo -i
bash <(curl -s https://raw.githubusercontent.com/A4ANK/cks/master/worker.sh)
```

### Vagrant stop VMs

```
vagrant halt
```
### Vagrant Destroy VMs
```
vagrant destroy
```

## References:-
- https://kubernetes.io/docs/home/
- https://github.com/killer-sh/cks-course-environment/
