---
title: Introduction to Docker
date: "2022-07-16T12:40:32.169Z"
template: "post"
draft: false
slug: "docker"
category: "Devops"
tags:
  - "Web"
# description: "A blog about restful api."
socialImage: "/media/docker.jpg"
---

- [Docker](#docker)
- [Virtual Machines vs Container](#virtual-machines-vs-container)
- [Problems with VM](#problems-with-vm)
- [Advantage of using Containers](#advantage-of-using-containers)
- [Docker Architecture](#docker-architecture)
- [What's a kernel?](#what's-a-kernal?)
- [Development Workflow](#development-workflow)
- [What does Image Contain?](#what-does-image-contain)

![docker.jpg](/media/docker.jpg)

## Docker
Docker is a platform for building, running, and shipping applications in a consistent manner so that if your application works in your development machine, it will function the same in another machine.

What can be the reason behind the application working on my machine does not working on other machines?
- One or more files missing
- Software version mismatch
- Different configuration settings
This is where Docker comes to the rescue.

With docker, you can easily package your application with everything it needs and run it any machine with Docker.

Therefore, if your application uses the specified node version and MongoDB version, then all of them will be present in your package. You may now execute this package on any system that supports Docker. It will undoubtedly function on test and production machines if it functions on your development machine.

![package.png](/media/package.jpg)

If someone joins your team mid-project when you are working in a group. They don't need to spend much time configuring the new computer to run your program. None of these dependencies need to be installed or configured by them.

They only need to instruct Docker to start the program; Docker will then take care of downloading all necessary dependencies inside of a container, an isolated environment.

```
  docker-compose up
```

This isolated environment allows multiple applications to use different versions of some software side by side. So one application may use Node version 14 and another application may use Node version 9. Both these applications can run side by side on the same machine without messing up with one another. This is how docker allows us to consistently run our application on different machines.  There is one more benefit when we are done working with some application we can remove the application and all its dependencies in one go.


## Virtual Machines vs Container
One of the questions that often comes in is how the container is different with the VM.


We could, for instance, have a mac and run two virtual computers on it. Windows is used on one, while Linux is used on the other. What is the best way to do that? use a program named Hypervisor. Simply put, the software we use to construct and maintain virtual computers is called a hypervisor. 

![mac-hypervisor.jpg](/media/mac-hypervisor.jpg)

There are many hypervisors available out there like:
- VirtualBox
- VMware
- Hyper-v (Windows Only)

So, what are the advantages of using Virtual Machines?
For us developers, we can run applications in isolation.

### Problems with VM
- Each VM needs a full-blown OS
- Slow to start
- Resource intensive

### Advantage of using Containers
- Allow running multiple apps in isolation
- Are lightweight
- Use OS of the host
- Start quickly
- Need less hardware resources

## Docker Architecture

Docker uses a client-server architecture. So, it has a client component that talks to the server component with the rest API. The server also called the DOCKER ENGINE sits in the background and tasks care of building and running the docker container.

![docker-architecture.jpg](/media/docker-architecture.jpg)

Technically a container is just a process like other processes running on our computer. As we already know, unlike virtual machines a container does not contain a full-blown operating system. Instead, all containers share the same Operating System of the host. More accurately all containers share the same kernel of the host. 

![process-in-container.jpg](/media/process-in-container.jpg)

# What's a kernel?

A kernel is the core of the Operating System. It's like the engine of the car. It's the part that manages applications and hardware resources like memory and CPU.

Every OS has its own kernel and this kernel has different APIs. That's why we can not run Windows applications on Linux. Because under the hood this application needs to talk to the kernel of the underlying OS.

![kernal.jpg](/media/kernal.jpg)

So, on the Linux machine, we can only run the Linux container because this container needs Linux.

But, on Windows, we can run both Windows and Linux containers. Because window 10 now shifts to the custom-based Linux kernel. 

Mac OS has its own kernel which is different from Linux and Windows kernels and this kernel does not have native support for container applications. So, docker on mac uses a lightweight Linux VM to run Linux containers.


## Development Workflow

First of all, we take an application and then dockerize it which means we make a small change so that it can be run by docker. 

How?
- we just add a dockerfile to it. 

A dockerfile is a plain text file that stores instructions to package that application into an image. And this image contains everything that our application needs to run.

![application-image.jpg](/media/application-image.jpg)

### What does Image Contain?
- A cut-down OS
- A runtime environment
- Application files
- Third-party libraries
- Environment variable

Once we have the image we tell the docker to start the container using the image. So, a container is just the process but it is a special kind of process because it has its own file system which is provided by the image. 


So, the application gets loaded inside of the container or process and this is how we run our application locally on our development machine. 

So, instead of directly launching the application and running it inside of the typical process we tell docker to run it inside of the container.

![docker-run.jpg](/media/docker-run.jpg)

So, here is the beauty of docker:
Once we have the image we can push it to the Docker registry like the Docker hub. Docker hub to Docker is just like GitHub to git. Docker hub is the storage that anyone can use. So, once our application is on the docker hub we can run it on any application that runs docker.