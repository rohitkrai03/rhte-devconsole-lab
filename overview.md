## Overview and Intro to Developer Perspective

OpenShift Developer Console adds a new developer perspective to the default web console that comes with OCP 4.2+. The original web console that came deployed on openshift cluster was very admin centric and often seemed very confusing for a simple developer workflow like importing a git repository and building the application that gets deployed on openshift. So, the new developer perspective adds curated developer workflows that makes it easy for a developer to use the console and create/test their applications in openshift seamlessly. Developer perspective also integrates serverless capabilties using Knative Serving Operator into these workflows. It also allows a developer to easily create and visualise their pipelines using Openshift Pipelines that uses Tekton.

- For using developer console login into web console using console master URL with username as admin and password as r3dh4t1!.

- Switch to Developer console by selecting **Developer** option from the dropdown present on the top of the Navigation Sidebar.

- Developer console's landing page is **Topology**. Switch to another page by selecting desired page from the Navigation Sidebar.

- Now let's create a new project that we'll use to import our applications.
  - Click the **Project** dropdown and select *Create Project*.
  - Enter a unique name for the *Name* field `rhte-project`. Optionally, add the *Display Name* and *Description* details for the Project.
  - Click *Create*.
  - A new project `rhte-project` will be created and set as your current context.



Next Lab: [3 - Import an application using Git Import Flow](./git-import.md)<br>
[Home](./README.md)
