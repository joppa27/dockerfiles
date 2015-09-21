[![](https://badge.imagelayers.io/kongkoro/pycharm:latest.svg)](https://imagelayers.io/?images=kongkoro/pycharm:latest 'Get your own badge on imagelayers.io')

# PyCharm Community Edition
This container is only possible because of how easy it as to mount your `X11` socket to a container.  
see this blog post for more details: https://blog.jessfraz.com/post/docker-containers-on-the-desktop/.  
I decided to try my hand at making a pycharm container for my ubuntu dev box, here goes nothing!  
## xhost permission
docker is going to need permission to mount the `X11` socket. The following command should do the trick:  
``` xhost +local:docker ```

## Get The image  
To get the image, you have two options, you can build it or you can pull it from docker-hub
### Pull
``` docker pull kongkoro/pycharm ```
### Build
download the kongkoro/pycharm Dockerfile, and navigate to that directory and run the following command:  
``` docker build -t kongkoro/pycharm . ```

### Run
If you just want to try out the container and aren't worried about losing your settings/config/code try this:  
``` docker run -it -v /tmp/.X11-unix/:/tmp/.X11-unix/ -e DISPLAY=$DISPLAY --rm kongkoro/pycharm ```  


 
