VERSION ?= 2.5.1

all: build push

build:
	docker build -t merqlove/ruby-magick:${VERSION} .

push:
	docker push merqlove/ruby-magick:${VERSION}
