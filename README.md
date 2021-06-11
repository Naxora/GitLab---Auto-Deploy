# GitLab - Auto Deploy

## Install gitlab-runner
https://docs.gitlab.com/runner/install/docker.html

## Create SSH key in remote server
ssh-keygen -t ed25519 -C "Comment"
Save as custom name like: gitlabKey

## Add SSH key to authorized keys** <br>
cat ~/.ssh/gitlabKey.pub >> ~/.ssh/authorized_keys

## GitLab
In gitlab project Settings go to
--> CD/CI
--> Add variables key 'SSH_PRIVATE_KEY' value is 'gitlabKey' private key file content (Not *.pub), or create variables in admin setting but this will be makes global variables

## Deploy token for repository
If you are using Private repository you need to create a deploy token.
Go to 'Setting' --> 'Repository' expand 'Deploy tokens' and create one.

Final url: http://**token_username**:**token**@gitlabserver.com/naxora/myrepo.git
