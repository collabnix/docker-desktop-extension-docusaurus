# Running Docusaurus as Docker Desktop Extension


### Getting Started


- [Download](https://www.docker.com/products/docker-desktop/) and Install Docker Desktop
- Enable Docker Extensions

<img width="1091" alt="image" src="https://user-images.githubusercontent.com/34368930/174530063-563b9a41-bb97-41a9-bd2d-d66a01fd37dd.png">

- [Download Docker Extension CLI from this link](https://github.com/docker/extensions-sdk/releases/download/v0.2.4/desktop-extension-cli-darwin-arm64.tar.gz)

```
docker extension

Usage:  docker extension [OPTIONS] COMMAND

Manages Docker extensions

Options:
      --socket string   The Desktop extension manager socket

Management Commands:
  dev             Extension development helpers

Commands:
  disable         Disable extensions in Docker Desktop
  enable          Enable extensions in Docker Desktop
  init            Create a new desktop extension
  install         Install a Docker extension with the specified image
  ls              List installed Docker extensions
  rm              Removes a Docker extension
  update          removes and re-install a Docker extension
  validate        Validate extension extension image or metadata file
  version         Print the client and server versions

Run 'docker extension COMMAND --help' for more information on a command.
```

- Listing the Docker Extensions

```
docker extension ls
```

- Install and Run Docusaurus

```
npx create-docusaurus@latest mywebsite classic
cd mywebsite
npm run start
```

By default, a browser window will open at http://localhost:3000.


- Develop the Extension UI

If your extension has a UI, you can see it directly inside Docker Desktop whilst you develop it directly. For this you need to first install the extension. If you then run a development server locally, with yarn start for example, enter the following command:

```
git clone https://github.com/docker/extensions-sdk
cd extension-sdk/samples/react
make build-extension

```
## Install the Extension

```
docker extension install docker/react-extension:latest
Extensions can install binaries, invoke commands and access files on your machine. 
Are you sure you want to continue? [y/N] y
Installing new extension "docker/react-extension:latest"
Installing Desktop extension UI for tab "UI Extension"...
Extension UI tab "UI Extension" added.
Extension "React Docker Extension" installed successfully
```

## Running the Extension UI

ajeetraina@Ajeets-MacBook-Pro react % docker extension dev ui-source docker/react-extension:latest http://localhost:3000
UI source for the extension "docker/react-extension:latest" changed to "http://localhost:3000"%  
```

<img width="1391" alt="image" src="https://user-images.githubusercontent.com/34368930/175223803-e34c870f-f682-41f0-ae41-2656e8e2781f.png">






