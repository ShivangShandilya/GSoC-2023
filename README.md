# Google Summer Of Code 2023

## Organization: CNCF (Armada Project)
During this summer, as part of Google Summer of Code, I contributed to armada, an open source project that comes under the Cloud Native Computing Foundation (CNCF). I am going to share my GSoC experience and project details.


## GSoC Project
### What is armada? 
Armada is a multi-Kubernetes cluster batch job scheduler. Armada is designed to address the following issues:

- A single Kubernetes cluster can not be scaled indefinitely, and managing very large Kubernetes clusters is [challenging](https://openai.com/research/scaling-kubernetes-to-7500-nodes). Hence, Armada is a multi-cluster scheduler built on top of several Kubernetes clusters. 
- Acheiving very high throughput using the in-cluster storage backend, etcd, is [challenging](https://openai.com/research/scaling-kubernetes-to-7500-nodes). Hence, queueing and scheduling is performed partly out-of-cluster using a specialized storage layer.

### Project Details

As a Google Summer Of Code 2023 mentee, I worked on the [Armada Project](https://github.com/armadaproject/armada) under my mentor [Kevin Hannon](https://github.com/kannon92) to implement kubectl plugin for armada.This included in-depth study of [`armadactl`](https://github.com/armadaproject/armada/tree/master/cmd/armadactl), solving issues with `armadactl` that could hinder the work with project and then creating a [`krew`](https://krew.sigs.k8s.io/) plugin for `armadactl` so that users can use armadactl alongside kubectl. Unfortunately the plugin was not recognized by the `krew` community so instead we self-hosted the `armadactl` plugin to make it work with `krew`.

### Why did I choose this project?

I was looking for a GSoC project that would fit my skill set. I bookmarked several projects, did some research, and gathered information about them. 
I was also contributing to Armada sinch February 2023.Since I began contributing, the Armada community has been incredibly supportive, which made me more eager to give back to the community.

### Contributions

I am going to summarise my contributions towards in-toto, which I have done during the Google Summer of Code period. I won’t go into much technical detail, and I’ll try to keep it short.

#### Community Bonding Period
During my community bonding period, my mentor gave me time to understand the codebase and pick up small issues that could be fixed right away.
I also used this time to connect with other amazing folks at the Armada community, everyone was so welcoming it felt like I have been contributing to the org for a long time now.

I divided my project into two major phases. These two phases were also mentioned in my GSoC Proposal.
- First Phase: Deep diving into `armadactl` and solving issues related to that.
- Second Phase: Creating the plugin for `kubectl`

#### First Phase
As mentioned above this phase was totally focused on deep diving and studying about `armadactl`. During this phase I worked on issues that were already available and opened up some more if I encountered any issues along the way.

#### Pull Requests

<b>Merged</b>
- Placing `armadactl` on User's PATH : [#2446](https://github.com/armadaproject/armada/pull/2446), [#2549](https://github.com/armadaproject/armada/pull/2549)
- Removal of example structure block from `armadactl` : [#2551](https://github.com/armadaproject/armada/pull/2551)

<b>Under Review</b>
- Addition of `armadctl` on Armada Website : [#2596](https://github.com/armadaproject/armada/pull/2596)

#### Second Phase
This phase was completely focused on creating the `krew` plugin for `kubectl` that would eventually integrate `kubectl` with `armadactl` and users would be able to use features of `armadactl` through `kubectl`.
I was able to create the plugin for `krew` but unfortunately `krew` community didn't recognize the plugin so we had to self-host the plugin in armada [`main`](https://github.com/armadaproject/armada) repository.

<b>Merged</b>
- Self-hosting `armadactl` plugin in armada : [#2850](https://github.com/armadaproject/armada/pull/2850)
- Adding documentation on how one can use `armadactl` with `kubectl` : [#2897](https://github.com/armadaproject/armada/pull/2897)

<b>Under Review</b>
- Adding `armadactl` plugn on Krew (hoping Krew merges it): [#3280](https://github.com/kubernetes-sigs/krew-index/pull/3280)

### Overall Experience
I think my report says how much fun I had working on this project. This wouldn't have been possible without the immense support from the [`armada`](https://github.com/armadaproject/armada) community. And even after the GSoC period ends I'm going to work on improving `armadactl` even further maybe even deep dive into other aspects of `Armada Project`.
