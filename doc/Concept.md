1.Tools for running Kubernetes clusters locally

1.1 Minikube

It is a tool for setting up a single-node Kubernetes cluster on a local machine. It provides an easy way to run and manage a lightweight Kubernetes environment. It is suitable for developers who want to test their applications locally and experiment with Kubernetes features.

1.2 Kind (Kubernetes in Docker)

It is a tool that allows developers to run Kubernetes clusters using Docker containers as nodes. It is designed to be lightweight and fast, making it suitable for local development and testing scenarios. It is easy to set up and can create multi-node clusters for simulating more complex Kubernetes environments.

1.3 k3d

It makes it very easy to create and single- and multi-node Kubernetes k3s clusters in Docker. It is known for its simplicity and fast setup time, making it suitable for local development and testing.

|                            | **Minikube**                                                                                                   | **Kind**                                                                                                                                          | **k3d**                                                                                                        |
|----------------------------|----------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| **Supported OS**           | Linux, macOS, Windows                                                                                          | Linux, macOS, Windows                                                                                                                             | Linux, macOS, Windows                                                                                          |
| **Supported Architecture** | x86-64, arm64, armv7, ppc64, s390x                                                                             | x86-64, arm64                                                                                                                                     | x86-64, arm64                                                                                                  |
| **CI/CD**                  | Prow, Google Cloud Build, GitHub, Azure Piplines, Travis CI, GitLab                                            | GitHub, Azure Piplines, Travis CI, GitLab                                                                                                         | GitHub Actions, Drone CI                                                                                       |
| **Kubernetes Control**     | use kubectl to create and manage deployments, services, pods, and other Kubernetes resources.                  | kubectl or any Kubernetes management tool to controland interact with the cluster.                                                                | kubectl                                                                                                        |
| **Container Runtime**      | options including Docker, Podman and containerd.                                                               | Docker                                                                                                                                            | Docker, Podman                                                                                                 |
| **Networking**             | Ingress and Load Balancing to enable routing external traffic to cluster.                                      | Cluster Networking allowing containers within the cluster to communicate with each other. LoadBalancer is working in a kind cluster using Metallb | New network for each cluster. Nginx loadbalancer alongside the clusters with port-forwarding.                  |
| **Monitoring**             | Integration with third-party monitoring tools like Prometheus and Grafana to monitor cluster and applications. | Integration with third-party monitoring tools like Prometheus and Grafana to monitor cluster and applications.                                    | Integration with third-party monitoring tools like Prometheus and Grafana to monitor cluster and applications. |
