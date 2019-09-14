## Install Ecplise Che Cluster

### Instructions

- Create a new project to install the **Che** cluster.
  - Click on the **Project** dropdown and select **Create Project** option.
  - Enter `rhte-che` in the **Name** field.
  - Click **Create**.
  - A new project `rhte-che` will be created and set as your current context.


- Install the **Eclipse Che** operator
  - Switch to the **Administrator** perspective using the perspective switcher on the nav menu.
  - Navigate to **Operators** -> **Operatorhub** from the navigation menu. 
  - In the search field enter `Eclipse Che` and click on the **Eclipse Che** operator. *A sidebar showing details of the selected **Operator** opens up on the right side.*
  - Click **Install** on the sidebar.
  - Click **Subscribe** on the subscription page after verifying the selected project is `rhte-che`. Do not change any default values.
  - Verify that it gets installed succesfully on the **Installed Operator** page that you get redirected to. (It may take a few seconds).
  - Once installed successfully, click on the **Ecplise Che** operator from the list. It will take you to the **Operator Details** page.
  - Click on the **Eclipse Che Cluster** tab.
  - Click on the **Create Che Cluster** button.
  - In the YAML editor, change the following parameters in the default generated yaml code - 
    - `tlsSupport: false` -> `tlsSupport: true`
    - `selfSignedCert: false` -> `selfSignedCert: true`
  - Click **Create** after updating the above parameters. *It takes about 5 minutes to configure and deploy all the workloads in a **Che Cluster***.

- Switch back to **Developer Perspective**. You can see the new deployments getting created on the **Topology** view for the **Che Cluster**.

Next Lab: [11 - Connect a database service to an application using Service Binding Operator](./service-binding.md)<br>
[Home](./README.md)
