FROM node:0.12.7

# Add users and sudo
RUN apt-get update && apt-get install -y sudo
RUN adduser devel --home /home/devel \
  --shell /bin/bash \
  --disabled-password \
  --gecos ""

# Add users to sudoers, so no need to ask for password
RUN echo "devel ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

# Make ports accessible
EXPOSE 8000

RUN mkdir -p /var/www/src
RUN mkdir -p /var/www/public

# Placeholder files, after first run /var/www
# should be replaced with a volume 
COPY package.json /var/www/src/
COPY index.html /var/www/public/
RUN chown -R devel /var/www/

WORKDIR /var/www/src
USER devel

CMD [ "npm", "start" ]
