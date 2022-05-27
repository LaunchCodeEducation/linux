<!-- root/_index.md -->
### Script One

A machine setup, and initialization script.

This script will automatically do everything that we learned in the Web Server: Static and Web Server: Reverse Proxy chapters.

It will all need to exist in one script. You will prove it works, by spinning up a brand new virtualbox image. Cloning the script. Executing the script. Access your deployed application from the browser of your VirtualBox image.

### Script Two:

This script fires every 5 minutes. It is constantly *polling* the project remote repo. If changes are detected it redeploys the application!

<!-- example/script-one -->
## Example

Pictures of the output of using the script in all states:

- completely successful
- successful but first time deployment failed
- not successful before deployment

## Validation

After running the script the pictures of proof of validation including:

- tools installed successfully
  - `which package` or `package --version` commandss
- remote repo cloned
  - `ls /path/to/clone/location`
  - `cd /path/to/clone/location` & `git remote --v`
- build artifacts created & moved
  - `ls /path/to/artifact/location`
- unit file exists
  - `ls /path/to/unit-file/location`
- deployment currently running
  - `systemctl status [unit-name]`
  - picture of browser with project accessible on port
- email sent
  - picture of email in personal account from server
- crontab successfully edited
  - `crontab -l`
<!-- example/script-two -->
## Example

Pictures of the output of using the script in all states:

- success: changes detected & successfully redeployed
- failure: changes detected & NOT successfully redeployed
- success: no changes detected log updated

## Validation

After running the script the pictures of proof of validation including:

- script exists
  - `ls /path/to/script`
- script logs
  - `cat /path/to/log/location`
- change made to project
  - picture of browser reflecting change after change made to project master branch
<!-- requirements/script-one -->
## Steps

- install dependencies
- clone repository
- build artifacts
- install web server
- configure web server
- create unit file
- move build artifacts to correct location
- start system
- if system deployed successfully:
  1. email your personal email address with a success message
  1. create a cron job that fires **script two** every 5 minutes
- if system did not deploy successfully:
  1. email your personal email address with a failure message
  2. make changes to your script and try again
<!-- requirements/script-two -->
## Steps

- change to project repo
- pull project repo
- if changes are detected:
  - build artifacts
  - move artifacts to unit file location
  - restart service
  - email that changes were detected and project was successfully re-deployed
- if no changes are detected:
  - write to a log file with:
    - timestamp
    - the local project path was checked
    - the remote repo that was checked