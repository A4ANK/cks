# Set up a local K8s cluster environment on Vagrant with VirtualBox driver.

### Setup Vagrant
- Download and install Vagrant & VirtualBox.

Uses ubuntu/focal64 (Ubuntu - 20.04 LTS)

```
vagrant init
vagrant up
```


### Manager/Primary/ControlPlane Node:-
```
vagrant ssh controlplane
```

```
sudo -i
bash <(curl -s https://raw.githubusercontent.com/A4ANK/k8s/main/controlplane.sh)
```
- After complete setup up of controlplane and worker nodes. We can label worker node also.
```
kubectl label node worker node-role.kubernetes.io/worker=worker
```

### Secondary/worker Node:-
```
vagrant ssh worker
```

```
sudo -i
bash <(curl -s https://raw.githubusercontent.com/A4ANK/k8s/main/worker.sh)
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
