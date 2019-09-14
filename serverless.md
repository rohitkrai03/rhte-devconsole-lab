## Create a serverless application using Knative Serving Operator

### Instructions

- On the **Add** page select the **Container Image** option to go to the **Deploy Image** flow again but with the serverless feature enabled.
  - All of the import flows now have a new **Serverless** section added with a `Scale to 0` checkbox option and Tech Preview Badge.

- In the **Image Search** section,
  - Enter `rohitkrai03/tag-portal-v1` into the search bar and press `Enter`.

- Once the image is succesfully pulled from the registry you'll be able to see the details of the docker image below the search bar. Verify the image details.

- Fields in the **General** section below the image search result will be auto populated based on the docker image data.
  - **Application** - *Adds `part-of` label to all the resources to create an application grouping*.
    - The first item in the **Application** dropdown `rhte-app-group-1` is auto selected since there are more than one application grouping.
    - Select `rhte-app-group-2` from the **Application** dropdown.
  - **Name** - *A unique name for the application*
    - This field is auto-populated with `tag-portal-v1` based on the image name.
    - Change the auto-populated **Name** field from `tag-portal-v1` to `tag-portal-v1-serverless`

- In the **Serverless** section, check the `Enable scaling to zero when idle` checkbox.

- **Advanced Options** 
  - The checkbox for **Create a route to the application** is checked by default and a route will be created for the application. You can uncheck it if no route is needed. Keep it checked for the purpose of this lab session.

  - **Serverless** applications have a different set of **Advanced Options**.
    - The **Deployment Configuration** option is removed since the **Configuration** resource maintains the desired state for your deployment instead of a **DeploymentConfig**.
    - The **Scaling** option for **Serverless** enables you to set the autoscaler parameters around pods and concurrency limits.
    - The **Routing** options for **Serverless** applications only have the **Target Port** field to configure. 
    - All the other options in the **Advanced Section** remain the same and are used to fine tune your application deployment.

- Click on **Create** once all required form fields are filled to create the application.
- After successful creation of the application you will be redirected to the **Topology View** where you can check the details of the application created.


- Serverless applications can be identified in topology with a `K` icon on top of the node.
- Click on the application node with the `K` icon that just got created and go to the **Resources** tab.
  - You will see `Revisions`, `Routes`, and `Configurations` resources which are specific to **Serverless** applications.

- Once deployed click on the `Route` icon on the topology node to access the application.
- This application will scale down to 0 pods when there is no traffic and automatically scale up to handle the traffic.


Next Lab: [10 - Install Eclipse Che Cluster](./install-che.md)<br>
[Home](./README.md)
