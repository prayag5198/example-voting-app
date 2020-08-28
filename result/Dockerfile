FROM node:10-slim

WORKDIR /result/app

RUN npm install -g nodemon
ADD /result/package.json /result/app/package.json
RUN npm config set registry http://registry.npmjs.org
RUN npm install && npm ls
RUN mv /result/app/node_modules /result/node_modules

ADD . /app

ENV PORT 80
EXPOSE 80

CMD ["node", "server.js"]
