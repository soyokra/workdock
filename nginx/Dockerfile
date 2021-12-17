FROM nginx:latest

LABEL maintainer="pingink <pingink@163.com>"

COPY nginx.conf /etc/nginx/

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
