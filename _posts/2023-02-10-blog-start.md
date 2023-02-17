---
layout: post
title: "GitHub Page"
date: 2023-02-10T14:25:52-05:00
author: jaeyong pae
categories: Jekyll
tags: docker jekyll
cover: "/assets/chicken_01.jpg"
published: true
---

예전부터 하고싶기도(?) 해야만하기도(?) 했던 일을 늦었지만... 약간의 강요(?)가 포함되어 시작하게 된것 같습니다. 개발자로서 스스로에게 남는것은 기록뿐...

[Medium](https://medium.com/), [브런치](https://brunch.co.kr/), [velog](https://velog.io/), [github](https://github.com/) 4가지 플랫폼 중 무료이면서 포맷을 자유롭게 사용할 수 있는 플랫폼으로 github 선택하게되었습니다.

# GitHub Page

### Create New Repository

![New Repository](/assets/20230210/01.NewRepository.png)

### GitHub Pages Settings

![Setting Page](/assets/20230210/02.Setting.Page.png)

# Local Editing Configuration

Ruby 개발을 할수도 있겠지만 당장은 Javascript 와 Pyhton 위주일듯 하여 또다른 환경을 맥북에 세팅하는게 부담이기 때문에 Docker 에 에디팅 환경을 구성하기로 함 ( React 도 익숙해질 겸 [Gatsby](https://www.gatsbyjs.com/) 로 다시 바꾸고 싶음 ㅜㅜ )

### Docker

dockerfile 내용
{% highlight html %}
FROM ruby:3.2.0-alpine3.17

RUN apk update
RUN apk add --no-cache build-base gcc cmake git

RUN gem update bundler
{% endhighlight %}

docker image 생성 및 container 생성
{% highlight html %}
docker build -t chaossin/jekyll .

docker run --name blog --volume="$PWD:/srv/jekyll" -p 4000:4000 -it chaossin/jekyll
{% endhighlight %}

### Jekyll

{% highlight html %}
bundle install

bundle exec jekyll serve --host 0.0.0.0 -p 4000 --unpublished
{% endhighlight %}

### Jekyll Theme

[centrarium](https://github.com/bencentra/centrarium) 사용
