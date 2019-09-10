## Create Che workspace with application sourcecode using Codeready Workspaces/Eclipse Che

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

- Switch back to **Developer Perspective**. You can see the deployments on the **Topology** view for the **Che Cluster**.

- Check if `Che` and `Keycloak` deployments are successful.
  - Click on the **Route** icon of `Keycloak` node from **Topology**.
    - Allow self signed SSL certificates in the browser. Once allowed you can see the `Keycloak` dashboard UI.
    - Close the tab.
  - Click on the **Route** icon of `Che` node from **Topology**.
    - Allow self signed SSL certificates in the browser.
    - Once allowed, you can see the login screen of Che.
    - Login using your Openshift Credentials. 
      - User - `admin`.
      - Password - `r3dh4t1!`.
    - Allow the permission access to your user data.
    - Add your details to create a new user in **Che**. *Do change pre-filled `admin` username in user creation*
    - After successful authentication you will be redirected to **Che** dashboard page.
    - Close the tab.

- Copy the **Ruute** URL of `che` from the **Topology** view.

- Create a **ConsoleLink** with the link to **Che** dashboard.
  - Go to **+Add** page and select **YAML** option to go to the **Import YAML** flow.
  - In the YAML editor enter following **OperatorSource** - 
    ```yaml
    apiVersion: console.openshift.io/v1
    kind: ConsoleLink
    metadata:
      name: che
    spec:
      applicationMenu:
        imageURL: >-
          https://raw.githubusercontent.com/eclipse/che-website/master/che/images/ico/96x96.png
        section: Red Hat Applications
      href: 'https://che.openshift.io'
      location: ApplicationMenu
      text: Che Dashboard
    ```
  - Change the value of **href** from `https://che.openshift.io` to the previously copied **Ruute** URL of `che`. 
  - Click on **Create** button to create the **ConsoleLink** resource.
  - Refresh the broswer page.
  - Very that a new link is added to the **Application Launcher** menu from the right side of primary masthead.

- Go back to the **Topology** view.
- Click on the **Edit Source Code** icon of `flask-app` node.
- It will redirect you to the **Che Workspace Factory** URL and trigger the creation of your workspace with source code of the deployed application.
- Workspace creation usually takes a few minutes to complete.
- Once completed your new workspace will be started.
  - If you see an error on the page with a URL, copy that URL and open it in the broswer. Allow the self singed certificates in the browser and you'll be able to start your workspace.

Next Lab: [11 - Creating and managing pipelines using Openshift Pipelines](./tekton.md)<br>
[Home](./README.md)
