1.Tools for running Kubernetes clusters locally

1.1 Minikube

It is a tool for setting up a single-node Kubernetes cluster on a local machine. It provides an easy way to run and manage a lightweight Kubernetes environment. It is suitable for developers who want to test their applications locally and experiment with Kubernetes features.

1.2 Kind (Kubernetes in Docker)

It is a tool that allows developers to run Kubernetes clusters using Docker containers as nodes. It is designed to be lightweight and fast, making it suitable for local development and testing scenarios. It is easy to set up and can create multi-node clusters for simulating more complex Kubernetes environments.

1.3 k3d

It makes it very easy to create and single- and multi-node Kubernetes k3s clusters in Docker. It is known for its simplicity and fast setup time, making it suitable for local development and testing.

2.Characteristics

|                            | **Minikube**                                                                                                   | **Kind**                                                                                                                                          | **k3d**                                                                                                        |
|----------------------------|----------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| **Supported OS**           | Linux, macOS, Windows                                                                                          | Linux, macOS, Windows                                                                                                                             | Linux, macOS, Windows                                                                                          |
| **Supported Architecture** | x86-64, arm64, armv7, ppc64, s390x                                                                             | x86-64, arm64                                                                                                                                     | x86-64, arm64                                                                                                  |
| **CI/CD**                  | Prow, Google Cloud Build, GitHub, Azure Piplines, Travis CI, GitLab                                            | GitHub, Azure Piplines, Travis CI, GitLab                                                                                                         | GitHub Actions, Drone CI                                                                                       |
| **Kubernetes Control**     | use kubectl to create and manage deployments, services, pods, and other Kubernetes resources.                  | kubectl or any Kubernetes management tool to controland interact with the cluster.                                                                | kubectl                                                                                                        |
| **Container Runtime**      | options including Docker, Podman and containerd.                                                               | Docker                                                                                                                                            | Docker, Podman                                                                                                 |
| **Networking**             | Ingress and Load Balancing to enable routing external traffic to cluster.                                      | Cluster Networking allowing containers within the cluster to communicate with each other. LoadBalancer is working in a kind cluster using Metallb | New network for each cluster. Nginx loadbalancer alongside the clusters with port-forwarding.                  |
| **Monitoring**             | Integration with third-party monitoring tools like Prometheus and Grafana to monitor cluster and applications. | Integration with third-party monitoring tools like Prometheus and Grafana to monitor cluster and applications.                                    | Integration with third-party monitoring tools like Prometheus and Grafana to monitor cluster and applications. |

3.Pros & Cons
|              | **Pros**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | **Cons**                                                                                                                                                                                                                                                                                       |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Minikube** | Easy setup and management of a single-node and multi-node Kubernetes cluster. Support for multiple operating systems and architectures. Integration with kubectl for managing and interacting with the cluster. Optional add-ons to enhance cluster functionality. Ingress and load balancing support. Popularity, Community support and active development. Experimental Podman support.                                                                                                        | Additional features like monitoring require integration with third-party tools. Resource-intensive, may require a machine with sufficient resources to run smoothly. Lack of built-in support for automatic cluster provisioning. Poor automation options: there is no configuration file.     |
| **Kind**     | Lightweight and fast setup of Kubernetes clusters using Docker containers. Support for multiple operating systems and architectures. Full compatibility with the standard Kubernetes API and tools. Customization and extensibility of clusters through Kubernetes configuration. Suitable for local development, testing, and CI pipelines. Easy creation and deletion of clusters through the CLI. Podman support. yml-file for configuration.                                                 | Lack of built-in monitoring or control features. Additional tools or integrations needed for monitoring and cluster management. Lack of automated cluster provisioning.                                                                                                                        |
| **k3d**      | Lightweight and fast creation of Kubernetes clusters using Docker containers. Support for multiple operating systems and architectures. Integration with container runtimes like Docker and containerd. Customization and extensibility of clusters through Kubernetes configuration. Networking support for container communication within the cluster. Load balancer integration for exposing services. Suitable for local development, testing, and CI pipelines. yml-file for configuration. | Lack of built-in monitoring or control features. Additional tools or integrations needed for monitoring and cluster management. Lack of automated cluster provisioning. Cluster scalability may be limited based on machine resources and Docker license limitations. Podman is not supported. |

4.Demo

4.1 Minikube

![Screenshot_minikube_service](https://github.com/svolkov/startup/assets/9334152/d41815ca-2d62-473c-bc85-a16215151747)

4.2 Kind

![screenshot_kind_service](https://github.com/svolkov/startup/assets/9334152/23b0b423-1f7b-4405-b6a3-e57c42eab785)


4.3 k3d

![screenshot_k3d_service](https://github.com/svolkov/startup/assets/9334152/00faf2a4-eaa9-4eec-9591-2274ce093690)


5.Conclusion

To get local environment in a simple and quick way, Kind and k3d would be the right choice based on its ability to read configuration file at the start.
If Docker license limitation will be critical for the startup, the Kind is the choice based on its Podman support. 

