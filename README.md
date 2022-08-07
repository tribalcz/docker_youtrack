# Youtrack
YouTrack is a project management tool from a company called JetBrains which make IDEs like PHPStorm, PyCharm, GoLand, etc. It offers nice features like issues tracking, sprint plan, workflow, and many more.

# Installation

<sub><sup>Run the commands for chown and chmod as sudo|root</sup></sub>

- Clone this repo
- (optional) - Modify docker-compose.yml
    - services->container_name
    - networks->{network_name}
    - services->networks
- create the necessary files by entering the command:
    - <code>mkdir -p -m 750 data conf logs backups</code>
    - (optional) - if the directory names are different, it is necessary to make the appropriate mapping in docker-compose.yml. Otherwise, the necessary folders       will be created automatically
- Another requirement is to grant permissions to non-root user to those folders. These are user and group 13001:13001. To do this, use the following command:
    - <code>chown -R 13001:13001 data/ logs/ backups/ conf/</code>
    
- And finally, start the container:
    - <code>docker-compose up -d --build</code>
    
- (optional) - in case of any problem you can use bash script to restart the container. You will need to assign the necessary permissions to it first, using the   following command:
    - <code>chmod +x restart.sh</code>
    - (restart command) - <code>./restart.sh</code>
    - The script does nothing more than run <code>docker-compose down</code> and <code>docker-compose up -d</code> in sequence
