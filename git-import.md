## Import an application using Git Import Flow

- In **Import from git** form, enter url of the git repo where the application that needs to be created exists. In this lab session for git import flow use `https://github.com/nodeshift-starters/react-web-app`.
- If you want to use another branch rather than master or your git repo doesnt have a master branch enter the specific branch or tag or commit in the Git reference field. This step can be skipped for now.
- Enter the path of the application directory in Context Dir field if there are multiple applications in the repo. This step can be skipped for now.
- Create secret from the Source Secret dropdown by selecting the Create New Secret option if the provided git repo is private. This step can be skipped for now.
- Select builder image from the options provided. In this lab session for git import flow select **Modern Webapp** option.
- You can change the builder image version from **Builder Image Version** dropdown. Leave it as it is for now.
- The active project is pre-selected where the application will be created, it can be changed by going back and selecting another project from Projects dropdown.
- If there are no application groups in your current project, option to create a new one will be auto selected and populated.
- If there are application groups in the current project, first one will be auto selected in the dropdown. You can select one or create a new application group.
- Enter a unique name for the application in the Name field. This field will be auto-populated, edit the field value if the application with the same name already exists.
- Check the **Create a route to the application** option to expose the application at a public URL. Keep the route option checked for git import flow in this lab session.
- Select the desired Advanced option to customise the build, deployment and workloads of the application. This step can be skipped for now.
   - **Routing** 
     - Using this option you can customise the route to the application and also make the route secure by adding security certificates using one the TLS termination types.
   - **Build Configuration**
     - Using this option you can customise the build config by adding the neccessary triggers and environment variables.
   - **Deployment Configuration**
     - Using this option you can customise the deployment config by adding the neccessary triggers and environment variables.
   - **Scaling**
     - Using this option you can set minimum number of pods that will be deployed initially.
   - **Resource Limits**
     - Using this option you can set the minimum and maximum amount of CPU and Memory container is allowed to use.
   - **Labels**
     - Using this option you can add labels to the application.

- Click on **Create** once all required form fields are filled to create the application.
- After successful creation of the application you will be redirected to the **Topology View** where you can check the details of the application created, access the connected resources created for the application, check the build status, access route of the application etc.



Next Lab: [4 - Deploy an Image from Dockerhub](./deploy-image.md)<br>
[Home](./README.md)
