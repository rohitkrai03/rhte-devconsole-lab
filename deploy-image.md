## Deploy a container image using Deploy Image flow

### Instructions

- Go to the **+Add** page using the navigation menu.

- On the **Add** page select the **Container Image** option to go to the **Deploy Image** flow.

- In the **Image Search** section,
  - Enter the name of the image that you want to pull from a public image registry in the **Image Search** field.
  - For the purpose of this lab session enter `rohitkrai03/tag-portal-v1` into the search bar and press `Enter` or click on the `Search` button on the right.
  - *Note - Currently we only support Dockerhub and Openshift Image Registry*

- Once the image is succesfully pulled from the registry you'll be able to see the details of the docker image below the search bar. Verify the image details.

- Fields in the **General** section below the image search result will be auto populated based on the docker image data.
  - **Application** - *Adds `part-of` label to all the resources to create an application grouping*.
    - Since, you created `rhte-app-group-1` grouping in the previous lab it is auto selected in the dropdown for you this time.
    - Click on the dropdown and select the `Create Application` option.
    - Enter `rhte-app-group-2` in the **Application Name** field.
  - **Name** - *A unique name for the application*
    - This field is auto-populated with `tag-portal-v1` based on the image name. You can leave the auto-populated value as it is for this lab. 

- **Advanced Options** 
  - The checkbox for **Create a route to the application** is checked by default and a route will be created for the application. You can uncheck it if no route is needed. Keep it checked for the purpose of this lab session.

  - All the other **Advanced Options** are same as the **Git Import Flow** and can be used to fine tune the configuration of your deployed application.
    
  - Select the **Scaling** option from the list of **Advanced Options**.
    - Increase the number of replicas to `2` using the number spinner input field. *This will increase the minimum number of pods deployed*

- Click on **Create**.
- After successful creation of the application you will be redirected to the **Topology View** where you can check the details of the application created.


Next Lab: [5 - Import an application from Developer Catalog](./s2i.md)<br>
[Home](./README.md)
