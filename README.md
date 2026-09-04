<p align="center">
  <img src="https://raw.githubusercontent.com/aramisjustin068/aramisjustin068/main/assets/header.svg" alt="Amara Justin — DevOps / IaC Engineer" width="880"/>
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/aramisjustin068/aramisjustin068/main/assets/now.svg" alt="now" width="720"/>
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=flat&logo=terraform&logoColor=white" height="22"/>
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white" height="22"/>
  <img src="https://img.shields.io/badge/Helm-0F1689?style=flat&logo=helm&logoColor=white" height="22"/>
  <img src="https://img.shields.io/badge/CI-GitHub%20Actions-2088FF?style=flat&logo=githubactions&logoColor=white" height="22"/>
  <img src="https://img.shields.io/badge/Go-00ADD8?style=flat&logo=go&logoColor=white" height="22"/>
  <img src="https://img.shields.io/badge/Prometheus-E6522D?style=flat&logo=prometheus&logoColor=white" height="22"/>
</p>

---

Cloud and DevOps engineer based in Lyon, France. Most of my work is the
unglamorous half of platform engineering: Terraform modules that still apply
cleanly six months later, Kubernetes manifests a tired on-call engineer can read
at 03:00, and dashboards nobody asks for until the night everybody needs one.

Day to day that means a small platform team, one Kubernetes cluster per
environment, and every infrastructure change arriving as a pull request with a
plan attached.

## What I work with

**Infrastructure as code** — Terraform and Terragrunt for anything with a state
file, Packer for images, Ansible for the legacy VMs that refuse to die.

**Orchestration** — Kubernetes on EKS and a bare-metal kubeadm cluster, plus
Helm, Kustomize and Argo CD for delivery.

**CI/CD** — GitHub Actions and GitLab CI, self-hosted runners on spot capacity,
artifact promotion instead of per-environment rebuilds.

**Observability** — Prometheus, Alertmanager, Grafana, Loki, and OpenTelemetry
collectors in front of them.

**Cloud** — AWS for most workloads, Scaleway and OVHcloud where data has to stay
in France.

**Languages** — Go and Python for tooling, Bash when Bash is honestly enough,
SQL more often than expected.

## A few things here

**[tf-baseline](https://github.com/aramisjustin068/tf-baseline)** — A minimal,
readable VPC module: three-tier network layout, optional NAT gateway, no wrapper
magic hiding the resources.

**[k8s-snippets](https://github.com/aramisjustin068/k8s-snippets)** — The
manifest templates I paste into every new service: Deployment with probes and
limits, Service, and a default-deny NetworkPolicy.

**[incident-runbook](https://github.com/aramisjustin068/incident-runbook)** — The
post-incident review template my team fills in the morning after, structured so
the timeline gets written before anyone argues about the cause.

**[helm-chart-skel](https://github.com/aramisjustin068/helm-chart-skel)** — The
chart skeleton I start every new service with. Deployment and Service templates
that read like they were written by someone who has been paged at 03:00, because
they were. Values that default to sane resource limits, not to whatever the
cloud provider hands you. It is not a library, it is a starting point you delete
the parts you do not need from.

**[sre-dashboard](https://github.com/aramisjustin068/sre-dashboard)** — A
Grafana dashboard definition in JSON plus a Python validator that checks the
panel structure before you import it. Built after watching someone push a
dashboard with a broken panel target and not notice for two weeks. The
validator runs in CI, not at 02:00 during an incident.

None of these are frameworks. They are the small tools that survived contact
with real incidents, which is a lower bar than it sounds and also a real one.

## How I work

- Infrastructure changes go through a pull request with the plan output
  attached. No exceptions, mine included.
- Every alert links to a runbook section. An alert without one is not an alert,
  it is noise with a pager attached.
- Default deny on the network, then open exactly what the service needs and
  write down why.
- The rollback path gets written before the rollout, and tested at least once
  outside an incident.
- Reviews are blameless in the report and specific in the action items. Vague
  follow-ups never ship.

## Homelab

- Three secondhand mini PCs running k3s, mostly so I can break upgrades where
  nobody is paged for it.
- A Prometheus instance watching the home network, which has taught me more
  about cardinality than any production cluster.
- Everything in the lab is bootstrapped from the same Terraform and Ansible
  patterns I use at work, on purpose.

## 📊 Activity

<p align="center">
  <img height="160" src="https://github-readme-stats.vercel.app/api?username=aramisjustin068&show_icons=true&theme=transparent&hide_border=true&count_private=true"/>
  <img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=aramisjustin068&layout=compact&theme=transparent&hide_border=true"/>
</p>
<p align="center">
  <img width="720" src="https://github-readme-activity-graph.vercel.app/graph?username=aramisjustin068&theme=github-compact&hide_border=true&radius=8"/>
</p>

## Contact

Open an issue or a discussion on any repository above — that is the channel I
actually read. I am happy to talk through module design, cluster upgrades, or
why a runbook template needs fewer fields than you think.

---

Opinions here are my own and not my employer's. Code published under MIT unless
a repository states otherwise.
