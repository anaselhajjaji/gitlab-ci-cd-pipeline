The command :

'''
CONFIG_FOLDER=.

docker run — rm -t -i \
 -v $CONFIG_FOLDER:/etc/gitlab-runner \
 gitlab/gitlab-runner register \
   --non-interactive \
   --executor "docker" \
   —-docker-image docker:stable \
   --url "http://localhost:30080/ci" \
   —-registration-token "_3zNd3Uve5CRYXcZn6P4" \
   —-description "Docker Runner" \
   --tag-list "docker" \
   --run-untagged \
   —-locked="false" \
   --docker-privileged
'''
