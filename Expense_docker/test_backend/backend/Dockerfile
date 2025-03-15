FROM node:20.18.3-alpine3.21
RUN addgroup -S expense && adduser -S sai -G expense && \
    mkdir /opt/backend && \
    chown -R sai:expense /opt/backend 
WORKDIR /opt/backend
COPY package.json .
RUN npm install 
COPY *.js .
USER sai
ENV DB_HOST="mysql"
EXPOSE 80
CMD ["node", "index.js"]