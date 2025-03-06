FROM almalinux:9
RUN dnf install nginx -y
RUN rm -rf /usr/share/nginx/html/index.html
ONBUILD COPY index.html /usr/share/nginx/html/index.html
ONBUILD WORKDIR /usr/share/nginx
CMD ["nginx", "-g", "daemon off;"]

