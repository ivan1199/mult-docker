FROM node:alpine as builder
WORKDIR "/app"
RUN npm install
COPY ./package.json
COPY . .
RUN npm run build

FROM nginx 
PORT 3000
COPY ./client/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html

