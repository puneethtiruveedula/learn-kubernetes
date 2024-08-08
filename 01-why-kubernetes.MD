# Why to use Kubernetes?

![Kubernetes Logo](https://cdn-images-1.medium.com/max/2000/1*d9MXw4wPVrLXhgG6eaP-pg.png)


Let’s start with a question. Would you deploy an Elasticsearch cluster for your company’s production environment using Docker on a single machine with several containers in it, just like you do on your local machine when you are using or learning Docker? Of course not! Why not? Mainly because you want to keep your job, don’t you? So, what’s wrong with this approach? Let’s list out some arguments below:

* The containers (Elasticsearch instances) would be running on a single machine. What would happen if this machine crashes?

* If some of those containers are down, how would you know about that? Besides, you would have to bring them up again by yourself (issuing the “docker run” command), and that is not funny when it’s 3:00 AM.

Actually, even if you run these containers on separate machines, you would still have to manage them one by one by yourself.

Of course that you could address these issues above by running a systemd unit for each container on each machine that would ensure the containers would always be running. However, again, what if the machines crash? Who would have to start new containers in other machines in order to bring the Elasticsearch cluster up again? That’s correct, you! However, if Kubernetes were managing these containers for you, it would be in charge of relaunching them again on the most appropriate machines available in the Kubernetes cluster (for example, the ones that are less overloaded).

Well, that might be arguments enough, but there are still much more. Forget about the Elasticsearch thing and imagine now that you are running a stateless web application using Docker containers. How would you deploy a new application release? Manually removing containers and launching new ones based on the new Docker image? Really, as a DevOps Engineer (or whatever you wanna call it), does it sound good to read the word “manually”? I bet you know the key for the DevOps culture is automation.

I think you are already convinced that, for production purposes, running and managing (or… **orchestrating**) container life cycles by yourself may not be a good idea. So, who is going to do this for you? That’s right, Kubernetes! That’s why we call tools like **Kubernetes, Docker Swarm, Amazon ECS** and others as **Container Orchestration Tools**.

Kubernetes has a set of great features that are very useful specially when it comes to production environments:

* Container replication among different nodes to ensure high availability.

* Automatic container recovery when it gets down for whatever reason.

* Container auto-scaling based on Kubernetes cluster metrics such as CPU consumption.

* Rolling deployments and deployment rollbacks.

* Service Discovery. That’s neat for deploying Microservices!

* Load Balancing and Volume management.

* Container health checks.

* Logical resources isolation using Namespaces.

* Controlling resources and quotas by Namespaces.

* Managing cron jobs.
