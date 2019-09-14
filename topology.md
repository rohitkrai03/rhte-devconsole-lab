## Introduction to Topology View


### Overview
**Topology** view provides an overview of the current or active project (e.g. any project selected in the project dropdown). It visually represents the applications present in the project in the form of donut shaped nodes. On clicking a node, a sidebar opens that provides the overview of the application and also shows the details of the application resources like pods, build, etc. Also the nodes have various decorators that are used for checking the build status, opening the application URL, etc. 

- By default the **Developer Console** opens up on the **Topology** view, but you can also navigate to the **Topology** view by selecting the **Topology** option from the Navigation sidebar present on the left side of the page.


### Instructions

- In the **Topology** view, from the **Project** dropdown select {} project.
- From **Application** dropdown select {} application group.
- An **Application Group** is represented visually as a white bubble behind the nodes.
- Click on {} node to open the application sidebar.

  - **Overview Tab**

    - In this tab application details like name, project name, labels, annotations etc are shown.
    - Using the arrows on the right side of the pod donut, you can scale the pods up/down. For serverless applications, the pod scales down to zero when idle and scales up based on the traffic. Try to scale up {} pods. 
    - Under **Annotations** the number of annotations and a pencil icon are shown and by clicking on it a modal is opened. Using this modal you can add or remove annotations. For connecting {} to {} add `KEY` as `app.openshift.io/connects-to` and `VALUE` as {}. 

  - **Resources Tab**

    - In this tab you can see the detailed list of all pods, builds, services and routes. 
- Close the sidebar by clicking on `x` button on top.
- Now, hover over the {} node and drag and drop the dashed blue arrow to the node you want to connect to.
- Select `all applications` from the application dropdown.
- Now, drag and drop the node to {} application group. This is how you can regroup the applications.




Next Lab: [9 - Create a serverless application using Knative Serving Operator](./serverless.md)<br>
[Home](./README.md)