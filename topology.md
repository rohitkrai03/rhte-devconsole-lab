## Introduction to Topology View


### Overview
**Topology** view provides an overview of the current or active project (e.g. any project selected in the project dropdown). It visually represents the applications present in the project in the form of donut shaped nodes. On clicking a node, a sidebar opens that provides the overview of the application and also shows the details of the application resources like pods, build, etc. Also the nodes have various decorators that are used for checking the build status, opening route of the application, etc. 

- By default the **Developer Console** opens up on the **Topology** view, but you can also navigate to the **Topology** view by selecting the **Topology** option from the Navigation sidebar present on the left side of the page.


### Instructions

- In the **Topology** view, select `rhte-project` project from the **Project** dropdown in secondary masthead.
- From the **Application** dropdown select `rhte-app-group-2`. application group.
  - An **Application Group** is represented visually as a white bubble behind the nodes.
  - You can use the **Application** dropdown to filter the nodes in the **Topology** view.
  
- Click on `flask-app` node to open the application sidebar. On the sidebar, **Overview** tab will be selected by default.

  - **Overview Tab** *This tab shows you the application details like name, project name, labels, annotations, etc.*
    - Click on the up arrow beside the pod donut and scale up the deployment to 2 pods.
    - Select **Edit Annotations** option from the **Actions** dropdown in the top right corner of the **Overview** tab. *A modal will open where you can add or remove annotations. *
    - Click on **Add more** button and enter `app.openshift.io/connects-to` as key and `tag-portal-v1` as value. 

  - **Resources Tab** *This tab shows you the detailed list of all pods, builds, services and routes.*
    - Click on **Start Build** in the **Build** section to trigger a new build.
    - Click on **View Logs** of the freshly started build to view the logs. 
    - Go back to the **Topology** page by clicking on the back button of your browser.


- From the **Application** dropdown select `All Applications`. application group to display all the applications in your project.

- Drag and drop the `flask-app` node outside of the `rhte-app-group-2` app grouping on the grey area of topology graph. 
  - A popup will open asking you to confirm your decision to remove the node from app group.
  - Click on **Remove**. *If an error occurs, try clicking on **Remove** again.*
  - Now you will be able to see the `flask-app` node without any application grouping.

- Click on the `flask-app` node again to open the sidebar.
  - Select **Edit Application Grouping** option from the **Actions** dropdown in the top right corner of the **Overview** tab. *A modal will open where you can select an application grouping from the dropdown or create a new one.*
  - Select **Create Application** from the dropdown on the modal and enter `python-app-group` in the **Application Name** field.

- Close the sidebar by clicking on `x` button on top of the sidebar or on anywhere inside the topology graph area.

- Drag and drop `django-app` node out of `rhte-app-group-1` into `python-app-group`. This will change the application group of `django-app`.
  - A popup will open asking you to confirm your decision to move the node from one app group to another.
  - Click on **Move**. *If an error occurs, try clicking on **Move** again.*
  - Now you will be able to see the `django-app` node in `python-app-group` application grouping.
  
- Hover over the `django-app` node and drag and drop the dashed blue arrow to the `flask-app` node.
  - This will connect the two nodes by adding `app.openshift.io/connects-to` annotation to `django-app`.

- Hover over the connector arrow between `flask-app` and `tag-portal-v1` nodes.
  - Click on the blue delete `icon` that will appear on the connector arrow.
  - A popup will open asking you to confirm your decision to delete the connection from `flask-app` to `tag-portal-v1`.
  - Click on **Remove**.

- You can control the zoom levels and resize the topology graph by using the **Toolbar** on the bottom left corner of the graph.




Next Lab: [9 - Create a serverless application using Knative Serving Operator](./serverless.md)<br>
[Home](./README.md)