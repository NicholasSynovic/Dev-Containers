FROM ubuntu:latest

RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install fuse kmod wget -y

RUN groupadd fuse
RUN usermod -a -G fuse "$(whoami)"

RUN wget https://public-cdn.cloud.unity3d.com/hub/prod/UnityHub.AppImage -O UnityHub.AppImage
RUN chmod a+x UnityHub.AppImage

CMD ./UnityHub.AppImage
