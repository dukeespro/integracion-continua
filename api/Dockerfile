FROM node:lts-buster AS base
LABEL maintainers="dukeespro@gmail.com"
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
COPY api/package*.json /
RUN npm install
COPY api/. .
RUN npm run build
EXPOSE 3000
CMD ["npm","start"];
