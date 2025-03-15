# # Stage 1

# FROM node:latest AS builder
# WORKDIR /opt/backend
# COPY package.json .
# RUN npm install 
# COPY *.js .

# # Stage 2 
# FROM node:20.18.3-alpine3.21
# RUN addgroup -S expense && adduser -S sai -G expense && \
#     mkdir /opt/backend && \
#     chown -R sai:expense /opt/backend 
# WORKDIR /opt/backend
# USER sai
# ENV DB_HOST="mysql"
# COPY --from=builder /opt/backend /opt/backend/
# CMD ["node", "index.js"]

FROM node:20
RUN addgroup -S expense && adduser -S sai -G expense && \
    mkdir /opt/backend && \
    chown -R sai:expense /opt/backend 
WORKDIR /opt/backend
COPY package.json .
COPY *.js .
RUN npm install
USER sai
ENV DB_HOST="mysql"
CMD ["node", "index.js"]
