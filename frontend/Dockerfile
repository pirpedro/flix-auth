FROM node:14.15.5-alpine3.12

RUN apk add --no-cache bash sudo git

RUN npm config set cache /home/node/app/.npm-cache --global

RUN adduser node wheel \
    && sed -e 's;^# \(%wheel.*NOPASSWD.*\);\1;g' -i /etc/sudoers

USER node

RUN touch /home/node/.bashrc | echo "PS1='\w$ '" >> /home/node/.bashrc

WORKDIR /home/node/app