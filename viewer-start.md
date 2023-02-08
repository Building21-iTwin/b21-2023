# Steps to setup a local viewer

## Install Pre-requisites

1. Install Docker desktop
1. Install the Dev Container Extension in VSCode
    - Search for `ms-vscode-remote.remote-containers`

## Initialize the Viewer

1. In the terminal, run the following command:

    ```npx create-react-app your-app-name --template @itwin/web-viewer --scripts-version @bentley/react-scripts```
    - This will generate a new application based on the iTwin Viewer React component.
    - By default, the viewer will be stored in a directory called your-app-name
1. Run `cd your-app-name` to move into the app directory
1. In the terminal, run `mkdir .devcontainer`
1. Setup the DevContainer configuration by copying the following files into a `.devcontainer` folder
    - [./devcontainer/devcontainer.json](./devcontainer/devcontainer.json)
    - [./devcontainer/Dockerfile](./devcontainer/Dockerfile)
1. In VSCode, press `Crtl+P` to open the command palette and search `Dev Containers: Reopen folder locally`.
1. Once the container finishes initializing, open the terminal and run `npm install`
1. [Register an application](https://developer.bentley.com/tutorials/web-application-quick-start/#3-register-an-application)
1. Open the .env file
1. Enter the appropriate values for:
    - IMJS_AUTH_CLIENT_CLIENT_ID: Enter the ClientID for the client you registered during the Register a Client step
    - IMJS_AUTH_CLIENT_REDIRECT_URI: Enter the Redirect URI for the client you registered during the Register a Client step
    - IMJS_AUTH_CLIENT_LOGOUT_URI: Enter the Post Logout Redirect URI for the client you registered during the Register a Client step
    - IMJS_AUTH_CLIENT_SCOPES: Enter the Scopes for the client you registered during the Register a Client step
    - IMJS_ITWIN_ID: Enter the iTwinId that was generated during the Create an iModel step
    - IMJS_IMODEL_ID: Enter the iModelID that was generated during the Create an iModel step
1. In the terminal window, enter npm start. This will serve the application with live reloading.
