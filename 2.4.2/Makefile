VERSION ?= 2.4.2

all: build push

build:
	docker build -t merqlove/ruby-magick:${VERSION} .

push:
	docker push merqlove/ruby-magick:${VERSION}
