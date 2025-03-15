FROM node:20.18.3-alpine3.21
RUN addgroup -S expense && adduser -S sai -G expense \
    mkdir /opt/backend \
    chown -R sai:expense /opt/backend \
WORKDIR /opt/backend
COPY package.json .
COPY *.js .
RUN npm install
USER sai
ENV DB_HOST="mysql"
CMD ["node", "index.js"]