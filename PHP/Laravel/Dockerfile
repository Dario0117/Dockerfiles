# Para  crear un proyecto:
# - Con la versión que quieras usa 'composer create-project laravel/laravel [nombre] [version]'
# - Con la versión más reciente usa 'laravel new [nombre]'
# Para crear el contenedor usa 'sudo docker run --name [nombre] --net host -it [nombre_imagen] bash'

FROM ubuntu:16.04
LABEL maintainer "Esteban D. Barboza Primera <dario0117@gmail.com>"

ENV DEBIAN_FRONTEND="noninteractive" PATH="$PATH:/root/.composer/vendor/bin"

RUN apt-get update && \
    apt-get install -y software-properties-common \
    locales && \
    locale-gen en_US.UTF-8 && \
    export LANG="en_US.UTF-8" && \
    add-apt-repository -y ppa:ondrej/php && \
    apt-get update && \
    echo 'America/Bogota' > /etc/timezone && \
    apt-get install -y --allow-unauthenticated php7.2 php7.2-mbstring php7.2-xml php7.2-zip && \
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');" && \
    mv composer.phar /usr/local/bin/composer && \
    composer global require "laravel/installer" && \
    rm -rf /var/lib/apt/lists/*
