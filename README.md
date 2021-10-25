# home-docker

# Project start up

- Prerequisites
- - node.js
- - docker
- - Yarn
- Step 1 (Build frontend )
- - run `yarn` in frontend folder (This installs the dependencies for the frontend )
- - run `yarn build` in frontend folder (This builds and packages the frontend so it can be copied into the nginx to be served)
- Step 2 (Get everything running)
- - run `docker compose up -d` in the root folder. (Starts up the docker stack -d detached so that you still have access to your terminal)
- Step 3 (Set up Radarr, Sonarr, Deluge, Jackett)
- - go to localhost
- - click on jackett
- - add indexer of your choice
- - open localhost in new tab
- - go to radarr/sonarr (steps same for both )
- - go to adding indexer
- - click on add
- - click on custom torznab
- - follow instructions in jackett for added indexer to radarr or sonar (Instead of localhost in the URL put in `jackett` this is because it is inside of a docker network)
- - test it, if it works good if not shit
- - go to adding downloader
- - open up deluge in new tab and go to settings > plugins and add the label plugin
- - Back to sonarr/Radarr now
- - click on add and click on deluge
- - if password changed put in new password
- - change host to `deluge` (Same reason as to why you put in jackett instead of localhost earlier)
- - follow the same steps sonarr if done for Radarr and vice versa
- Step 4 (Setting up pihole)
- - open a terminal into the deluge container
- - run `sudo pihole -a -p` to change the password (Just follow on screen prompts from here)
- - go to pihole and login using the password just set
- Step 5
- - setup plex

# pihole

- set password by running `sudo pihole -a -p` in the pihole docker image and follow prompts

# radarr

- Need to set the url from localhost to jacket:....

# Deluge

# Plex

- go to localhost:3200/web (or whatever port you set)
