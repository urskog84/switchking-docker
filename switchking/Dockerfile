FROM ubuntu:14.04
MAINTAINER karl.petter.fors@gmail.com 


RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* \
    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
ENV LANG en_US.utf8


RUN apt-get update

RUN apt-get install -y wget
RUN apt-get install -y unzip
RUN apt-get install -y mono-complete

RUN wget --content-disposition http://www.switchking.se/download/665/ -O /tmp/switchking.zip
RUN unzip /tmp/switchking.zip -d /bin/switchking/


# Import Existing Database
COPY ./DB/switchKing.server.db3 /bin/switchking/Bin/DB/switchKing.server.db3


# Start With new database
#RUN tar -xvf /bin/switchking/Bin/DB/switchKing.server.db3.tar.gz -C /bin/switchking/Bin/DB/


RUN echo "deb-src http://download.telldus.com/debian/ stable main" | sudo tee -a /etc/apt/sources.list
RUN echo "deb http://download.telldus.com/debian/ stable main" | sudo tee -a /etc/apt/sources.list
RUN wget -q http://download.telldus.se/debian/telldus-public.key -O- | sudo apt-key add -


RUN apt-get update
RUN apt-get install -y telldus-core libftdi1 libconfuse0 libconfuse-dev --fix-missing

COPY tellstick.conf /etc/tellstick.conf

#Sart Tedusd services
#ENTRYPOINT  ./etc/init.d/telldusd start && mono /bin/switchking/Bin/SwitchKing.exe daemon 8080 8800 && /bin/bash
