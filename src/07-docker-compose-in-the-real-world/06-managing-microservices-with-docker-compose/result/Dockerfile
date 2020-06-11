# Updates:
#   Nov 2019: Update base Docker image to use a more recent version of Node
FROM node:12.13.1-slim

WORKDIR /app

# Updates:
#   Nov 2019: Lock version to avoid potential future versioning issues
RUN npm install -g nodemon@2.0.1
ADD package.json /app/package.json
RUN npm config set registry http://registry.npmjs.org
RUN npm install && npm ls
RUN mv /app/node_modules /node_modules

ADD . /app

ENV PORT 80
EXPOSE 80

CMD ["node", "server.js"]
