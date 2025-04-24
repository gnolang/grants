# Project Name
gnoup

- GitHub handle: @GoNameless
- Email: leon@nameless.ventures
- Links:
    - LinkedIn: https://za.linkedin.com/in/leonafrica
    - X: @theleonafrica
    - website: nameless.ventures

## Project summary

This project aims to create a robust, reusable, and production-ready deployment pipeline for gno.land across multiple cloud providers using Rancher, Kubernetes, and Helm. It will integrate with GitHub Actions for CI/CD and include monitoring, observability, and cloud-specific configuration for EKS, GKE, and AKS.

The goal is to enable gno.land contributors, validators, and dApp teams to easily deploy scalable testnets and clusters in real-world environments with minimal setup overhead.

Repo: https://github.com/GoNameless/gnoup

### Goals and deliverables

Board: 

#### Core Goals:

- Enable one-click or automated gno.land deployment to EKS, GKE, and AKS via Rancher-managed Kubernetes clusters.

- Create Helm charts for flexible and scalable deployments.

- Set up GitHub-based CI/CD pipelines with auto-deploy capability.

- Integrate observability tools like Prometheus, Grafana, and Loki.

- Improve the local development experience using lightweight Kubernetes (e.g., Kind or k3d).

- Document the full system and provide reproducible templates.

#### Deliverables:

- Public GitHub repository with Helm charts and deployment automation

- GitHub Actions CI/CD pipeline templates

- Step-by-step deployment documentation for each cloud provider

- Monitoring dashboards and alerting configurations

- Recorded walkthrough or live demo

### Impact on gno.land’s developer ecosystem

This project significantly improves developer and validator experience by providing:

1. Turnkey deployments to real cloud infrastructure

2. Better onboarding for new teams looking to test or validate

3. Scalability for dApps needing testnets or sandboxed environments

4. Monitoring for production-grade clusters

5. Infrastructure templates that reduce DevOps overhead for ecosystem projects


gnoup directly aligns with the **Infrastructure, Developer Experience, and Quality** track of the grant program and is designed to grow and evolve with the network.

### Timeline and milestones

## Project Timeline & Milestones

| Month    | Milestone                                                                                   |
|----------|---------------------------------------------------------------------------------------------|
| Month 1  | Research, planning, and initial test cluster deployment; review gnoland’s current Docker setup |
| Month 2  | Rancher setup, deployment to local cluster using Helm; initial chart development             |
| Month 3  | Cloud integration: Deploy to EKS, GKE, and AKS; handle provider-specific nuances             |
| Month 4  | Build and test full CI/CD pipeline using GitHub Actions; automated deploys to all clusters  |
| Month 5  | Integrate monitoring stack: Prometheus, Grafana, Loki; configure dashboards and alerts       |
| Month 6  | Improve local developer workflow (Kind, k3d), polish configs and hardening                   |
| Month 7  | Final testing, polish, documentation, walkthrough video/demo, public repo release            |


## Contributions or related work for gno.land (if applicable)

1. gnoup: https://github.com/Leon-Africa/gnoup 
[private EC2 based deployment @zivkovicmilos has access]

2. https://github.com/gnolang/gno/pull/2536 
[Suggestion have been implemented at https://github.com/gnolang/gno/tree/master/misc/telemetry]

## Why are you and your team well-suited for this project?

I have a background in infrastructure automation, DevOps, and cloud-native tooling, with hands-on experience in production grade mainnet Blockchain DevOps.

This project combines my passion for blockchain and open-source DevOps practices in a way that can help strengthen gno.land’s foundation.

## Referrals or examples of past work

1. https://github.com/maticnetwork/node-ansible/pull/48
2. https://github.com/Leon-Africa/karpenter-k8s-multi-instance-automation
3. https://github.com/Leon-Africa/flashswap-hardhat
4. https://github.com/ethereum/EIPs/pull/9405
5. https://github.com/Leon-Africa/zkp
6. https://github.com/Leon-Africa/auto-deploy-lotus-fullnode
7. https://github.com/Leon-Africa/avail-node-deployer