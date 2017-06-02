# Selenium Client with Ubuntu Desktop Dockerfile

Docker container for Ubuntu 16.04 including ubuntu-desktop and vncserver.

# How to run

`docker run -v $(pwd)/robots:/robots amarinnwc/selenium-client bash -c "pybot /robots"`

# Run with zalenium

`docker network create --subnet=172.18.0.0/16 cinet`

`docker run --rm -ti --name zalenium --network default --net cinet --ip 172.18.0.5 -v $(which docker):/usr/bin/docker -v /var/run/docker.sock:/var/run/docker.sock -v /tmp/videos:/home/seluser/videos dosel/zalenium start`

`docker run --net cinet -v $(pwd)/robots:/robots -v $(pwd):/output -e ROBOT_TESTS=/robots/ -e BROWSER=firefox amarinnwc/selenium-client bash -c "pybot /robots"`
