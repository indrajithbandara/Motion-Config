FROM vcatechnology/linux-mint
MAINTAINER evgeny.lityushkin@gmail.com

RUN apt-get update && apt-get install -y motion && apt-get install -y mutt 
#RUN mkdir -p /home/user/motion/ && mkdir -p /home/user/motion/cam1/ && mkdir -p /var/lib/motion/ 

RUN rm -f /etc/motion/motion.conf
COPY motion.conf /etc/motion/motion.conf
#RUN rm -f /etc/default/motion
#COPY motion /etc/default/motion
VOLUME /dev
VOLUME /home/user/motion
VOLUME /var/log/motion
VOLUME /var/lib/motion


EXPOSE 8080 8081

CMD ["/usr/bin/motion", "-c", "/etc/motion/motion.conf", "-n"]
#ENTRYPOINT "/usr/bin/motion"

