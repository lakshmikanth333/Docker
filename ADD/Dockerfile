FROM almalinux:9
RUN dnf install nginx -y
RUN rm -rf /usr/share/nginx/html/index.html
ADD https://raw.githubusercontent.com/lakshmikanth333/terraform/refs/heads/main/workspace/workspace/main.tf /usr/share/nginx/html
RUN +x /usr/share/nginx/html
RUN +r /usr/share/nginx/html
CMD ["nginx", "-g", "daemon off;"]