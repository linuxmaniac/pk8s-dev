Prereq
======
download and install omnictl and omniconfig from omni


Create MachineClasses
=====================
```bash
omnictl apply -f pk8s-dev.yaml
```

Create cluster
==============
```bash
omnictl cluster template sync --file cluster-pk8s-dev.yaml
```

### age config
```bash
cat ~/.config/sops/age/keys.txt | kubectl --context admin@sipwork create secret generic sops-age \
  --namespace=argocd \
  --from-file=age.agekey=/dev/stdin
```
