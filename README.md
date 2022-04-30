# Otomi: Self-hosted PaaS for Kubernetes

<img src="./otomi-console.png" alt="otomi-screenshot"/>

[Otomi](https://otomi.io/) is an open source self-hosted PaaS for Kubernetes and connects many of the technologies found in the CNCF landscape in a single installable package to provide direct value to developers.

Otomi:

- Brings a full PaaS (like Heroku) to your own Kubernetes cluster. The only thing you'll need to do yourself is build your app image and configure Otomi to use it, which will then do the rest.

- Allows you to use a PaaS on top of K8s without the constraints and abstractions of traditional PaaS offerings like OpenShift, Cloud Foundry and Heroku.

- Removes the burden of building and maintaining your internal (developer) platform, lowers the burden on operations, and empowers developers to focus on application deployment and management only.

## About the workshop

The workshop aims to demonstrate different use cases and features of [Otomi](https://github.com/redkubes/otomi-core) through hands-on labs.

## For who is the workshop?

- Developers
- Solutions Architects
- DevOps Engineers
- SREs
- Infrastructure & Cloud Engineers
- Product Managers

## 🎊 Learning objectives

The main objective is to get a good understanding/overview of Otomi and be able to identify the benefits and possible use cases for it.

## 🛠 Lab prerequisites

- A K8s cluster with al least 16 vCPU and 32GiB memory
- Otomi installed
- CLI tools used in the labs
  - [helm](https://helm.sh/docs/intro/install/)
  - [kubectl](https://kubernetes.io/docs/tasks/tools/)
  - Optionally: [K9s](https://kubernetes.io/docs/tasks/tools/)

## 🚀 Labs

The workshop is organized into 5 labs:

- Lab 1: [Creating Teams](01-create-team/README.md)
- Lab 2: [Configuring network policies](02-netpols/README.md)
- Lab 3: [Activate apps](03-activate-apps/README.md)
- Lab 4: [Using Knative](04-knative/README.md)
- Lab 5: [Using Harbor](05-harbor/README.md)
- Lab 6: [Create and use secrets](06-secrets/README.md)
- Lab 7: [Creating a microservice architecture](05-microservice-architecture/README.md)
- Coming soon: Lab 8: Working with ArgoCD

After completing the labs, you'll be able to:

- Use the Teams feature in Otomi for multi-tenancy and network isolation
- Use te Otomi web UI to expose K8s services and configure network policies between workloads
- Explain the difference between Otomi core apps and how to activate optional apps
- Create Knative workloads using the Otomi web UI
- Expose workloads in a microservice architecture, allowing multiple workloads in different team namespaces to work together.

## 📖 Documentation & support

Official Otomi documentation is available [here](https://otomi.io). We'd also like to invite you to [join our Slack community](https://otomi.slack.com/join/shared_invite/zt-12h11e8aa-6po4NWhhpMXxT~nffDsYqA#/shared-invite/email) for additional support, feature discussions, or just for a quick chat.

The Otomi open source project can be found [here](https://github.com/redkubes/otomi-core) on GitHub. Don't forget to ⭐️ ⭐️ ⭐️.

Thank you!
