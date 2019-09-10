## Import an application from Developer Catalog


### Instructions

- On the **Add** page select **From Catalog** flow to open up the **Developer Catalog** which lists all the available **Builder Images** and **Service Templates**

- On the **Developer Catalog** page search for `python`.

- Click on the **Python** card from the search results. A sidebar showing details of the selected builder image opens up on the right side.

- Click on the **Create Application** button on the sidebar to open the **Source to Image** form.

- In the **Source to Image** form,
  - In the **Builder** section,
    - **Builder Image** is auto selected to `Python` version `3.6`. *You can leave it as it is.*
  
  - In the **Git** section,
    - Click on the **Try Sample** option under the **Git Repo URL** field to auto populate the git fields using the metadata from the selected `Builder Image`.
  
  - Fields in the **General** section will be auto populated based on the builder image data.
    - **Application** - *Adds `part-of` label to all the resources to create an application grouping*.
        - Since, you created the `rhte-app-group-1` grouping in the previous lab it is auto selected in the dropdown for you this time. *You can leave it as it is.*
    - **Name** - *A unique name for the application*
      - This field is auto-populated with `python` based on the metadata from the builder image.
      - Change the auto-populated **Name** field from `python` to `django-app`

  - **Advanced Options** 
    - The checkbox for **Create a route to the application** is checked by default and a route will be created for the application. You can uncheck it if no route is needed. Keep it checked for the purpose of this lab session.

    - All the other **Advanced Options** are same as the **Git Import Flow** and can be used to fine tune the configuration of your deployed application.


- Click on **Create**.
- After successful creation of the application you will be redirected to the **Topology View** where you can check the details of the application created.


Next Lab: [6 - Import an application from Git and build using Dockerfile](./dockerfile.md)<br>
[Home](./README.md)
