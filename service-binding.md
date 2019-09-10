## Connect a database service to an application using the Service Binding Operator

### Service Binding Operator
The goal of the Service Binding Operator is to enable application authors to import an application and run it on OpenShift with operator-backed services. For example running a database without having to perform manual configuration of secrets, configmaps, etc.

### Instructions

- Install the Service Binding Operator using an OperatorSource
  - Go to the **+Add** page and select the **YAML** option to go to the **Import YAML** flow.
  - In the YAML editor enter the following - 
    ```yaml
    apiVersion: operators.coreos.com/v1
    kind: OperatorSource
    metadata:
      name: redhat-developer-operators
      namespace: openshift-marketplace
    spec:
      type: appregistry
      endpoint: https://quay.io/cnr
      registryNamespace: redhat-developer
    ```
  - Click on the **Create** button to create the OperatorSource resource.
  - Switch to **Administrator** perspective.
  - Navigate to the **Operators** -> **OperatorHub** in the navigation menu.
  - Select **Other** from the list of category filters on the left side and select the **Service Binding Operator** operator.
  - Click **Install** on the sidebar.
  - Click **Subscribe** on the subscription page without changing any default values.
  - Verify that it gets installed succesfully on the **Installed Operator** page that you were redirected to. (It may take a few seconds)

- Install the Database Operator using an OperatorSource
  - Click on the `+` icon in the upper right side of the masthead header to open YAML editor.
  - In the YAML editor enter following - 
    ```yaml
    apiVersion: operators.coreos.com/v1
    kind: OperatorSource
    metadata:
      name: db-operators
      namespace: openshift-marketplace
    spec:
      type: appregistry
      endpoint: https://quay.io/cnr
      registryNamespace: pmacik
    ```
  - Click on **Create** button to create the **OperatorSource** resource.
  - Navigate to the **Operators** -> **OperatorHub** from the navigation menu.
  - Select **Database** from the list of category filters on the left side and select the **PostgreSQL Database** operator.
  - Click **Install** on the sidebar.
  - Click **Subscribe** on the subscription page without changing any default values.
  - Verify that it gets installed succesfully on **Installed Operator** page that you get redirected to. (It may take a few seconds)

- Switch back to the **Developer** perspective.

- You have already imported `nodejs-crud-app` application in **Git Import** flow. This application needs to connect to a `postgresql` database to work properly.

- Create a Database instance for the application
  - Go to **+Add** page and select **YAML** option to go to the **Import YAML** flow.
  - In the YAML editor enter following **OperatorSource** - 
    ```yaml
    apiVersion: postgresql.baiju.dev/v1alpha1
    kind: Database
    metadata:
      name: db-demo
      namespace: rhte-project
    spec:
      image: docker.io/postgres
      imageName: postgres
      dbName: db-demo
    ```
  - Click on **Create** button to create the **Database**.

- Go to the **Topology** view.

- Add correct labels to the application 
  - Now you need to set arbitrary labels on the application's **DeploymentConfig** in order for the **Service Binding Operator** to be able to find the application.
  - Click on `nodejs-crud-app` node in the topology.
  - From the **Actions** menu in the sidebar, select **Edit Labels**.
  - Add `connects-to=postgres environment=demo` labels to the input field in the modal and click **Save**.

- Express an intent to bind the database and the application.
  - Go to **+Add** page and select **YAML** option to go to the **Import YAML** flow.
  - In the YAML editor enter following **OperatorSource** - 
    ```yaml
    apiVersion: apps.openshift.io/v1alpha1
    kind: ServiceBindingRequest
    metadata:
      name: binding-request
      namespace: rhte-project
    spec:
      applicationSelector:
        matchLabels:
          connects-to: postgres
          environment: demo
        group: apps.openshift.io
        version: v1
        resource: deploymentconfigs
      backingServiceSelector:
        group: postgresql.baiju.dev
        version: v1alpha1
        kind: Database
        resourceRef: db-demo
      mountPathPrefix: “”
    ```
  - Click on **Create** button to create the **ServiceBindingRequest**.

- Go back to **Topology** view.
- Once the service binding request is successfully completed, it causes the application to be re-deployed.
- Click on the route icon of `nodejs-crud-app` to check the database connection in the application UI.

Next Lab: [10 - Create Che workspace with application source code using Codeready Workspaces/Eclipse Che](./che.md)<br>
[Home](./README.md)
