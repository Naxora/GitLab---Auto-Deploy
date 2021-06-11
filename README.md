# GitLab - Auto Deploy

## Install gitlab-runner
https://docs.gitlab.com/runner/install/docker.html <br>
I'm using 'Option 2: Use Docker volumes to start the Runner container' version

## Configure gitlab-runner to your repo
You can find manually runner setup in your repo settings --> 'CI/CD' --> expand 'Runners' <br>
Click 'Show runner installation instructions' and use 'Command to register runner' code if you using docker version.<br>
Copy code and replace '$REGISTRATION_TOKEN' variable to your token what you can find below 'And this registration token:' text.

Go to your runner, login and paste modified command.

## Create SSH key in remote server
ssh-keygen -t ed25519 -C "Comment" <br>
Save as custom name like: gitlabKey

## Add SSH key to authorized keys** <br>
cat ~/.ssh/gitlabKey.pub >> ~/.ssh/authorized_keys

## GitLab
In gitlab project Settings go to
--> CD/CI
--> Add variables key 'SSH_PRIVATE_KEY' value is 'gitlabKey' private key file content <br> (not *.pub), or create variables in admin setting but this will be makes global variables

## Deploy token for repository
If you are using Private repository you need to create a deploy token.
Go to 'Setting' --> 'Repository' expand 'Deploy tokens' and create one.

Final url: http://**token_username**:**token**@gitlabserver.com/naxora/myrepo.git
