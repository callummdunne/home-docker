# home-docker

## Project setup

### Prerequisites

- node.js
- docker
- Yarn

### Docker setup

- Docker is what managers your containers and each of your services running
- In this project you will find a file called `docker-compose.yml` In this file is specifies information for each of your services
- First to setup is to set all the locations where you want the movies/tv shows and configurations stored
  - To do this you will go into the `docker-compose.yml` file and edit the values under volumes for each of the services
    Volume example
    ```
    volumes:
    - D:/plextest/config:/config
    - D:/plextest/transcode:/transcode
    - D:/plextest/series:/data/tv
    - D:/plextest/movies:/data/movies
    ```
    - You will have to change the D:/... to where ever you want the data to be stored

### Starting docker

- Run `docker compose up -d` in the root folder. (Starts up the docker stack -d detached so that you still have access to your terminal)
- This will take some time the first time you do it as it will have to download all of the images
- Once it says that all the containers are up and running got to `localhost` and you should see:
- 
![docker-home screenshot ](https://user-images.githubusercontent.com/36222895/140610145-097fcbe2-7e9a-479e-aa98-0b6c3317f148.png)

### Deluge setup

- Now that you are on the main screen click on deluge
- Password for deluge is `deluge`
- Change the password in settings
- Go to settings > plugins and add the label plugin

### Jackett setup

- Go to `localhost` click on jackett
- Go to add indexers and add the indexers of your choice
- Look at the instructions on jackett for adding it to radarr and sonarr because you are going to follow that soon

### Sonar/Radarr setup

(The setup for these 2 is the same)

- Follow the instructions on jackett to add jackett to it (NB you will have to change the URL a bit from `http://localhost:9117/api/v2.0/indexers/1337x/results/torznab/` to `http://jackett:9117/api/v2.0/indexers/1337x/results/torznab/` as it will be routing inside of docker)
- To add deluge go to settings > download clients
- click the add and click on the deluge preset
- Change the host to `deluge`
- set the name you want
- set the password you have set in your deluge

### pihole

- For this you will have to use the command line to set the password for pihole
- Connect to the pihole container and enter `sudo pihole -a -p` to change the password
- Once completed you should be able to access pihole with that password without an issue

### Plex

- For this you will have to first go to `https://www.plex.tv/claim/` and create a plex account or login to your plex account
- This will then show you a claim code
- This code you must copy and paste into your `docker-compose.yml` file where it says `- PLEX_CLAIM=PUT PLEX CLAIM HERE` so if the claim is `claim-aaaaaa_ddddddd` the value in the docker-compose file will change to `- PLEX_CLAIM=claim-aaaaaa_ddddddd`
- Then run `docker compose up -d` again to have it take place
- Then go to `localhost` and click on plex
- It should show you the first couple of steps to setup your plex server
- Just note that the claim code only lasts about 4 minutes so could expire if this process takes to long
