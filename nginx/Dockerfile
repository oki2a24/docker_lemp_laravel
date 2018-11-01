FROM nginx:alpine

ARG TZ=UTC
ENV TZ ${TZ}
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime

COPY ./conf.d/default.conf /etc/nginx/conf.d/

WORKDIR /var/www
