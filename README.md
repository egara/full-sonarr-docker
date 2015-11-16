# Project: full-sonarr-docker
It is a containerized system using docker in order to run Sonarr. Sonarr, by default, doesn't have a download client installed, so this project tryes to put a client and Sonarr itself working together in a easy way.

# What is Sonarr? ##

[Sonarr](https://sonarr.tv/) is a tv series management tool which will allow to not only download shows, but maintain them after it. It supports [NZBGet](nzbget.net) and [Sabnzbd](sabnzbd.org)

# Deployment instructions #

## Docker and Docker Compose ##

Docker and Docker Compose must be installed on the system. Depending on the Linux Distribution, the installation process is different (example for Arch):

    sudo pacman -S docker
    yaourt -S docker-compose

## Clone git repository ##

Go to the directory where you want to install full-sonarr-docker project:

    git clone https://
