FROM nginx:latest

ARG TZ=UTC
ENV TZ ${TZ}
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime

RUN apt-get update && apt-get install -y \
    openssl \
    ssl-cert \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /var/www
