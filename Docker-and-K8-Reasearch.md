- [Kubernetes](#kubernetes)
  - [What is Kubernetes](#what-is-kubernetes)
  - [Why Kubernetes](#why-kubernetes)
  - [Kubernetes benefits](#kubernetes-benefits)
    - [1. Scalability](#1-scalability)
    - [2. High Availability](#2-high-availability)
    - [3. Self-Healing](#3-self-healing)
    - [4. Resource Efficiency](#4-resource-efficiency)
  - [What is a Kubernetes Cluster](#what-is-a-kubernetes-cluster)
  - [Difference between Containerisation and Virtualisation](#difference-between-containerisation-and-virtualisation)
    - [Containerisation](#containerisation)
    - [Virtualisation](#virtualisation)
- [Docker](#docker)
  - [What is Docker](#what-is-docker)
  - [Why use Docker](#why-use-docker)
    - [Benefits of Docker:](#benefits-of-docker)
  - [Monolith vs 2-Tier vs Microservices](#monolith-vs-2-tier-vs-microservices)


# Kubernetes

## What is Kubernetes

Kubernetes is a portable, extensible, open source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

It's like an orchestra each musician is a container kubernetes is the conductor that manages those containers. The orchestra itself would be the application.

## Why Kubernetes

Containers are a good way to bundle and run your applications. In a production environment, you need to manage the containers that run the applications and ensure that there is no downtime. For example, if a container goes down, another container needs to start. Wouldn't it be easier if this behavior was handled by a system?

## Kubernetes benefits

Kubernetes provides a comprehensive platform for automating the deployment, scaling, and management of containerized applications. Its features enhance the efficiency, reliability, and security of applications, making it an ideal choice for modern cloud-native architectures.

### 1. Scalability
Kubernetes can automatically scale applications in and out based on demand one way it does this is through a replica set. It supports horizontal scaling by adding more instances of an application when needed and removing them when demand decreases.

Replicas are pods of containers that are ready to me used.

### 2. High Availability
Kubernetes ensures high availability of applications through features like:
- **Automatic Restarts**: Automatically restarts containers that fail or stop.
- **Replicas**: Maintains the desired number of application instances running.
- **Load Balancing**: Distributes network traffic evenly across all instances of an application.

### 3. Self-Healing
Kubernetes can detect when a container or node fails and automatically reschedules the affected containers to ensure that the desired state of the application is maintained. This reduces downtime and ensures continuous operation.

### 4. Resource Efficiency
Kubernetes efficiently utilizes hardware resources by dynamically allocating resources to applications as needed. This helps in maximizing resource usage and reducing costs.

## What is a Kubernetes Cluster

A system deployed on Kubernetes

A Kubernetes (K8s) cluster is a set of nodes that run containerized applications managed by the Kubernetes orchestration system. It enables the deployment, scaling, and management of applications in containers across multiple hosts, providing resilience, scalability, and ease of management. Here’s a detailed breakdown of the components and workings of a Kubernetes cluster:

- **Master Node (Control Plane)**
The master node is responsible for managing the cluster. It runs several critical components:

- **Worker Nodes**
Worker nodes are the machines where containerized applications run. Each worker node includes:

## Difference between Containerisation and Virtualisation

| Feature           | Virtualization                             | Containerization                                 |
|-------------------|--------------------------------------------|--------------------------------------------------|
| **Isolation**     | Strong, via hypervisor and separate OSes   | Lightweight, via OS-level features               | 
| **Resource Usage**| Higher, due to multiple OS instances       | Lower, shares host OS kernel                     |
| **Boot Time**     | Longer, as each VM boots a full OS         | Shorter, containers start almost instantly       |
| **Portability**   | Moderate                                   | High, consistent environments across development |
| **Use Cases**     | Legacy applications, different OSes        | Microservices, DevOps, rapid deployment          |


- **Virtualization** is ideal for scenarios requiring complete isolation and the ability to run different operating systems on the same hardware.
- **Containerization** is suited for modern application development, especially for microservices, due to its lightweight nature, speed, and efficiency. one end point an id

Container has a weaker security they are very easy to get into whereas a with virtualisation need to ssh in and povide the appropriate key pairs

### Containerisation

Containerisation involves encapsulating an application and its dependencies into an image where the container runs on the host’s OS. Containers share the host OS kernel but are isolated from each other using OS-level features.

### Virtualisation 

Virtualisation involves creating multiple virtual machines on a single physical machine. Each VM runs its own operating system (OS) and applications, providing complete isolation from other VMs on the same host.

# Docker

## What is Docker

Docker is a containerization platform that allows developers to package applications and their dependencies into standardized units called containers. These containers provide a consistent environment for running applications across different systems, ensuring that software behaves the same way regardless of where it's deployed. Docker simplifies the process of software development, enabling developers to build, ship, and run applications with ease.

Thousands of images you can choose from that can be ran and destroy in a matter of seconds.

## Why use Docker

Docker offers numerous benefits for software development and deployment. Firstly, it streamlines the development process by providing a consistent environment for building and testing applications. 

Docker can't scale.

### Benefits of Docker:

- **Portability**: Applications packaged in Docker containers can run consistently across different environments, reducing compatibility issues and simplifying deployment.
- **Efficiency**: Docker containers are lightweight and share the host OS kernel, leading to faster startup times and efficient resource utilization.
- **Isolation**: Containers provide isolation for applications, ensuring that they do not interfere with each other and improving security.
- **Scalability**: Docker's container orchestration tools allow for easy scaling of applications to meet varying demand.
- **Consistency**: Docker promotes consistency across development, testing, and production environments, reducing the chances of "works on my machine" issues and streamlining the software delivery process.

## Monolith vs 2-Tier vs Microservices

Monolithic Architecture:

Monolithic architecture is best suited for applications with relatively stable and predictable requirements, such as a school management system used by a fixed number of students. In this scenario, the application serves a specific user base, and the number of users is unlikely to fluctuate significantly. With monolithic architecture, all components of the application are tightly coupled and deployed as a single unit. While this approach simplifies development and deployment, it may become challenging to maintain and scale as the application grows or requirements change.

2-Tier Architecture:

If the school decides to expand its operations and offer the application across all its branches throughout the UK, serving thousands of students, a 2-tier architecture may be more suitable. In a 2-tier architecture, the application is divided into two layers: a presentation layer and a data management layer. This separation allows for better scalability and availability, as the presentation layer can be scaled independently from the data layer. Additionally, by distributing the application's workload across multiple servers or locations, 2-tier architecture can improve performance and fault tolerance.

Microservices Architecture:

As the school continues to grow and adapt to changing demands, it may eventually transition to a microservices architecture. In a microservices architecture, the application is decomposed into smaller, independently deployable services, each responsible for a specific business function. For example, the school management system could consist of services for student enrollment, grade tracking, and resource allocation, among others. Microservices offer several advantages, including improved agility, scalability, and fault isolation. However, they also introduce complexity in terms of service communication, data consistency, and deployment management.

Conclusion:

Each architecture has its strengths and weaknesses, and the choice depends on factors such as the application's size, complexity, scalability requirements, and organizational goals. While monolithic architecture may be suitable for simple applications with stable requirements, 2-tier architecture offers better scalability and availability for larger deployments. Microservices architecture, on the other hand, provides the highest level of flexibility and scalability but requires careful design and management to realize its full benefits. Ultimately, the school must evaluate its current and future needs to determine the most appropriate architecture for its application.


