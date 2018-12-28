The command to register the runner :

```
docker run --rm -t -i -v $PATH_TO_CONFIG:/etc/gitlab-runner --name gitlab-runner gitlab/gitlab-runner register \
   --non-interactive \
   --executor "docker" \
   --docker-image docker:stable \
   --url "http://localhost:30080/" \
   --registration-token "_3zNd3Uve5CRYXcZn6P4" \
   --description "Gitlab Runner" \
   --tag-list "docker" \
   --run-untagged \
   --locked="false" \
   --docker-privileged
```

Then start the runner :

```
docker run -d --name gitlab-runner \
 --restart always \
 -v $PATH_TO_CONFIH:/etc/gitlab-runner \
 -v /var/run/docker.sock:/var/run/docker.sock \
 gitlab/gitlab-runner:latest
 ```
