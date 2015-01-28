FROM ubuntu:14.04

RUN apt-get update

RUN apt-get -y install wget build-essential openssl libreadline6 libreadline6-dev libpq-dev

RUN apt-get -y install libpcre3-dev unzip

RUN wget http://openresty.org/download/ngx_openresty-1.7.7.1.tar.gz

RUN tar xvfz ngx_openresty-1.7.7.1.tar.gz

RUN wget https://github.com/FRiCKLE/ngx_cache_purge/archive/master.zip

RUN unzip master.zip

RUN apt-get -y install libxml2 libxslt1-dev

RUN mkdir Nginx

WORKDIR /ngx_openresty-1.7.7.1

RUN ./configure --prefix=/Nginx --without-http_echo_module --without-http_xss_module --without-http_set_misc_module --without-http_form_input_module --without-http_encrypted_session_module --without-http_srcache_module --without-http_array_var_module --without-http_memc_module --without-http_redis2_module --without-http_upstream_keepalive_module --without-http_rds_json_module --without-http_ssl_module --with-http_postgres_module --with-http_stub_status_module  --add-module=/ngx_cache_purge-master

RUN make

RUN make install
