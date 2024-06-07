FROM alpine:latest
RUN apk update
RUN apk add --no-cache nginx
RUN update-ca-certificates
COPY gitlabserver.com.crt /usr/local/share/ca-certificates/gitlabserver.com.crt
RUN cat /usr/local/share/ca-certificates/gitlabserver.com.crt >> /etc/ssl/certs/ca-certificates.crt
RUN echo '192.168.10.10 gitlabserver.com.crt' >> /etc/hosts
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]