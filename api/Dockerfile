FROM node:20.12-alpine

RUN npm install -g nodemon
RUN npm install -g pm2

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 5000

CMD ["npm", "run", "start"]