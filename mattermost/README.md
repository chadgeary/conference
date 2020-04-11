# Reference
Creates an (all-in-one) mattermost server via docker, tested with CentOS 7.

# Deployment
```
# local example with bigbluebutton plugin 
sudo ansible-playbook mattermost.yml --extra-vars="target=localhost my_email=chad@chadg.net my_hostname=mm.chadg.net bbb=True bbb_version=2.1.0"
```

# Notes
- DB password is generated on first run.
