
---

<div align="center">

# **Kubernetes VLC Orchestration Lab**

### *A Multi-Phase Learning Project for DaemonSets, StatefulSets & Kubernetes Operators*

<img src="https://raw.githubusercontent.com/VamsiKP-Dev/k8s-vlc-orchestration-lab/main/.assets/project-banner.png" width="80%" />

</div>

---

## 📌 **Project Overview**

This repository contains a **3-phase Kubernetes hands-on lab** built around a *mock media-streaming service* using VLC-like workloads.
It focuses on **Kubernetes concepts**, not on running actual VLC playback inside containers.

✔ Demonstrates **DaemonSets**
✔ Demonstrates **StatefulSets with autoscaling (HPA/VPA)**
✔ Demonstrates **Custom Resource Definitions (CRDs)**
✔ Demonstrates **Operator pattern**
✔ Includes **Docker**, **Config**, **Secrets**, **Monitoring (Prometheus)**
✔ Includes **Deployment automation scripts**

---

## 📁 **Repository Structure Diagram**

```
k8s-vlc-orchestration-lab
│
├── docker/
│   ├── config/
│   ├── media/
│   ├── playlists/
│   ├── scripts/
│   ├── Dockerfile
│   ├── Dockerfile.windows
│   └── docker-compose.yml
│
├── monitoring/
│   └── prometheus/
│
├── phase1-daemonset/
│   ├── daemonset.yaml
│   ├── configmap.yaml
│   ├── secret.yaml
│   ├── service.yaml
│   └── deploy.sh
│
├── phase2-statefulset/
│   ├── statefulset.yaml
│   ├── configmap.yaml
│   ├── hpa.yaml
│   ├── vpa.yaml
│   ├── service.yaml
│   └── deploy.sh
│
├── phase3-operators/
│   ├── crds/
│   ├── operator/
│   ├── rbac/
│   ├── examples/
│   └── deploy.sh
│
├── PROJECT_OVERVIEW.md
├── README.md
└── deploy.sh
```

---

# 🌐 **Phase Breakdown**

---

## **🔵 Phase 1 — Kubernetes DaemonSet**

A mock VLC agent is deployed across all nodes using a **DaemonSet**.

**Key Learnings:**

* DaemonSet scheduling behavior
* ConfigMap + Secret injection
* Cluster-wide logging agent pattern
* Node-level workloads

> ⚠ VLC GUI cannot run inside Kubernetes containers.
> This phase simulates *node-level agents*, which is valid and real-world.

---

## **🟢 Phase 2 — Kubernetes StatefulSet + Autoscaling**

Implements a simulated media metadata service using **StatefulSet**.

**Features:**

* Persistent hostname & numbering
* HorizonalPodAutoscaler (HPA)
* VerticalPodAutoscaler (VPA)
* Service stable network identity

This teaches **scaling + identity** concepts.

---

## **🟣 Phase 3 — Kubernetes Operator & CRDs**

Implements a Kubernetes Operator using:

* Custom Resource Definitions (CRDs)
* RBAC
* Operator Deployment
* Example CRD instances

You learn:
✔ Custom API design
✔ Controller/operator deployment
✔ Managing VLC-like workloads using custom resources

---

# 🏗 **How to Deploy**

### **Clone Repository**

```sh
git clone https://github.com/VamsiKP-Dev/k8s-vlc-orchestration-lab.git
cd k8s-vlc-orchestration-lab
```

### **Deploy Phase 1**

```sh
cd phase1-daemonset
./deploy.sh
```

### **Deploy Phase 2**

```sh
cd phase2-statefulset
./deploy.sh
```

### **Deploy Phase 3**

```sh
cd phase3-operators
./deploy.sh
```

---

# 🗂 **Repository Log**

```
Initial commit:
✔ Added Docker setup
✔ Added DaemonSet + StatefulSet manifests
✔ Added Operator framework (CRDs, RBAC, deployment)
✔ Added monitoring (Prometheus)
✔ Added project overview & scripts
✔ Added full directory structure
```

---

# 🎯 **Why VLC?**

VLC is used **only as a learning theme**.
The real goal is to teach **Kubernetes orchestration patterns**, not media streaming.

---

# 🚀 **Future Enhancements**

* Add ArgoCD deployment examples
* Integrate full Prometheus + Grafana dashboards
* Implement actual Go-based operator logic

---

# 🏁 Conclusion

This project is a **complete Kubernetes learning lab**, covering:

✔ Nodes → DaemonSets
✔ Pods with identity → StatefulSets
✔ Autoscaling → HPA & VPA
✔ Extending Kubernetes → CRDs + Operator
✔ Infrastructure config → Docker + Prometheus

You can safely use this as a **portfolio project** or **resume highlight**.

---

# 📄 **License**

MIT License
Copyright © 2025 Vamsi Krishna

---

## 🔧 **Where is the project banner image stored?**

Place this file inside your repo:

```
.assets/project-banner.png
```
