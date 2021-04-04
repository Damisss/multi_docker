FROM node:14.16.0-alpine3.13
WORKDIR /app
COPY package.json ./
RUN npm install
COPY . . 
RUN npm run build

From nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=0 /app/build /usr/share/nginx/html