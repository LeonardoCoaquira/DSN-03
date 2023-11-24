FROM node:14

WORKDIR /web

COPY ./web/package.json /app/
COPY ./web/package-lock.json /app/

RUN npm install

COPY ./web /app

EXPOSE 80

CMD ["npm", "start"]