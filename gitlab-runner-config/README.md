The command to register the runner :

```
docker run --rm -t -i -v $CONFIG_PATH:/etc/gitlab-runner --name gitlab-runner gitlab/gitlab-runner:latest register --non-interactive --executor "docker" --docker-image alpine:3 --url "http://192.168.43.41:8080/ci" --registration-token "_3zNd3Uve5CRYXcZn6P4" --description "docker-runner" --tag-list "docker,aws" --run-untagged --locked="false"
```

Then start the runner :

```
docker run -d --name gitlab-runner --restart always -v $CONFIG_PATH:/etc/gitlab-runner -v /var/run/docker.sock:/var/run/docker.sock gitlab/gitlab-runner:latest
```
