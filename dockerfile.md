## Import an application from Git and build using Dockerfile

- Go to the **+Add** page.
- On **+Add** page select **From Dockerfile** option to go to the **Import from Dockerfile** flow.

- In **Import from Dockerfile** form,

  - In **Git** section,
    - Enter `https://github.com/rohitkrai03/flask-dockerfile-example` in **Git Repo URL** field.

  - In **Dockerfile** section,
    - **Dockerfile Path** field is auto-populated with `Dockerfile`. You can change this value if your dockerfile exists in a directory other than root. For the purpose of this session do not change it.
    - **Container Port** field is auto-populated with `8080` as default target port.
    - Change the **Container Port** field from `8080` to `5000`. *This value should be equal to the value of `EXPOSE` in the dockerfile.*

    - Fields in the **General** section will be auto populated based on the git repo URL.
      - **Application** - *Adds `part-of` label to all the resources to create application grouping*.
        - First item in the **Application** dropdown `rhte-app-group-1` is auto selected since there are more than one application grouping.
        - Select `rhte-app-group-2` from the **Application** dropdown.
      - **Name** - *A unique name for the application*
        - This field is auto-populated with `flask-dockerfile-example` based on the git repo.
        - Change auto-populated **Name** field `flask-dockerfile-example` to `flask-app`

    - **Advanced Options** 
      - Checkbox for **Create a route to the application** is by default checked and a route will be created for the application. You can uncheck it if no route is needed. Keep it checked for the purpose of this lab session.

      - All the other **Advanced Options** are same as **Git Import Flow** and can be used to fine tune the configuration of deployed application.

- Click on **Create** once all required form fields are filled to create the application.
- After successful creation of the application you will be redirected to the **Topology View** where you can check the details of the application created. 


Next Lab: [7 - Introduction to Topology View](./topology.md)<br>
[Home](./README.md)
