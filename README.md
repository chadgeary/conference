# Reference
Playbooks for feature-rich self-hosted chat with seamless video/audio conferencing using BigBlueButton and Mattermost open source projects.

# Requirements
BigBlueButton https://github.com/bigbluebutton
- One domain name, e.g. bbb.chadg.net
- One Ubuntu 1604 instance, e.g. t3a.large, 30GB vol.
- See /bigbluebutton/instance for AWS EC2 instance building playbook.

Mattermost https://github.com/mattermost
- One domain name, e.g. mm.chadg.net
- One CentOS 7 instance, e.g. t3a.small, 10GB vol.
- See /mattermost/instance for an AWS EC2 instance building playbook.

# Installation
See READMEs of BigBlueButton and Mattermost subdirectories.

# Post-Installation Tasks
- Create administrator account for Mattermost by browsing to your Mattermost server, e.g. https://mm.chadg.net
- Set 'Enable integrations to override usernames' and 'Enable integrations to override profile picture icons' in Mattermost Web System Console -> Integrations
- Add the BigBlueButton Server URL (e.g. https://bbb.chadg.net/bigbluebutton/api) and Secret as output in the BigBlueButton ansible playbook
