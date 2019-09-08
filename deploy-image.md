## Deploy an Image from Dockerhub

- From the **+Add** page select **Container Image** option to go the **Deploy Image** flow.

- In the **Image Search** field enter the name of the image that you want to pull from a public image registry.
  - For the purpose of this lab session use - `rohitkrai03/tag-portal-v1`
  - Note - Currently we support Dockerhub and Openshift Image Registry

- Once the image is succesfully pulled from the registry you'll be able to see the details of the docker image below the search bar. Verify the image details.

- Fields in the general section below the image search result will be auto populated based on the docker image data.
  - If there are no application groups in your current namespace, option to create a new one will be auto selected and populated based on the docker image name.
  
  - If there are application groups in the namespace, first one will be auto selected in the dropdown. You can select one or create a new application group.
  
  - Enter a unique name for the application in the Name field. This field will be auto-populated based on the docker image name, edit the field value if the application with the same name already exists.

- Checkbox for **Create a route to the application** is by default checked and a route will be created for the application. You can uncheck it if no route is needed. Keep it checked for the purpose of this lab session.

- All the other **Advanced Options** are same as **Git Import Flow** and can be used to fine tune the configuration of deployed application.

- Click on create once all required form fields are filled to create the application.
- After successful creation of the application you will be redirected to the **Topology View** where you can check the details of the application created, access the connected resources created for the application, check the build status, access route of the application etc.