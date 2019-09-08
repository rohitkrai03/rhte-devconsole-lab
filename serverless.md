## Create a serverless application using Knative Serving Operator

- Now that you've created a bunch of applications using various import flows of Developer Console, let's explore the serverless options that comes integrated with the Developer Console.
- To be able to create a serverless application you need to install **Knative Serving Operator**.
- Installing **Knative Serving** operator
  - Switch to **Admin Perspective** using the perspective switcher on the nav menu.
  - Go to **Operatorhub** tab and search for **Knative**.
  - Install the operator and create its subscription.
  - Verify that it gets installed succesfully on **Installed Operator** page that you get redirected to. (Its takes a few seconds)

- Switch back to **Developer Perspective** and go to **+Add** page.
- Choose any of the import flows Git/Container Image/S2I
- In all above flows you can see a new **Serverless** section added with a `Scale to 0` checkbox option and Tech Preview Badge.
- For the purpose of this lab session let's choose the **Container Image** flow again but with the serverless option checked.
- Enter the same image name from earlier `rohitkrai03/tag-portal-v1`.
- Once the image is successfully pulled from the image registry, it will again autopopulate the fields in **General** section.
- Change the **Name** of the application from `tag-portal-v1` -> `tag-portal-v1-serverless`.
- In the **Serverless**, check the `Enable scaling to zero when idle` checkbox.

- **Advanced Options** for **Serverless** applications are a little different than regular applications.
  - There is no **Deployment Configuration** option since **Configuration** resource maintains the desired state for your deployment instead of a **DeploymentConfig**.
  - The **Scaling** option changes for **Serverless** to set the autoscaler parameters around pods and concurrency limits.
    - **Min Pods** - The lower limit for the number of pods that can be set by autoscaler. If not specified defaults to 0.
    - **Max Pods** - The upper limit for the number of pods that can be set by autoscaler.
    - **Concurrency Target** - Defines how many concurrent requests are wanted per instance of the application at a given time (soft limit) and is the recommended configuration for autoscaling. If not specified, will be defaulted to the value set in the cluster config.
    - **Concurrency Limits** - Limits the amount of concurrent requests allowed into one instance of the application at a given time (hard limit), and is configured in the revision template. If not specified, will be defaulted to the value set in the cluster config.
  - All the other options in the **Advanced Section** remain same and are used to fine tune application deployment.

- Click on create once all required form fields are filled to create the application.
- After successful creation of the application you will be redirected to the **Topology View** where you can check the details of the application created.

- Serverless applications can be identified in topology with a `K` icon on the top of the node.
- Click on the application node with the `K` icon that just got created and go to the **Resources** tab.
  - You will see `Revisions`, `Routes` and `Configurations` resources instead of `Pods`, `Builds`, `Services` and `Routes` that you see with regular import flows.
  - This is because in case of a **Serverless** application, **Knative Serving** resources get created that are provided by the operator.

- Once deployed click on the `Route` icon on the topology node to access the application.
- This application witll scale down to 0 pods when there is no traffic and automatically scale up to handle the traffic.