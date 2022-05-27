---
title: "Bonus: Redeployment Script"
weight: 120
date: 2022-05-05
---

## Redeployment Script

Below you will find a script that can be run inside of the react-tic-tac-toe project.

The script accomplishes a few things:
1. Compares the local and remote branch to one another
  1. Appends a message to a deploy
1. Rebuilds the project if there are changes that were merged

{{% notice note %}}
This is not a common way to redeploy projects nor rebuild them. This is meant to serve as a fun way to manipulate the `.git` directory within any given project.
{{% /notice %}}

{{% expand "Click Here for Script" %}}
```bash
## Change into react-tic-tac-toe project directory (your directory location may vary)
cd ~/Desktop/react-tic-tac-toe-tutorial

git fetch

remote_head=$(sed 's/\t.*$//' .git/FETCH_HEAD)
local_head=$(cat .git/refs/heads/master)

## Compare remote and local branch
if [[ $remote_head == $local_head ]]
then
	echo "$(date):Commit histories are the same, no changes detected" >> ~/Desktop/react-deploy.log

else
	git merge
	## build project
	export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
	[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
	nvm install 16.3.0
	nvm use 16.3.0
	npm i
	npm run build
	rm -rf ~/Desktop/build
	mv build/ ~/Desktop
	echo "$(date):Changes have been detected, project rebuilt and redeployed" >> ~/Desktop/react-deploy.log
fi
```
{{% /expand %}}