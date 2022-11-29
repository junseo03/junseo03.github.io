---
layout: post
title:  "Google Analytics"
date:   2022-11-29 23:20:26 +0900
categories: jekyll update
comments: true
---

## 1.Google Analytics 계정 생성

계정을 만들었다면 Data Streams → Choose Platform 에서 하나를 선택하고 내 웹사이트를 등록한다.

웹사이트를 등록하면 Measurement ID가 만들어진다.

## 2.Google Analytics, Jekyll에 적용

우선 analytics.html 이라는 새로운 파일을 _includes 폴더 안에 만들어 준다.

analytics.html 파일 안에 다음과 같이 채워준다.

{% highlight ruby %}
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-XXXXXXXXXX');
</script>
{% endhighlight %}

'G-XXXXXXXXXX' 부분을 아까 만든 Measurement ID 바꿔준다.

Jekyll이 프로젝트를 빌드할때 analytics.html를 모든 페이지에 추가하기 위해 {% include analytics.html %}를 default.html의 헤드에 추가한다.

마지막으로 빌드하면 Google Analytics에서 트레픽 정보를 확인할 수 있다.