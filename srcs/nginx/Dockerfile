FROM alpine:3.12.1
EXPOSE 22
EXPOSE 80
EXPOSE 443
RUN apk update
RUN apk add openrc
RUN rc-status
RUN touch /run/openrc/softlevel
RUN wget http://dl-cdn.alpinelinux.org/alpine/v3.13/community/x86_64/telegraf-1.17.0-r0.apk
RUN apk add telegraf-1.17.0-r0.apk
RUN apk add nginx
COPY default.conf /etc/nginx/conf.d
COPY example.crt /
COPY example.key /
COPY telegraf.conf /
COPY run.sh /
CMD sh /run.sh