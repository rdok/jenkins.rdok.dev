# jenkins.rdok.dev
Docker based jenkins.

### Config
#### Environment variables
Export .env.example according to your needs. 

#### Expose docker socket
[ ~jpetazzo/Using Docker-in-Docker for your CI or testing environment? Think twice.](https://jpetazzo.github.io/2015/09/03/do-not-use-docker-in-docker-for-ci/) has established running docker in docker is not a good idea. 

Instead expose the hosts's Docker socket to the Jenkins CI container. 

Assuming you've completed [Post-installation steps for Linux](https://docs.docker.com/install/linux/linux-postinstall/) 

Find this docker group gid (`cat /etc/group | grep docker`) and append it as an environment variable. See .env.example (`DOCKER_GID`)

### Run
`compose up -d`
