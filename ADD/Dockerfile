FROM almalinux:9
RUN dnf install nginx -y
RUN rm -rf /usr/share/nginx/html/index.html
ADD https://raw.githubusercontent.com/lakshmikanth333/terraform/refs/heads/main/workspace/workspace/main.tf /usr/share/nginx/html/index.html
RUN chmod +r /usr/share/nginx/html/index.html
ADD hello.txt /
ADD aws.tar /
CMD ["nginx", "-g", "daemon off;"]