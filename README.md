# Project: full-sonarr-docker
It is a containerized system using docker in order to run Sonarr. Sonarr, by default, doesn't have a download client installed, so this project tryes to put a client and Sonarr itself working together in a easy way.

# What is Sonarr? ##

[Sonarr](https://sonarr.tv/) is a tv series management tool which will allow to not only download shows, but maintain them after it. It supports [NZBGet](nzbget.net), [Sabnzbd](sabnzbd.org) and even torrent.

# Deployment instructions #

## Docker and Docker Compose ##

Docker and Docker Compose must be installed on the system. Depending on the Linux Distribution, the installation process is different (example for Arch):

    sudo pacman -S docker
    yaourt -S docker-compose

## Clone git repository ##

Go to the directory where you want to install full-sonarr-docker project:

    git clone https://github.com/egara/full-sonarr-docker.git
    
## Prepare the directories ##

- _config_ directory will contain all the Sonarr configuration files.
- _tvshows_ directory will contain all the tv show's stuff downloaded and managed by the application. This directory will be used for transmission to store the files it downloads. Before starting dockers, it could be a good idea to change permissions in this directory in order to avoid problems with Sonarr:


    cd full-sonar-docker
    sudo chmod 777 -R ./tvshows

## Docker compose configuration ##

If you want to configure the system that is going to started up, please edit _docker-compose.yml_ which is in _full-sonar-docker_ directory. Some tips:

- Ports exposed to the host: 8989 (Sonarr) and 9091 (Transmission)
- The PGID and PUID values set the user / group you'd like your container to 'run as' to the host OS. This can be a user you've created or even root (not recommended).

## Start the whole system up ##

    cd full-sonar-docker
    sudo docker-compose up
    
## Login to the applications ##

- To access Sonarr, go to your browser and type localhost:8989
- To access Transmission, go to your browser and type localhost:9091 (User: admin)(Password: admin)

## Sonarr Basic Configuration ##
When Sonarr starts for the first time, it is necessary to set up the configuration.

- Go to Settings -> Indexer -> Add a new one (for example, KickassTorrents).
- Go to Settings -> Download Client -> Add a new one (Transmission). Fill the form. It is important that you type _transmission_ in _Host_, _9091_ in _Port_ and use the credentials for transmission (admin, admin as I mentioned above). That's all. After that, add any tv show you want.
