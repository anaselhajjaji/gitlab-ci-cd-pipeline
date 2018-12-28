The command to register the runner :

```
docker run --rm -t -i -v $CONFIG_PATH:/etc/gitlab-runner --name gitlab-runner gitlab/gitlab-runner:latest register --non-interactive --executor "docker" --docker-image alpine:3 --url "http://192.168.43.41:8080/ci" --registration-token "EpHZLFMH-pcyV7ivR6Xm" --description "docker-runner" --tag-list "docker,aws" --run-untagged --locked="false"
```

Then start the runner :

```
docker run -d --name gitlab-runner --restart always -v $CONFIG_PATH:/etc/gitlab-runner -v /var/run/docker.sock:/var/run/docker.sock gitlab/gitlab-runner:latest
```

To publish to docker hub, set the following variables :

```
CI_REGISTRY_USER=username
CI_REGISTRY_PASSWORD=********
CI_REGISTRY=index.docker.io
CI_REGISTRY_IMAGE=index.docker.io/username/nodejsapp
```
