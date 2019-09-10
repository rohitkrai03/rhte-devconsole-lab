## Overview of Developer Perspective and first steps


### Overview
- OpenShift Developer Console adds an alternative perspective in the OpenShift UI that will sit beside the admin console. 

- The new developer perspective - 
  - Adds Curated workflows specific to developer use cases.
  - Provides a **Topology** view that shows a visual representation of all the applications within a project, their build status, and the components and services associated with them
  - Integrates serverless capabilties using **Knative Serving Operator** into these workflows. 
  - Integrates the ability create and visualise Tekton Pipelines using **Openshift Pipelines Operator**.
  - Integrates the ability to create workspaces and edit application code using **Ecplipse Che** or **Codeready Workspace**.


### Instructions

- After logging in to the console, you will see the **Dashboard** page which is default landing page of **Administrator** perspective. 

- Switch to **Developer** perspective.
  - You will see the perspective switcher on the top of the navigation menu showing **Administrator** as current perspective.
  - Click on the switcher to open a dropdown with all available perspectives.
  - Select the **Developer** option from the dropdown.

- You will be redirected **Topology** view which is the default landing page of **Developer** perspective.
  - You will be in the context of `default` project.
  - If there no workloads in your project **Topology** view defaults back to **+Add** page as an empty state.

- Create a new project that you'll use to import new applications.
  - Just below the masthead header, there is a secondary masthead which has **Project** ad **Application** dropdown selectors.
  - Click on the **Project** dropdown and select **Create Project** option.
  - Enter a unique name for the **Name** field `rhte-project`. Optionally, add the **Display Name** and **Description** details for the Project.
  - Click **Create**.
  - A new project `rhte-project` will be created and set as your current context.



Next Lab: [3 - Import an application using Git Import Flow](./git-import.md)<br>
[Home](./README.md)
