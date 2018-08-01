Using the public EFTG Docker image
==================================

 # Pull latest docker image from EFTG's public repository
 - docker pull eftg/main:latest

 # Clone EFTG git repository that contains the necessary config files
 - git clone https://github.com/scr53005/eftg-steem.git

 # Create a local directory that will store the EFTG Blockchain configuration, block file and shared_memory file
 - mkdir ~/efttg

 # Copy the configuration for the type of node you'll like to use into the directory we just created
 - cp ~/eftg-steem/config/seed/config.ini ~/eftg/

 # Edit the configuration and change all lines that contain the [replace] comment
 # In order to be able to connect to our Infra, please provide us your public external IP address. You can contact us [here](https://discord.gg/F4C3zBK "EFTG's discord server")
 - vim ~/eftg/config.ini

 # Finally, let's run the container !
 - docker run -p 2001:2001 -p 8090:8090 -v ~/eftg:/eftg -d --name seed -t eftg/main:latest /usr/local/bin/steemd -d /eftg
