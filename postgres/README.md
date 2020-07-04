# Example deploy postgresql for bare-metal kubernetes cluster

Requirements:
  - docker kubeadm kubelet kubectl are already install on your bare-metal machine 
  - Recommended for dev and staging environment. **Not recommended to prod!**

1. Change hostpath if required in PersistentVolume
2. Run command: ```kubectl apply -f .```

**Ready!** postgres available inside your cluster postgres:5432
