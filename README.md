![CI](https://github.com/VamsiKP-Dev/k8s-vlc-orchestration-lab/actions/workflows/ci.yaml/badge.svg)

# VLC Player Kubernetes Deployment Project

This project demonstrates a comprehensive Kubernetes deployment of a VLC Player application across three progressive phases:

# 📘 Kubernetes VLC Orchestration Lab

### *A Multi-Phase Kubernetes Learning Project (DaemonSet → StatefulSet → Operators)*

![GitHub CI](https://img.shields.io/badge/GitHub%20Actions-Pipeline-blue)

## 🚀 Overview

This project is a **3-phase Kubernetes Lab** that simulates orchestration of a media-processing workload (VLC-style) using:

| Phase       | Kubernetes Component         | Purpose                    |
| ----------- | ---------------------------- | -------------------------- |
| **Phase 1** | DaemonSet                    | Run an agent on every node |
| **Phase 2** | StatefulSet (with HPA + VPA) | Scale stateful workloads   |
| **Phase 3** | Custom Operators + CRDs      | Extend Kubernetes API      |

💡 **IMPORTANT:** VLC cannot fully run inside containers.
This project focuses on **Kubernetes concepts**, not real VLC playback.

---

# 🧱 Project Structure Diagram

```
k8s-vlc-orchestration-lab/
│
├── docker/
│   ├── config/
│   ├── media/
│   ├── playlists/
│   ├── scripts/
│   ├── Dockerfile
│   ├── docker-compose.yml
│
├── monitoring/
│   └── prometheus/
│
├── phase1-daemonset/
│   ├── configmap.yaml
│   ├── daemonset.yaml
│   ├── secret.yaml
│   ├── service.yaml
│   └── deploy.sh
│
├── phase2-statefulset/
│   ├── statefulset.yaml
│   ├── service.yaml
│   ├── hpa.yaml
│   ├── vpa.yaml
│   └── deploy.sh
│
├── phase3-operators/
│   ├── crds/
│   ├── operator/
│   ├── examples/
│   ├── rbac/
│   └── deploy.sh
│
├── PROJECT_OVERVIEW.md
└── README.md
```

---

# 🧪 Phase 1 — DaemonSet

Deploys a VLC-agent placeholder on every node.

### Deploy:

```sh
kubectl apply -f phase1-daemonset/
```

Check Pods:

```sh
kubectl get pods -o wide -l app=vlc-player
```

---

# 📦 Phase 2 — StatefulSet

A distributed media-worker cluster with:

* Stable network identity
* Persistent storage
* Auto-scaling via **HPA** and **VPA**

Deploy:

```sh
kubectl apply -f phase2-statefulset/
```

---

# 🧬 Phase 3 — Kubernetes Operator

Implements two CRDs:

* **VLCPlayer**
* **VLCPlaylist**

The operator watches these CRDs and performs reconciliation.

Deploy:

```sh
kubectl apply -f phase3-operators/
```

Apply CR example:

```sh
kubectl apply -f phase3-operators/examples/vlcplayer-examples.yaml
```

# 🤝 Contributions

PRs welcome. Fork the repo → Make changes → Submit PR.

---

# ⭐ If you like this project

Give the repository a **Star** ⭐ on GitHub!

---
