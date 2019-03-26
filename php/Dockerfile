FROM php:7

ARG composer_url=https://getcomposer.org/installer

ENV COMPOSER_ALLOW_SUPERUSER=1
ENV PATH=$PATH:vendor/bin

RUN apt-get update && apt-get install -y --no-install-recommends \
      curl \
      git \
      python-dev \
      python-pip \
      zlib1g-dev \
      libzip-dev
RUN pip install --upgrade setuptools
RUN pip install awscli
RUN docker-php-ext-install zip
RUN curl -o installer "$composer_url"
RUN php installer --install-dir=/usr/local/bin --filename=composer
RUN rm -rf /var/lib/apt/lists/*
