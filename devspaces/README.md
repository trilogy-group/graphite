# Graphite Development with DF Devspaces

## Install DF Devspaces

1. Create and install devspaces client as it is written in help guide https://support.devspaces.io/article/22-devspaces-client-installation.

2. Here is some details about DF Devspaces https://devspaces.io/devspaces/help

Here follows the main commands used in Devspaces cli. 

|action   |Description                                                                                   |
|---------|----------------------------------------------------------------------------------------------|
|`devspaces --help`                    |Check the available command names.                               |
|`devspaces create [options]`          |Creates a DevSpace using your local DevSpaces configuration file |
|`devspaces start <devSpace>`          |Starts the DevSpace named \[devSpace\]                           |
|`devspaces bind <devSpace>`           |Syncs the DevSpace with the current directory                    |
|`devspaces info <devSpace> [options]` |Displays configuration info about the DevSpace.                  |

Use `devspaces --help` to know about updated commands.


### Start Devspaces 

This guide assumes that user is inside `devspaces` folder of the repository.

1.  Create DevSpaces.

```bash
devspaces create
```

2. Start your devspaces.
```bash
devspaces start graphite
```

3. Start containers synchronization. Open a new terminal on a folder that should be synced with devspaces and run:

```bash
devspaces bind graphite
```

4. Clone the source inside the sync folder from previous step. You may check out the sync process by openning `http://localhost:49152/` in your browser.

```bash
git clone https://github.com/trilogy-group/graphite.git
```

5. Get some information about created devspace. 

```bash
devspaces info graphite
```

6. Connect to development container

```bash
devspaces exec graphite
```

7. Get inside the repo folder and create a `prod.js` based on `dev.js`.

```bash
cd graphite
cp src/components/helpers/dev.js src/components/helpers/prod.js
```

8. Build and run the project.

```bash
npm install
npm run start
```

9. Open a link for port 3000 on your browser.

**Importnat note**: Local development will result in CORS errors on authentication. Use a CORS browser extension to get around this. Future version will eliminate this need and when pushed to a hosted site, the CORS error is resolved. In the case of crhome, you may use `https://chrome.google.com/webstore/detail/cors/dboaklophljenpcjkbbibpkbpbobnbld?hl=en`

10. Also you may run tests.

```bash
npm run test
```