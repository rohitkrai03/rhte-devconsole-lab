## Create Che workspace with application sourcecode using Codeready Workspaces/Eclipse Che

### Instructions

- In the **Topology** view, select `rhte-che` project from the **Project** dropdown in secondary masthead.

- Check if `Che` and `Keycloak` deployments are successful.
  - Click on the **Route** icon of the `Keycloak` node from **Topology**.
    - Allow self signed SSL certificates in the browser. Once allowed you can see the `Keycloak` dashboard UI.
    - Close the tab.
  - Click on the **Route** icon of `Che` node from **Topology**.
    - Allow self signed SSL certificates in the browser.
    - Once allowed, you can see the login screen of Che.
    - Login using your Openshift Credentials. 
      - User - `admin`.
      - Password - `r3dh4t1!`.
    - Allow the permission access to your user data.
    - Add your details to create a new user in **Che**. *You must change the pre-filled `admin` username in user creation*
    - After successful authentication you will be redirected to the **Che** dashboard page.
    - Close the tab.

- Copy the **Route** URL of `che` from the **Topology** view.

- Create a **ConsoleLink** with the link to **Che** dashboard.
  - Go to the **+Add** page and select the **YAML** option to go to the **Import YAML** flow.
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
  - Change the value of **href** from `https://che.openshift.io` to the previously copied **Route** URL of `che`. 
  - Click on the **Create** button to create the **ConsoleLink** resource.
  - Refresh the broswer page.
  - Verify that a new link is added to the **Application Launcher** menu (3x3 grid icon) from the right side of primary masthead.

- Switch the project to `rhte-project` from project dropdown selector.
  
- Go back to the **Topology** view.
- Click on the **Edit Source Code** icon of `flask-app` node.
- It will redirect you to the **Che Workspace Factory** URL and trigger the creation of your workspace with the source code of the deployed application.


- Workspace creation usually takes a few minutes to complete.
- Once completed your new workspace will be started.
  - If you see an error on the page with a URL, copy that URL and open it in the broswer. Allow the self singed certificates in the browser and you'll be able to start your workspace.

Next Lab: [13 - Wrap Up](./wrap.md)<br>
[Home](./README.md)
