# Amara Justin

![Terraform](https://img.shields.io/badge/Terraform-623CE4?style=flat&logo=terraform&logoColor=white) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white) ![CI](https://img.shields.io/badge/CI-GitHub%20Actions-2088FF?style=flat&logo=githubactions&logoColor=white)

Cloud and DevOps engineer based in Lyon, France. Most of my work is the
unglamorous half of platform engineering: Terraform modules that still apply
cleanly six months later, Kubernetes manifests a tired on-call engineer can read
at 03:00, and dashboards nobody asks for until the night everybody needs one.

Day to day that means a small platform team, one Kubernetes cluster per
environment, and every infrastructure change arriving as a pull request with a
plan attached.

## Stack

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

## Selected work

**[tf-baseline](https://github.com/aramisjustin068/tf-baseline)** — A minimal,
readable VPC module: three-tier network layout, optional NAT gateway, no wrapper
magic hiding the resources.

**[k8s-snippets](https://github.com/aramisjustin068/k8s-snippets)** — The
manifest templates I paste into every new service: Deployment with probes and
limits, Service, and a default-deny NetworkPolicy.

**[incident-runbook](https://github.com/aramisjustin068/incident-runbook)** — The
post-incident review template my team fills in the morning after, structured so
the timeline gets written before anyone argues about the cause.

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

## Contact

Open an issue or a discussion on any repository above — that is the channel I
actually read. I am happy to talk through module design, cluster upgrades, or
why a runbook template needs fewer fields than you think.

---

Opinions here are my own and not my employer's. Code published under MIT unless
a repository states otherwise.
