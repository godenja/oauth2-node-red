FROM nodered/node-red:4.0

RUN npm install passport-openidconnect

COPY settings.js /usr/src/node-red/node_modules/node-red/settings.js

USER root 

RUN chown node-red:node-red /usr/src/node-red/node_modules/node-red/settings.js && chmod 644 /usr/src/node-red/node_modules/node-red/settings.js

USER node-red
