FROM node:alpine
RUN addgroup -S expense && adduser -S sai -G expense
USER sai
RUN mkdir /opt/backend
RUN chown -R sai:expense /opt/backend
WORKDIR /opt/backend
COPY package.json .
COPY *.js .
RUN npm install
RUN useradd sai
ENV DB_HOST="mysql"
CMD ["node", "index.js"]
