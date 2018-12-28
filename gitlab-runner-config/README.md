'
CONFIG_FOLDER=/tmp/gitlab-runner-config

docker run — rm -t -i \
 -v $CONFIG_FOLDER:/etc/gitlab-runner \
 gitlab/gitlab-runner register \
   --non-interactive \
   --executor "docker" \
   —-docker-image docker:stable \
   --url "https://gitlab.com/" \
   —-registration-token "$PROJECT_TOKEN" \
   —-description "Exoscale Docker Runner" \
   --tag-list "docker" \
   --run-untagged \
   —-locked="false" \
   --docker-privileged
   '
