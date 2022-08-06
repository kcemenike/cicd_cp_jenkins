# https://nodejs.org/en/docs/guides/nodejs-docker-webapp/
FROM node:16

WORKDIR /app

COPY package*.json ./

RUN npm ci --only=production

COPY . .

EXPOSE 80
CMD [ "npm", "start" ]