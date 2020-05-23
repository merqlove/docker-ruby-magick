FROM ruby:2.4.2-alpine

ARG RAILS_ROOT=/app
ARG PACKAGES="tzdata postgresql-client nodejs bash imagemagick"

ENV RAILS_ENV=production
ENV BUNDLE_APP_CONFIG="$RAILS_ROOT/.bundle"

WORKDIR $RAILS_ROOT

# install packages
RUN apk update \
    && apk upgrade \
    && apk add --update --no-cache $PACKAGES \
    && gem install bundler --no-document
