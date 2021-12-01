# cicd-sandbox

https://opensource.com/article/19/4/devops-pipeline

Dev machine dependencies:
* git
* ghostwriter
* emacs
* docker

Playing around with CI/CD &amp; Docker containers
* [ ] Figure out how to abstract secrets to safe location [5 practical tips](https://www.youtube.com/watch?v=JE2PJbbpjsM&ab_channel=DevOpsDirective)
* [ ] Put django experiment in a docker container
* [ ] [Test CI/CD on Django experiment](https://www.youtube.com/watch?v=gdbA3vR2eDs&ab_channel=JavaHomeCloud)
* [ ] Put react-native experiment in a docker container
* [ ] Test CI/CD on ReactNat experiment
* [ ] One line app building from scratch (https://jpetazzo.github.io/2015/09/03/do-not-use-docker-in-docker-for-ci/) Is this a script? Something else?
* [ ] Do 2 release tests to ensure PROD is updated 
* [ ] Abstract the whole mess to a simple easy launchable app framework

## 11/13/2021
* Changing directions again to follow [this tutorial](https://www.youtube.com/watch?v=_CBYbEGvxYY)
* Plan is to develop from scratch in a docker container. Paradigm will be that the mono repo will live in a folder and code will be developed inside docker containers to avoid sys configs from creating additional headaches. The docker container will be hosted in the cloud and synced. If Docker can handle the env reqs, package.json should be able to handle most/everything else.

## 11/12/2021 Developing React Native Web in Container Notes
* Worked off [this tutorial](https://www.rockyourcode.com/how-to-run-react-native-expo-web-in-a-docker-container/)
* Had an NPM issue that was resolved with `npm cache clean --force` but probably could/should use `npm cache verify`
* Had 2 versions of Node, so had to nuke both and install Node fresh. NPM kept throwing simver errors
* May have issues because of this:
``` expo-cli supports following Node.js versions:
* >=12.13.0 <13.0.0 (Maintenance LTS)
* >=14.0.0 <15.0.0 (Active LTS)
* >=15.0.0 <17.0.0 (Current Release)
```
* Got lots of warnings when building the Docker container for the first time.
* Had trouble with the parantheses in the example, so I skipped to docker compose. Had to install docker-compose.
* Had enormous difficulty resolving an npm permissions error. I found the solution [here](https://forum.codewithmosh.com/t/docker-npm-permission-denied/4766/3)
* Tutorial was kinda hard to adapt and all I got was a blank white screen. Shifted focus to [this tutorial](https://www.digitalocean.com/community/tutorials/build-mobile-friendly-web-apps-with-react-native-web)
* 

## 11/12/2021 Developing React in Container Notes
* Installed Docker
* Added [Remote Development](https://aka.ms/vscode-remote/download/extension) extension pack to VS Code
* Restart was required. Need to add `sudo usermod -aG docker $USER` to init bash script
* Had to run `npm install` from VS Code terminal after starting container
* Once this was done, running the node app AUTOMATICALLY launched a browser window. I didn't have to expose any ports or any of that. Gasp.

The dev environment can be launched by pressing `F1` and typing `Remote-Containers: Open Folder in Container`
