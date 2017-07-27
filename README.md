# platformio-vsts-agent-docker
Visual Studio Team Services (VSTS) Agent Docker Images with PlatformIO with ESP8266 pre-installed

This is based off (vsts-agent-docker)[https://github.com/Microsoft/vsts-agent-docker] images. View this website for more information.

# How to build the docker image
- Open command prompt and change directory to ubuntu/windows
- docker build -t <imageName> .

# How to start docker
docker run -e VSTS_ACCOUNT=<accountName> -e VSTS_TOCKEN=<token> -e VSTS_POOL=<poolName> -it <imageName>