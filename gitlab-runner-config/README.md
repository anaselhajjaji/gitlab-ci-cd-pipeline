The command to register the runner :

```
docker run --rm -t -i -v $PATH_TO_CONFIH:/etc/gitlab-runner --name gitlab-runner gitlab/gitlab-runner register \
  --non-interactive \
  --executor "docker" \
  --docker-image alpine:3 \
  --url "http://localhost:30080/ci" \
  --registration-token "_3zNd3Uve5CRYXcZn6P4" \
  --description "docker-runner" \
  --tag-list "docker,aws" \
  --run-untagged \
  --locked="false"
```

Then start the runner :

```
docker run -d \
 --name gitlab-runner \
 --restart always \
 -v $PATH_TO_CONFIH:/etc/gitlab-runner \
 -v /var/run/docker.sock:/var/run/docker.sock \
 gitlab/gitlab-runner:latest
 ```
