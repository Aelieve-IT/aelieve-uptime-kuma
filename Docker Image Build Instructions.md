## Prereqs
--- 
- WSL 2 or Ubuntu 22.04
- NVM
- NodeJS
	- **Release Branch** Node version 20.18.0
	- **Master Branch** Node Version 20.10.0
- [Aelieve Uptime Kuma Repo](https://github.com/Aelieve-IT/aelieve-uptime-kuma) Cloned and on the branch you wish to build

## Master Build
--- 
***This build is a Beta version of Uptime Kuma 2.0. USE THIS FOR TESTING ONLY!!!***

Clone the Aelieve Uptime Kuma Repo and cd into it: 
```
git clone org-113565270@github.com:Aelieve-IT/aelieve-uptime-kuma.git 
```
```
cd aelieve-uptime-kuma
```

Checkout the master branch:
```
git switch master
```

Insure you're on the correct version of nodejs
```
nvm current # this should output v20.10.0
```

If you are ***NOT*** on the correct version of nodejs, use NVM to install and switch to the correct version:
```
nvm install 20.10.0
```
```
nvm use 20.10.0
```

Install NPM packages:
```
npm install
```

Set $VERSION variable (use the latest release of Uptime Kuma):
```
export VERSION=2.0.0-dev
```
```
echo $VERSION
```

Build GO Builder images:
```
npm run build-docker-builder-go
```

Build base images:
```
npm run build-docker-base
```
```
npm run build-docker-base-slim
```
``` 
npm run build-docker-base-slim-rootless 
```

Build application images:
```
npm run build-docker
```

Images will be deployed to docker hub and ready for use.

## Release Build
--- 
Clone the Aelieve Uptime Kuma Repo and cd into it: 
```
git clone org-113565270@github.com:Aelieve-IT/aelieve-uptime-kuma.git 
```
```
cd aelieve-uptime-kuma
```

Checkout the release branch:
```
git switch 1.23.X
```

Insure you're on the correct version of nodejs
```
nvm current # this should output v20.18.0
```

If you are ***NOT*** on the correct version of nodejs, use NVM to install and switch to the correct version:
```
nvm install v20.18.0
```
```
nvm use v20.18.0
```

Install NPM packages:
```
npm install
```

Set $VERSION variable:
```
export VERSION=1.23.15
```
```
echo $VERSION
```

Build GO Builder images:
```
npm run build-docker-builder-go
```

Build Debian base images:
```
npm run build-docker-debian-base
```

Build Alpine base Images:
```
npm run build-docker-alpine-base
```

Build application images:
```
npm run build-docker
```

Images will be deployed to Docker Hub and ready for use!