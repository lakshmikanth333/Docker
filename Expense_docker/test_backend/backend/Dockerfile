# Stage 1

FROM node:20.18.3-alpine3.21 AS builder
WORKDIR /opt/backend
COPY package.json .
RUN npm install 
COPY *.js .

# Stage 2 
FROM node:20.18.3-alpine3.21
RUN addgroup -S expense && adduser -S sai -G expense && \
    mkdir /opt/backend && \
    chown -R sai:expense /opt/backend 
WORKDIR /opt/backend
USER sai
ENV DB_HOST="mysql"
COPY --from=builder /opt/backend /opt/backend/
CMD ["node", "index.js"]
