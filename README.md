# Red Hat Tech Exchange Lab - Hands on with Developer Console on OpenShift

This page contains a series of instructios for hands-on lab on OpenShift Developer Console conducted during Red Hat Tech exchange.


## Overview
OpenShift Developer Console adds a new developer perspective to the default web console that comes with OCP 4.2+. The original web console that came an openshift cluster was very admin centric and often seemed very confusing for a simple developer workflow like importing a git repository and building the application that gets deployed on openshift. So, the new developer perspective adds curated developer workflows that makes it easy for a developer to use the console and create/test their applications in openshift seamlessly. Developer perspective also integrates serverless capabilties using Knative Serving Operator into these workflows. It also allows a developer to easily create and visualise their pipelines using Openshift Pipelines that uses Tekton.


## Session Abstract
Openshift 4 has made Kubernetes even better. The new Developer Console provides a fresh perspective that supports the developer mindset and adds curated workflows for developers while still working with the Admin console for the Operators. Adding Knative Serving which directly integrates into the developer workflows simplifies the experience further. The latest version of OpenShift now supports Knative and this hands-on lab will walk you through everything you need to know. We will start with going through some of the most common developer workflows and how developer console import flows improves that experience, after that we'll move on to activating Knative support in OpenShift which will extend the import flows letting us create Serverless applications seamlessly. We will go through the new Topology view that helps a developer visualise, understand and interact with all the applications in his namespace at a glance. We will also go through basics of Tekton Pipelines and how developer console can help visualise and build your pipelines. Come see what the new OpenShift Developer console has to offer.


### Presenter/Lab Developer - Rohit Rai, Senior Software Engineer - Developer Tools, Red Hat



## Labs Index

* [0 - Introduction and Prerequisites](./intro.md)<br>
* [1 - Login into OpenShift Console](./login.md)<br>
* [2 - Switch to Developer Perspective](./perspective.md)<br>
* [3 - Import an application using Git Import Flow](./git-import.md)<br>
* [4 - Deploy an Image from Dockerhub](./deploy-image.md)<br>
* [5 - Import an application from Git and build using Dockerfile](./dockerfile.md)<br>
* [6 - Import an application using S2I from Developer Catalog](./s2i.md)<br>
* [7 - Create a serverless application using Knative Serving Operator](./serverless.md)<br>
* [8 - Create an application that binds to a database using App Binding Operator](./app-binding.md)<br>
* [9 - Intro to Openshift Pipelines](./tekton.md)<br>
* [10 - Wrap up](./wrap.md)<br>
