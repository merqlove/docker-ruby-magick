VERSION ?= 2.6.6

all: build push

build:
	docker build -t merqlove/ruby-magick:${VERSION} .

push:
	docker push merqlove/ruby-magick:${VERSION}
