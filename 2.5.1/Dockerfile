FROM ruby:2.5.1-slim-stretch

ARG RAILS_ROOT=/app
ARG PACKAGES="libpq-dev nodejs nginx tzdata imagemagick"

ENV RAILS_ENV=production
ENV BUNDLE_APP_CONFIG="$RAILS_ROOT/.bundle"

WORKDIR $RAILS_ROOT

# install packages
RUN apt-get update \
    && apt-get install -y curl gnupg1 apt-transport-https
RUN curl --silent --show-error --location https://deb.nodesource.com/gpgkey/nodesource.gpg.key | apt-key add - \
    && echo "deb https://deb.nodesource.com/node_10.x/ stretch main" | tee /etc/apt/sources.list.d/nodesource.list
RUN apt-get update \
    && apt-get install -y --no-install-recommends $PACKAGES

RUN gem install bundler --no-document
