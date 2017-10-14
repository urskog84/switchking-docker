
# switchking-docker


clone the repo

build the image 

docker build .

start conainer

docker run --privileged -p 8800:8800 -p 8080:8080 -v /dev/bus/usb:/dev/bus/usb -it 8adfb6d1b56c  /bin/bash --name switchking

docker exec switchking ./etc/init.d/telldusd start
docker exec switchking mono /bin/switchking/Bin/SwitchKing.exe daemon 8080 8800

