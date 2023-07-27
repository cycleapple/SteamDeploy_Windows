# SteamDeploy_Windows
```
jobs:
  deployToSteam:
    runs-on: ubuntu-latest
    steps:
      - uses: cycleapple/steam_deploy_windows@v1
        name: Deploy_to_Steam
        with:
          username: ${{ secrets.STEAM_USERNAME }}          
          appId: ${{ secrets.AppId }}
          depotId: ${{ secrets.DepotId }}
          buildDescription: "Build Description"
          rootPath: build
          releaseBranch: sit_branch
```