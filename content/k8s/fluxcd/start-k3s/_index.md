---
content_type: project
flavours:
- none
from_repo: k8s/manual-app-deployment/project-overview
prerequisites:
  hard:
  - k8s/manual-app-deployment/project-overview
  soft:
  - k8s/fluxcd/setup-postgresql-backend
ready: true
submission_type: continue_repo
tags:
- kubernetes
- fluxcd
title: Start k3s

---

#  Start k3s

This time around we are starting the k3s cluster without trafik and using the postgres that is running locally, in production likely your postgresdb will be outisde of the cluster and maintained seperately

```
sudo curl -sfL https://get.k3s.io | INSTALL_K3S_EXEC="server --disable=traefik --datastore-endpoint=postgres://k3s:yourpassword@localhost:5432/kubernetes" sh -
```