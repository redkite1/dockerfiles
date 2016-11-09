# This container allow you to run node-sonos-http-api on a Raspberry Pi
#
# # Usage:
# - Build it:
#     docker build -t rpi-node-sonos .
#
# - Run it. Thnode app will commnunicate over UPNP and has to be in the same network
#   than your sonos devices, thus, you should use the docker host's network stack:
#     docker run --net=host --restart=always --name=rpi-node-sonos-01 rpi-node-sonos
#
# - Use it:
#     http://<raspberry_pi_ip>:5005
#

FROM hypriot/rpi-node

RUN git clone --depth 1 https://github.com/jishi/node-sonos-http-api.git /opt/app

# install dependencies
WORKDIR /opt/app
RUN npm install --production

EXPOSE 3500/tcp 5005/tcp

CMD ["npm", "start"]
