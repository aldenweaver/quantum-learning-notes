# Kubernetes & Python Meetup 2024-01-024 [Notes]

Your local machine
python file
Dockerfile

Doker build cmd on machine results in an image that you push to a registry (db for storing images (usually cloud hosted db) 

Container pull onto any machine anywhere with Docker running

K8s container orchestration plaform
High availability - running multiple copies of an image at once
Self heaing
Maximize usage of available compute resources


Container running an application
Had to run multiple copies in parallel

Ability to maximize what compute *resources* you have available
Each resource is pooled in such a way you can divy up the resources any way you like
Make the most of every node (day)
Find the node within your cluster with the resources required to run servicex

Kubernetes development flow
Everything plus a couple steps

Standard Kubernetes Dev/Deployment Flow
spins up resources defined in yaml manifest

K8 native application development
[[Source Code + K8s SDK] -> container image to YAML manifest] then kubctl to [Kubernetes K8s API -> K8s Deployment]

Kubernetes native app

Code running in Kubernetes is available via API accessible Python resources
You can do anything you imagine doing
Keep going!

Write an app, containerize it, interact with API via cluster
Able to spin up additional resources
Giving your app away to dynaically on the fly spin up additional infrastructure resources
Way to give yourself addiitional resources to offload certain tasks
So why build one?
Running isolated processes in your cluster
Running workflows asynchronoyusly in your cluster
Distributing workflows acreoss your cluter's allocated resources
Run it in with the rest of the code in isolation due to security concerns
Why create a Kubernetes container? Running an isolated process, asynchronous background tasks
Achitecture that involes an async background task
Spins up image in container for a finite amount of time, completes function & returns, then cleans itself up
Super efficient & clean way to complete a task
Finds the best place for these async nodes to run
Standard Kubernetes 

3 instances running in parallel 



Need to do something additionally beyond handling background traffic to handle workload dynamically

Hands off tasks to other resources & cleans it up

Something that needs to pass task is responsible to handing it off/teaching/disclipleship

Kubernetes pods work similarly to containers

Tidy themselves up when process ends

We are all nodes to run the processes to do Gods work

Evolving over time

Distributed systems

Some servers are running indefinitely/Allwehs

Interact with Kubernetes pod inside the cluster

Also keeps track of who spun it up & names it accordingly

As subsequent requests come in a user task is run in their pod

Garbage collection service running in the background is continually pulling the Kubernetes API to where it didn’t meet criteria for definitely tearing down

Impetous

Video frame stabilization

Trims down video frame by frame

Downloads video

Uploads file back into stabilized form

Time intensive workflow so good candidate for Kubernetes native

Super lite traffic still bogs it down

CPU intensive

Adding additional layer can speed up additional infrastructure pieces that only life for the time of a certain task before they get dynamically pulled down

Deployments are only spun up upon request

Create a deployment & pod; pods to do additional work are handled by deployment

Inside of that pod is a container

No matter how you want to run container it is a finite process

Teachers & discipleship

Frees up processing so you can handle incoming traffic 

Running efficiently 

Not bugging

Not bogging things down in an effort to to not bog things down/speed things up

Job queue, job queue broker

Hits API, stores image in MongoDB

Not as queue (FIFO) but as standalone process that is more organic running in parallel

LIFO/Stack

Flag gives it a file name

How many current flags do 

Standard cluster is usally 3 nodes

Usually run odd number of nodes due to elections in cluster

List of tasks

Automatically abstracted 

Variable

Want to be performant, don't wait for it to spin up everything you do a task

Running up nodes computationally

Apply networking rules

Fine grain controls/fine tune

Running in to problems

Asynchronous processing & compute resources users

Base Python image

Exec into pods

Copy script in run it, capture output & return to user

What has been sitting idle

Garbage collection running in background

Refresh

Maintenance & fine tuning done by angels?

User experience

Performance indicator in app dependent on speed

Might eat up too much time to spin up so would be too negligible



Create job objects, define in yaml manifest

Key value pairs

Have to know more or less what different elements are

Define specific image to run, set environment variables

Ingress allows external jobs to be sent on path to port 8000 (?)

Once you get it down, copy pasta is real & you can deploy stuff efficiently

Helm templating

Raft Consensus. 
    Overview of how it works: https://raft.github.io/

Application to quantum resource allocation & AI

Intersections of memory needed to save progress & resource allocation/garbage collection

Smart garbage collection

Ability to self heal

Number of containers per pod

Side cars

Containers running near each other can share a pod/simulation/world

Only one container per pod allows you to leverage high availability/self healing abaialbilities

Not managing containers, managing pods

Running one process per container is rare

One self contained process per pod

If one goes down they all go down

If you want it to keep going if service A fails, service B fails, you have to put them in separate pods (quantum entanglement & relationships)

Local cluster options

Mini kube, Kind, container, Russian dolls

You can run more nodes that way / if they cooperate together to do good works

Unlike other cloud providers you don’t have to pay for control layer

Only have to pay for compute resources

If you don’t use nodes clusters or they don’t do the jobs you want, they still cost money

Tending towards using microK8?

If it breaks it’s just the click of a check mark

New Kubernetes cluster of it breaks can use an uninstall & then reinstall

Those looking to get started & are overwhelmed by sheer amount of options, it is a good place to start because it is baked into Docker ???

Once cluster is running get cli out of box so can run commands without messing around about connecting everything, easier to spin up, can catch up quickly

To run basic things it’s not too difficult to run commands 



Where to get started if new to Kubernetes?

Infinite layers, learn about each layer as you go

The best thing to do may be to look at pods in particular

Don’t get overwhelmed with different infrastructure pieces

Start small with container in Kubernetes having to be run in a pod

Fewer than 10 lines

Pod manifest running in yaml file manifest
If I get this to run, can I check the logs?

Start from the middle then work out (classical mechanics) start from pods then go from there

Millions of resources
    O’Reilly books & platforms

Start at beginning then get to administrator

Catacode with interactive environments so you don’t have to install infrastrures because it is an online shell
Local infrastructure can bog down the learning process so online environments are useful
K3d is another good option for running your cluster locally.  
    https://k3d.io/v5.6.0


Quantum Jazz