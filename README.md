# Set up K8s cluster environment for CKS on Vagrant with VirtualBox locally.

Setup Vagrant
- Download and install Vagrant & VirtualBox.

Uses ubuntu/focal64

```
vagrant init
vagrant up
```


Manager/primary/master Node:-
```
vagrant ssh master
```

```
sudo -i
bash <(curl -s https://raw.githubusercontent.com/A4ANK/cks/master/master.sh)
```

Secondary/worker Node:-
```
vagrant ssh worker
```

```
sudo -i
bash <(curl -s https://raw.githubusercontent.com/A4ANK/cks/master/worker.sh)
```

## References:-
- https://kubernetes.io/docs/home/
- https://github.com/killer-sh/cks-course-environment/
