FROM node:14.16.0-alpine3.13
# RUN addgroup app && adduser -S -G app app
# USER app
WORKDIR /app
COPY package.json ./
RUN npm install
COPY . . 
RUN npm build

From nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=0 /app/build /usr/share/nginx/html