FROM node:24 AS build

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build


FROM nginx:1.29-alpine

COPY --from=build /usr/src/app/dist /usr/share/nginx/html