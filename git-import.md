## Import an application using Git Import Flow

### Instructions

- From the **Empty State** page on **Topology** select **From Git** option to go to the **Git Import** flow.

- In **Import from git** form,
  - The active project `rhte-project` is pre-selected where the application will be created, it can be changed by going back and selecting another project from **Projects** dropdown in secondary masthead.
  
  - In **Git** section,
    - Enter URL of the git repository in **Git Repo URL** field. For the purpose of this session use `https://github.com/pmacik/nodejs-rest-http-crud`.
    
    - You can click on **Show Advanced Git Options** to add more information about the git repo. *Note - For this particular lab you can skip this step*.
      - You can use **Git Reference** field to specify specific branch or tag or commit.
      - You can use **Context Dir** field to specify a context directory for the build.
      - If you want to import a private repo, you can use **Source Secret** dropdown select a source secret or create a new one.
  
  - In **Builder** section, select **Node.js** builder image from the available builder images.
    - Change the builder image version from **Builder Image Version** dropdown to `latest`.

  - Fields in the **General** section below the **Builder** section will be auto populated based on the git repo URL.
    - **Application** - *Adds `part-of` label to all the resources to create application grouping*.
      - If there are no application groups in your current namespace, option to create a new one will be auto selected and populated based on the git repo URL.
      - If there are application groups in the namespace, first one will be auto selected in the dropdown. You can select one or create a new application group.
      - Change auto-populated **Application Name** field from `react-web-app-app` to `rhte-app-group-1`
    - **Name** - *A unique name for the application*
      - This field will be auto-populated based on the git repo URL, edit the field value if the application with the same name already exists.
      - Change auto-populated **Name** field `nodejs-rest-http-crud` to `nodejs-crud-app`

  - **Advanced Options** 
    - Checkbox for **Create a route to the application** is by default checked and a route will be created for the application. You can uncheck it if no route is needed. Keep it checked for the purpose of this lab session.
    - You can select the desired advanced option from the list to customise the route, build, deployment and workloads of the application.
       - **Routing** 
         - Using this option you can customise the **Route** to the application and also make the route secure by adding security certificates using one the TLS termination types.
       - **Build Configuration**
         - Using this option you can customise the **BuildConfig** by adding the neccessary triggers and environment variables.
       - **Deployment Configuration**
         - Using this option you can customise the **DeploymentConfig** by adding the neccessary triggers and environment variables.
       - **Scaling**
         - Using this option you can set minimum number of pods that will be deployed initially.
       - **Resource Limits**
         - Using this option you can set the minimum and maximum amount of CPU and Memory container is allowed to use.
       - **Labels**
         - Using this option you can add labels to the application.

  - Click on **Create** once all required form fields are filled to create the application.

- After successful creation of the application you will be redirected to the **Topology View** where you can check the details of the application created and interact with your application.



Next Lab: [4 - Deploy an Image from Dockerhub](./deploy-image.md)<br>
[Home](./README.md)
