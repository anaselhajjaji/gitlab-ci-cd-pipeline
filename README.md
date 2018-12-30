# CI-CD Pipeline using Gitlab CI
![Explanations](https://github.com/anaselhajjaji/ci-cd-pipeline/blob/master/solution_impl.jpg)

(1) The developer makes changes in the web application then pushes those changes to master

(2) Gitlab communicates with the gitlab-runner that performes the actions defined in .gitlab-ci.yml, in the example : 
- Test with npm test 
- build and push the image to docker hub: https://cloud.docker.com/repository/docker/anaselhajjaji/nodejsapp
- Deploy the the new image to docker

(3) The gitlab-runner invoke the webhook defined in Portainer (Service section, don't forget to copy the URL to Gitlab CI variables)

(4) Once the webhook received, Portainer deploys the new version of the service (downloads the latest image from the docker hub then deploys it). Portainer communicate with the docker engine to do so

(5) The new version of the webapp is available for the browser
