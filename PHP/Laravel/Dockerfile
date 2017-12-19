# Para  crear un proyecto:
# - Con la versión que quieras usa 'composer create-project laravel/laravel [nombre] [version]'
# - Con la versión más reciente usa 'laravel new [nombre]'
# Para crear el contenedor usa 'sudo docker run --name [nombre] --net host -it [nombre_imagen] bash'

FROM ubuntu:16.04
LABEL maintainer "Esteban D. Barboza Primera <dario0117@gmail.com>"

RUN apt-get update 
RUN apt-get install -y software-properties-common
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get install -y locales
RUN locale-gen en_US.UTF-8
ENV LANG=en_US.UTF-8
RUN add-apt-repository -y ppa:ondrej/php
RUN apt-get update
RUN echo 'America/Bogota' > /etc/timezone
RUN apt-get install -y --allow-unauthenticated php7.2 php7.2-mbstring php7.2-xml php7.2-zip
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer
RUN composer global require "laravel/installer"
ENV PATH="$PATH:/root/.composer/vendor/bin"