---
layout: post
title: "GitHub Page"
date: 2023-01-26T14:25:52-05:00
author: jaeyong pae
categories: jekyll
tags: docker jekyll
cover: "/assets/chicken_01.jpg"
---

예전부터 했어야 할 일을 이제서야 하는거임. 약간의 강요가 포함되어 시작하게 됐음.

[Medium](https://medium.com/), [브런치](https://brunch.co.kr/), velog, github 무료이면서 포맷을 자유롭게 사용할 수 있는 플랫폼을 택하면 github 인듯

## GitHub Page

github page 설정

## Editing Configuration

Ruby 개발을 할수도 있겠지만 당장은 Javascript 와 Pyhton 위주일듯 하여 또다른 환경을 맥북에 세팅하는게 부담이기 때문에 Docker 에 에디팅 환경을 구성하기로 함

### Docker

{% highlight html %}
FROM ruby:3.2.0-alpine3.17

RUN apk update
RUN apk add --no-cache build-base gcc cmake git

RUN gem update bundler
{% endhighlight %}

{% highlight html %}
docker build -t chaossin/jekyll .

docker run --name blog --volume="$PWD:/srv/jekyll" -p 4000:4000 -it chaossin/jekyll
{% endhighlight %}

{% highlight html %}
bundle install

bundle exec jekyll serve --host 0.0.0.0 -p 4000
{% endhighlight %}

### Jekyll

### Jekyll Theme
