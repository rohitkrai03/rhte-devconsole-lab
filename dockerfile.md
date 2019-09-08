## Import an application from Git and build using Dockerfile

- On **Add** page select **From Dockerfile** flow.
- In this flow, enter this URL `https://github.com/rohitkrai03/flask-dockerfile-example` in **Git Repo** field.
- Enter the dockerfile path relative to **Context Dir** in the **Dockerfile Path** field under **Docker** section. This field is auto-populated by value *Dockerfile*. Do not change the value of this field for now.
- Enter the port number that the docker container exposes in the **Container Port** field. The application will run on this port. Use port number *5000* for this flow. 
- Follow the same steps as git import flow to fill out rest of the form fields.
- Click on **Create** button to create the application.   