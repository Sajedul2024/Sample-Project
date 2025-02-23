FROM node:18.19.1-alpine AS build


WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

RUN npm run build

FROM nginx:alpine


COPY conf/nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 9097 

CMD ["nginx", "-g", "daemon off;"]
