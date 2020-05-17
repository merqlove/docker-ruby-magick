FROM ruby:2.4.2-slim-stretch

ARG RAILS_ROOT=/app
ARG PACKAGES="libpq-dev nginx tzdata imagemagick"

ENV RAILS_ENV=production
ENV BUNDLE_APP_CONFIG="$RAILS_ROOT/.bundle"

WORKDIR $RAILS_ROOT

# install packages
RUN apt-get update \
    && apt-get install -y --no-install-recommends $PACKAGES \
    && rm -rf /var/lib/apt/lists/* \
    && gem install bundler --no-document
