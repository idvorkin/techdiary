# Cloud native services

## Why?

<!-- prettier-ignore-start -->
<!-- vim-markdown-toc GFM -->

- [Success criteria For this post](#success-criteria-for-this-post)
- [Micro services](#micro-services)
- [Containers](#containers)
    - [Containers are about application packaging and delivery.](#containers-are-about-application-packaging-and-delivery)
        - [The power of the Dockerfile and image repository.](#the-power-of-the-dockerfile-and-image-repository)
    - [Containers as execution hosts - vs Virtual and Physical Machines](#containers-as-execution-hosts---vs-virtual-and-physical-machines)
    - [Container Orchestration](#container-orchestration)
        - [Kubertnetes](#kubertnetes)
        - [Everything else](#everything-else)
- [Networking](#networking)
    - [Planes - Control, Data, and Management](#planes---control-data-and-management)
    - [Communication buses: Envoy](#communication-buses-envoy)
- [New patterns](#new-patterns)
    - [Side cars](#side-cars)
- [Functions as a Service FaaS](#functions-as-a-service-faas)
    - [Introduction](#introduction)
    - [FaaS Orchestration](#faas-orchestration)
    - [Triggers](#triggers)
    - [Security](#security)
    - [Logging](#logging)
    - [Triggers](#triggers-1)
    - [Debugging](#debugging)
- [References:](#references)
- [Organizational Challenges](#organizational-challenges)
    - [Conways law - Four complier teams implies a four pass complier](#conways-law---four-complier-teams-implies-a-four-pass-complier)

<!-- vim-markdown-toc -->
<!-- prettier-ignore-end -->

## Success criteria For this post

## Micro services

## Containers

### Containers are about application packaging and delivery.

We often talk about containers being a light weight VM, which they are. However, I think the real value of the container (which is why docker is synonymous with container), is a software packaging and delivery mechanism.The sole reason Docker containers got more attention than its competition is because of this software delivery approach.

#### The power of the Dockerfile and image repository.

### Containers as execution hosts - vs Virtual and Physical Machines

(Yes there is other container tech, for example [here](https://www.katacoda.com/courses/containers-without-docker))

### Container Orchestration

#### Kubertnetes

#### Everything else

- Docker Swarm
- Service Bus
- Methos

## Networking

### Planes - Control, Data, and Management

### Communication buses: Envoy

## New patterns

### Side cars

Package functionality into a seperately injected application: https://docs.microsoft.com/en-us/azure/architecture/patterns/sidecar

## Functions as a Service FaaS

### Introduction

### FaaS Orchestration

### Triggers

### Security

### Logging

### Triggers

### Debugging

## References:

## Organizational Challenges

### Conways law - Four complier teams implies a four pass complier

Conway's law is an aphorism in IT that posits the idea that “organizations which design systems are constrained to produce designs which are copies of the communication structures of these organizations.” This idea can be traced back to a programmer named Melvin Conway who developed this principle in the late 1960s.

- [Container usage study](https://www.datadoghq.com/container-orchestration/)
- [Azure cloud patterns](https://docs.microsoft.com/en-us/azure/architecture/patterns/)
- [Building Microservices: Designing Fine-Grained Systems](https://www.amazon.com/Building-Microservices-Designing-Fine-Grained-Systems/dp/1491950358)
- [Designing Data-Intensive Applications: The Big Ideas Behind Reliable, Scalable, and Maintainable Systems](https://www.amazon.com/Designing-Data-Intensive-Applications-Reliable-Maintainable/dp/1449373321/ref=pd_lpo_sbs_14_t_0?_encoding=UTF8&psc=1&refRID=AZ1QGMVFB2K45MWY14X0)