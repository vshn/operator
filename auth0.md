# Creating an auth0 application

TriggerMesh authentication is based on [Auth0](https://auth0.com). In order to deploy a TriggerMesh instance properly you need to create an Auth0 application first and get its `clientid` and `clientsecret`.

## Sign up or Login to Auth0

Here are the first three steps to follow:

1. Sign up or login to [auth0](https://auth0.com/auth/login)
2. If it is your first time using Auth0 you will need to create a _Tenant Domain_ as shown in the two snapshots below:
![create a tenant](./images/1.png)
![fill up info about tenant](./images/2.png)

3. If you are already using Auth0, you can create a new tenant for your TriggerMesh instance from the Dashboard view, by clicking on your account down arrow at the top right.
![create a tenant](./images/6.png)

## Create two Applications

You are now ready to create two Auth0 applications. One for the TriggerMesh frontend and one for the TriggerMesh backend.

1. Click on "Create application" button in the Dashboard view.
![create application](./images/3.png)

1. Type an application name and select "Single Page web Applications"
![select application type](./images/4.png)

1. Create a second application of type "Machine to Machine" and note the `Client ID` and `Client Secret` that you will use in the manifest of the TriggerMesh instance.

## Configure the CallBack URLs



