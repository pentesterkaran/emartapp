FROM node:14 AS builder
WORKDIR /emartapp
COPY ./ ./client
RUN cd client && npm install && npm run build --prod

FROM nginx:latest
WORKDIR /emartapp
COPY --from=builder /emartapp/client/dist/client/ /usr/share/nginx/html/
COPY ./nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 4200 
