# Reference
Creates a bigbluebutton server via bigbluebutton's installations cript, tested with Ubuntu 1604.

# Deployment
```
# local example
ansible-playbook bigbluebutton.yml --extra-vars="target=localhost my_hostname=mm.chadg.net my_email=chad@chadg.net"
```

# Notes
- The final step of this playbook outputs the URL and Secret for Mattermost's BBB Plugin.
- BBB's installation script automatically integrates LetsEncrypt-signed certificate.

# Todo
- Switch to docker (or Ubuntu 1804) when BBB updates - they appear to be close!
