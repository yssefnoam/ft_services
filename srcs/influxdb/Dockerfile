FROM alpine:3.12.1
EXPOSE 8086
RUN apk update
RUN apk add openrc
RUN rc-status
RUN touch /run/openrc/softlevel
RUN apk add influxdb
RUN wget http://dl-cdn.alpinelinux.org/alpine/v3.13/community/x86_64/telegraf-1.17.0-r0.apk
RUN apk add telegraf-1.17.0-r0.apk
COPY telegraf.conf /
COPY run.sh /
CMD sh run.sh