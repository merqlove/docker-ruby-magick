FROM ruby:2.6.6-slim-buster

ARG RAILS_ROOT=/app
ARG PACKAGES="libpq-dev nodejs nginx tzdata imagemagick"

ENV RAILS_ENV=production
ENV BUNDLE_APP_CONFIG="$RAILS_ROOT/.bundle"

WORKDIR $RAILS_ROOT

# install packages
RUN apt-get update \
    && apt-get install -y curl gnupg1 apt-transport-https \
    && curl --silent --show-error --location https://deb.nodesource.com/gpgkey/nodesource.gpg.key | apt-key add - \
    && echo "deb https://deb.nodesource.com/node_10.x/ stretch main" | tee /etc/apt/sources.list.d/nodesource.list \
    && apt-get update \
    && apt-get install -y --no-install-recommends $PACKAGES \
    && apt-get autoremove -y curl gnupg1 apt-transport-https \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && gem install bundler --no-document
