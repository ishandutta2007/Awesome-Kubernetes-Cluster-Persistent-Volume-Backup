# Awesome-Kubernetes-Cluster-Persistent-Volume-Backup

# Awesome-Kubernetes-Cluster-Persistent-Volume-Backup

# Top Kubernetes Cluster & Persistent Volume Backup Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Cluster State Backup, Persistent Volume Snapshots, Application-Aware Recovery & Multi-Cluster Disaster Recovery*  
**Last updated: November 2026**

This repository tracks notable **SaaS/hosted platforms** and **open-source projects** for **Kubernetes Cluster & Persistent Volume Backup**. These systems protect etcd/cluster resources and CSI-backed volumes—enabling scheduled backups, point-in-time restore, and cross-cluster migration.

**Examples** include Druva Kubernetes Protection, Kasten by Veeam, Commvault K8s Protection, Cohesity DataProtect for Kubernetes, Rubrik Kubernetes Protection, Portworx PX-Backup, Velero, CloudCasa by Catalogic, TrilioVault for Kubernetes, Red Hat Advanced Cluster Management, and SUSE-related data protection offerings.

**Open-source emphasis**: Cluster and PV backup is led by open source. **Velero**, **Stash**, **K8up**, **Kanister**, **VolSync**, and **restic**-based operators form the practical foundation. This section is heavily expanded.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Kasten by Veeam, CloudCasa by Catalogic, Portworx PX-Backup, TrilioVault for Kubernetes](https://www.kasten.io/)**  
  Kubernetes-native backup and mobility platforms—application-centric policies, PV protection, and multi-cluster restore workflows.

- **[Commvault, Rubrik, Cohesity, Druva](https://www.commvault.com/)**  
  Enterprise data-protection suites with dedicated Kubernetes modules for cluster resources and persistent data.

- **[Red Hat Advanced Cluster Management & OpenShift data protection integrations](https://www.redhat.com/en/technologies/management/advanced-cluster-management)**  
  Fleet management with backup/DR patterns for OpenShift and Kubernetes estates.

- **[Other commercial K8s backup platforms](https://www.rubrik.com/)**  
  Additional vendors offering container, volume, and cluster protection with enterprise support.

## Open-Source GitHub Projects

### Cluster & Application Backup

- **[Velero](https://github.com/vmware-tanzu/velero)**  
  Leading open-source tool for Kubernetes backup, restore, and migration—captures cluster resources and persistent volumes to S3-compatible object storage.

- **[Stash (AppsCode)](https://github.com/stashed/stash)**  
  Open backup operator for Kubernetes—CRD-driven, application-aware backups using restic for volumes and databases.

- **[K8up](https://github.com/k8up-io/k8up)**  
  Open restic-based backup operator—schedules, backups, restores, and prunes for Kubernetes workloads.

- **[Kanister](https://github.com/kanisterio/kanister)**  
  Open data-protection framework—blueprint-driven, application-consistent backup and restore for stateful apps on Kubernetes.

- **[VolSync](https://github.com/backube/volsync)**  
  Open asynchronous volume replication and migration using CSI—useful for DR and moving PVs between clusters.

### Volume Snapshots, Storage & Engines

- **[Kubernetes CSI Snapshot APIs](https://github.com/kubernetes-csi/external-snapshotter)**  
  Official open external-snapshotter and volume snapshot CRDs—foundation for storage-native PV backups.

- **[restic](https://github.com/restic/restic)**  
  Open deduplicated, encrypted backup engine used by Stash, K8up, and many custom pipelines.

- **[kopia](https://github.com/kopia/kopia)**  
  Open fast backup tool increasingly adopted in Kubernetes-friendly volume and file backup flows.

- **[Longhorn](https://github.com/longhorn/longhorn)**  
  Open distributed block storage for Kubernetes with recurring snapshots and backup-to-object-storage.

- **[OpenEBS](https://github.com/openebs/openebs)**  
  Open Kubernetes-native storage engines with snapshot capabilities depending on the storage backend.

- **[Piraeus / DRBD-based replication](https://github.com/piraeusdatastore/piraeus)**  
  Open software-defined storage patterns for replicated volumes and recovery scenarios.

### Control Plane & Supporting Patterns

- **[etcd snapshot best practices / etcdctl](https://github.com/etcd-io/etcd)**  
  Critical open tooling for control-plane backup—complement app-level Velero backups with etcd snapshots.

- **[Cluster API](https://github.com/kubernetes-sigs/cluster-api)**  
  Open cluster lifecycle project often combined with Velero for full environment rebuilds.

### Additional Strong Open-Source Options

- **Default choice for cluster + PV backup**: Velero.
- **Operator + restic workflows**: Stash or K8up.
- **App-consistent hooks**: Kanister.
- **Ongoing PV sync / migration**: VolSync.
- **Storage-native snapshots**: CSI VolumeSnapshot + Longhorn/OpenEBS where applicable.
- **Composable stacks**: Velero (resources + PV) → object storage; CSI snapshots for fast rollback; etcd snapshots for control plane.
- Commercial platforms still lead for unified policy UI, compliance reporting, and multi-cloud support SLAs.

**Frameworks for building custom systems**:  
**Velero** for portable cluster and volume backups; **Stash**/**K8up** for restic operators; **Kanister** for database-aware blueprints; **VolSync** for replication; **CSI snapshots** for storage-level recovery.  
Fully open cluster and persistent volume backup is production-ready for most platform teams.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS/hosted or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- A backup is only as good as its restore—test regularly. Encrypt backup targets, restrict credentials, and verify CSI snapshot support for your storage classes. etcd and application data may need coordinated schedules for consistency.
- Open-source tools offer transparency and no license lock-in. Commercial products shift policy management and support to the vendor. Neither replaces runbooks, RTO/RPO planning, and chaos-style restore drills.

---

**Made for platform engineers, SREs, and Kubernetes operators who treat recovery as mandatory.**  
Let's expand open cluster and persistent volume backup while recognizing the enterprise workflow depth that commercial Kubernetes protection platforms deliver.
