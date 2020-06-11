  
FROM node:latest

LABEL MAINTAINER = "Jean Carlos Moreira da Silva <jc_mds@outlook.com>"

RUN npm install -g --production json-server &&   rm -rf /root/.npm/usr/lib/node_modules/npm 

WORKDIR /data
VOLUME /data

EXPOSE 80
ADD run.sh /run.sh
ENTRYPOINT ["bash", "/run.sh"]
CMD []