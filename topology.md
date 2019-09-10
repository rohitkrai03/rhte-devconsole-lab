## Introduction to Topology View


### Overview
**Topology** view provides an overview of the current or active project i.e any project selected in the project dropdown. It visually represents the applications present in the project in the form of donut shaped nodes. On clicking a node, a sidebar opens that provides the overview of the application and also shows the details of application resources like pods, build etc. Also the nodes have various decorators that are used for checking the build status opening the application URL etc. 

- By default **Developer Console** opens up on **Topology** view, but you can also navigate to **Topology** view by selecting **Topology** option from the Navigation sidebar present on the left side of the page.


### Instructions

- In **Topology** view, from **Project** dropdown select the desired project. Select {} for this session.

- From **Application** dropdown select the desired application group. Select {} for this session.

- An **Application Group** is represented visually as a white bubble covering the nodes.

- Click on {} node to open the application sidebar.

  - **Overview Tab**

    - In this tab application details like name, project name, labels, annotations etc are shown.
    - Using the arrows given beside the pod donut on this tab, you can scale the pods up/down. For serverless applications, the pods scales down to zero when idle and scales up based on the traffic.
    - Under **Annotations** the number of annotations and a pencil icon is shown and by clicking on it a modal is opened using this modal you can add or remove annotations.  


Next Lab: [8 - Create a serverless application using Knative Serving Operator](./serverless.md)<br>
[Home](./README.md)