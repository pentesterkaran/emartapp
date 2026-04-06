FROM node:14 as builder
WORKDIR /emartapp
COPY ./ ./nodeapi
RUN cd nodeapi && npm install

FROM node:14
WORKDIR /emartapp
COPY --from=builder /emartapp/nodeapi/ ./nodeapi
EXPOSE 5000

CMD ["/bin/sh","-c","cd /emartapp/nodeapi/ && npm start"]

