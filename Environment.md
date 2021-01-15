# Accounts
- [Github account] (https://github.com)
- [DockerHub account] (https://hub.docker.com/?ref=login)
- [Google Cloud Platform] (https://console.cloud.google.com/billing/01D4EF-77D620-DAFCAA?project=utopian-theater-297420)
- [Mongo DB] (https://account.mongodb.com/account/login)

# Credentials
- Google credentials
- SSH GitHub
- SSH GCP global (for VMs etc)
- SSH GKE cluster (for kubectl)

# Mongo DB instance
- mongodb+srv://rnr-mongo-db:rnr-mongo-db@cluster0.6di2v.mongodb.net/rnr-persist

# Local Environment

## VS Code
> Version: 1.52.1
> Commit: ea3859d4ba2f3e577a159bc91e3074c5d85c0523
> Date: 2020-12-16T16:30:02.420Z (3 wks ago)
> Electron: 9.3.5
> Chrome: 83.0.4103.122
> Node.js: 12.14.1
> V8: 8.3.110.13-electron.0
> OS: Darwin x64 19.6.0

## NodeJS
> $ node -v
> v14.8.0

## NPM
> $ npm version
> {
>   labs: '1.0.0',
>   npm: '6.14.7',
>   ares: '1.16.0',
>   brotli: '1.0.7',
>   cldr: '37.0',
>   icu: '67.1',
>   llhttp: '2.0.4',
>   modules: '83',
>   napi: '6',
>   nghttp2: '1.41.0',
>   node: '14.8.0',
>   openssl: '1.1.1g',
>   tz: '2020a',
>   unicode: '13.0',
>   uv: '1.38.1',
>   v8: '8.4.371.19-node.12',
>   zlib: '1.2.11'
> }

## Postman
> Version 7.36.1 (7.36.1)

## MongoDB Compass
> Version 1.24.6 (1.24.6)

## Docker
> Rocks-MacBook-Pro:~ rockbarney$ docker version
> Client: Docker Engine - Community
>  Version:           19.03.12
>  API version:       1.40
>  Go version:        go1.13.10
>  Git commit:        48a66213fe
>  Built:             Mon Jun 22 15:41:33 2020
>  OS/Arch:           darwin/amd64
>  Experimental:      false

> Server: Docker Engine - Community
>  Engine:
>   Version:          19.03.12
>   API version:      1.40 (minimum version 1.12)
>   Go version:       go1.13.10
>   Git commit:       48a66213fe
>   Built:            Mon Jun 22 15:49:27 2020
>   OS/Arch:          linux/amd64
>   Experimental:     false
>  containerd:
>   Version:          v1.2.13
>   GitCommit:        7ad184331fa3e55e52b890ea95e65ba581ae3429
>  runc:
>   Version:          1.0.0-rc10
>   GitCommit:        dc9208a3303feef5b3839f4323d9beb36df0a9dd
>  docker-init:
>   Version:          0.18.0
>   GitCommit:        fec3683

# Python
> $ python -V
> Python 2.7.16

## Kubectl
> $ kubectl version
> Client Version: version.Info{Major:"1", Minor:"20", GitVersion:"v1.20.1", GitCommit:"c4d752765b3bbac2237bf87cf0b1c2e307844666", GitTreeState:"clean", BuildDate:"2020-12-18T12:09:25Z", GoVersion:"go1.15.5", Compiler:"gc", Platform:"darwin/amd64"}
> Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.10", GitCommit:"575467a0eaf3ca1f20eb86215b3bde40a5ae617a", GitTreeState:"clean", BuildDate:"2019-12-11T12:32:32Z", GoVersion:"go1.12.12", Compiler:"gc", Platform:"linux/amd64"}

## Google Cloud SDK
> google-cloud-sdk-VERSION-darwin-x86_64.tar
> ./google-cloud-sdk/install.sh
> ./google-cloud-sdk/bin/gcloud init
> Picked "7" as the default compute zone: us-central1-c
> Project is utopian-theater-297420
> Cluster is my-first-cluster-1
> gcloud container clusters get-credentials my-first-cluster-1 --zone us-central1-c --project utopian-theater-297420

## Google Cloud SDK
> $ gcloud -v
> Google Cloud SDK 322.0.0
> beta 2021.01.05
> bq 2.0.64
> core 2021.01.05
> gsutil 4.57
