## Import an application using S2I from Developer Catalog

- On **Add** page select **From Catalog** flow to open up the **Developer Catalog** which lists all the available **Builder Images** and **Service Templates**

- On the **Developer Catalog** page search `python`.

- Click on the `Python` card from the search results. A sidebar showing details of the selected builder image opens up on the right side.

- Click on **Create Application** button on the sidebar to open **Source to Image** form.

- In **Source to Image** form,
  - In **Builder** section,
    - **Builder Image** and **Builder Image Version** is auto selected to `Python` and `3.6`. *You can leave it as it is.*
  
  - In **Git** section,
    - Click on **Try Sample** option under **Git Repo URL** field to auto populate the git fields using the metadata from the selected `Builder Image`.
  
  - Fields in the **General** section will be auto populated based on the builder image data.
    - **Application** - *Adds `part-of` label to all the resources to create application grouping*.
        - Since, you created `rhte-app-group-1` grouping in previous lab it is auto selected in the dropdown for you this time. *You can leave it as it is.*
    - **Name** - *A unique name for the application*
      - This field is auto-populated with `python` based on the metadata from builder image.
      - Change auto-populated **Name** field `python` to `django-app`

  - **Advanced Options** 
    - Checkbox for **Create a route to the application** is by default checked and a route will be created for the application. You can uncheck it if no route is needed. Keep it checked for the purpose of this lab session.

    - All the other **Advanced Options** are same as **Git Import Flow** and can be used to fine tune the configuration of deployed application.

- Click on **Create** once all required form fields are filled to create the application.
- After successful creation of the application you will be redirected to the **Topology View** where you can check the details of the application created.


Next Lab: [6 - Import an application from Git and build using Dockerfile](./dockerfile.md)<br>
[Home](./README.md)
