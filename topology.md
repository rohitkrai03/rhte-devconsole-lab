## Introduction to Topology View


### Overview
**Topology** view provides an overview of the current or active project (e.g. any project selected in the project dropdown). It visually represents the applications present in the project in the form of donut shaped nodes. On clicking a node, a sidebar opens that provides the overview of the application and also shows the details of the application resources like pods, build, etc. Also the nodes have various decorators that are used for checking the build status, opening the application URL, etc. 

- By default the **Developer Console** opens up on the **Topology** view, but you can also navigate to the **Topology** view by selecting the **Topology** option from the Navigation sidebar present on the left side of the page.


### Instructions

- In the **Topology** view, from the **Project** dropdown select the desired project. Select {} for this session.

- From **Application** dropdown select the desired application group. Select {} for this session.

- An **Application Group** is represented visually as a white bubble behind the nodes.

- Click on {} node to open the application sidebar.

  - **Overview Tab**

    - In this tab application details like name, project name, labels, annotations etc are shown.
    - Using the arrows on the right side of the pod donut, you can scale the pods up/down. For serverless applications, the pod scales down to zero when idle and scales up based on the traffic.
    - Under **Annotations** the number of annotations and a pencil icon are shown and by clicking on it a modal is opened. Using this modal you can add or remove annotations.  


Next Lab: [8 - Create a serverless application using Knative Serving Operator](./serverless.md)<br>
[Home](./README.md)