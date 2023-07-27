Steam - Deploy GitHub Action
============================

Description
-----------

This GitHub Action allows you to deploy game builds to Steam using the SteamSDK. It automates the process of modifying
the necessary build scripts and deploying your game builds to Steam with ease, is designed for windows self-runner.


### Inputs

The action requires the following inputs:

* `steamcmdPath` (required): The full path to the SteamCMD executable.
* `username` (required): The username of your builder account on Steam.
* `userpwd` (required): The user password of your builder account on Steam.
* `appId` (required): The app ID within the Steam partner network.
* `depotId` (required): The depot ID within the Steam partner network.
* `rootPath` (required): The root path to your game builds. This is the base from which depots will search for your files.
* `buildDescription` (optional): Description for this build. (You can leave it empty if not required)
* `releaseBranch` (optional): The branch within Steam where this build will be automatically put live. (You can leave it empty if not
  required)

### Example Workflow

Here's an example of how to use the "Steam - Deploy" action in your GitHub workflow:

```
      Deploy to Steam
        runs-on: self-hosted
        steps:
        - name: Deploy to Steam
          uses: cycleapple/SteamDeploy_Windows@v1
          with:
            steamcmdPath: '/path/to/steamcmd'
            username: ${{ secrets.STEAM_USERNAME }}
            userpwd: ${{ secrets.STEAM_PASSWORD }}
            appId: 'your_app_id'
            depotId: 'your_depot_id'
            rootPath: '/path/to/your/builds'
            buildDescription: 'Your build description'
            releaseBranch: 'Your release branch'

```


### Secrets

Make sure to set the following secrets in your GitHub repository:

* `STEAM_USERNAME`: The username of your builder account on Steam.
* `STEAM_PASSWORD`: The user password of your builder account on Steam.

License
-------

This project is licensed under the [MIT License](LICENSE).


