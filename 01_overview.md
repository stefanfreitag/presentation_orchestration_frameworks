#  Container Orchestration Frameworks



## What are Containers?


### Shipping containers
- Efficiently moved
- Ubiquitous
- Standardized
- Available anywhere in the world
- Extremely simple to use
- Content is kept isolated from that of the others
- No way for a neighboring container to steal more than its share of space.

Note:
- Efficiently moved:
  - Using different modes of transport
  - At no point in the journey do the contents of that container need to repacked or modified in any way.
- Easy to use: just open them up, load in your cargo, and lock the doors shut.
- Isolation: A container full of Mentos can safely sit next to the container full of soda without any risk of a reaction.
- Booked spot on the ship:
- Once a spot on the container ship has been booked, you can be confident that there's room for all of your packed cargo for the whole trip


### Sofware containers
Fulfill a similar role for your application.

- Packing involves defining what needs to be there for your application to work
- Once defined, that *image* is used to create containers that run in any environment
- Many containers can run on the same machine

Note:
- Packaging: Operating system, libraries, configuration files, application binaries, and other parts of your technology stack.
- Run in any environment:  From the developer's laptop to your test/QA rig, to the production data center, on-premises or in the cloud, without any changes.
- Consistency: A support engineer can spin up a container to replicate an issue and be confident that it exactly matches what's running in the field.
- Many containers on one machine: Allowing full use of all available resources. Linux containers and cgroups are used to make sure that there's no cross-contamination between containers: data files, libraries, ports, namespaces, and memory contents are all kept isolated. They also enforce upper boundaries on how much system resource (memory, storage, CPU, network bandwidth, and disk I/O) a container can consume so that a critical application isn't squeezed out by noisy neighbors.


### Sofware containers
Exceptions to the metaphore exist as shipping containers typically don't interact with each other

Software containers can interact with each other through well defined interfaces

*The modular container model is a great way to implement microservice architectures*

Note:
- Interaction: One container provides a database service that an application running in another container can access through an agreed port.


### Business value
- DevOps & Continuous Delivery
- Replicating Environments
- Accurate Testing
- Scalability
- Isolation
- Performance
- High Availability

Note:
- DevOps & Continuous Delivery: When the application consists of multiple containers with clear interfaces between them, it is a simple and low-risk matter to update a container, assess the impact, and then either revert to the old version or roll the update out across similar containers. By having multiple containers provide the same capability, upgrading each container can be done without negatively affecting service.
- Replicating Environments: When using containers, it's a trivial matter to instantiate identical copies of your full application stack and configuration. These can then be used by new hires, partners, support teams, and others to safely experiment in isolation.
- Accurate Testing: You can have confidence that your QA environment exactly matches what will be deployed – down to the exact version of every library.
- Scalability: By architecting an application to be built from multiple container instances, adding more containers scales out capacity and throughput. Similarly, containers can be removed when demand falls. Using orchestration frameworks – such as Kubernetes and Apache Mesos – further simplifies elastic scaling.
- Isolation: Every container running on the same host is independent and isolated from the others as well as from the host itself. The same equipment can simultaneously host development, support, test, and production versions of your application – even running different versions of tools, languages, databases, and libraries without any risk that one environment will impact another.
- Performance: Unlike VMs (whether used directly or through Vagrant), containers are lightweight and have minimal impact on performance.
- High Availability. By running with multiple containers, redundancy can be built into the application. If one container fails, then the surviving peers – which are providing the same capability – continue to provide service. With the addition of some automation (see the orchestration section of this paper), failed containers can be automatically recreated (rescheduled) either on the same or a different host, restoring full capacity and redundancy.

Source: [https://www.mongodb.com/containers-and-orchestration-explained](https://www.mongodb.com/containers-and-orchestration-explained)



# Container Orchestration


## Why?

- Automate the process of deploying multiple containers to implement an application.
- Importance grows with the number of applications, containers, and hosts.


## Existing Frameworks

 Name         | Maintainer                 | License
 ------------ | -------------------------- | ----
Docker Swarm  | Docker                     | Apache 2.0
Kubernetes    | CNCF                       | Apache 2.0
Mesos         | Apache Software Foundation | Apache 2.0
Nomad         | HashiCorp                  | Mozilla Public 2.0
Titus         | Netflix                    | Apache 2.0
...           | ...                        |

## Overview
 Name         | Community
 ------------ | ---------------------------------------
Docker Swarm  | 5k+ Stars, 1k+ Forks, 160+ Contributors
Kubernetes    | 35k+ Stars, 12k+ Forks, 1k+ Contributors
Mesos         | 3k+ Stars, 1k+ Forks, 270+ Contributors
Nomad         | 3k+ Stars, 600+ Forks, 240+ Contributors
Titus         | 1k+ Stars,40+ Forks, 5+ Contributors
(April 2018)


## Google Trends Search

(Source: https://trends.google.de/trends/explore?cat=5&date=today%205-y&q=kubernetes,docker%20swarm,%2Fm%2F012n8tpr)
