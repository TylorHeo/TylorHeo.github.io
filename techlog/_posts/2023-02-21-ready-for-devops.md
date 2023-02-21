---
layout: post
title: "데브옵스 준비하기"
subtitle: "Ready for DevOps"
category: techlog
tags: devops
---

![tylor](/assets/img/tylor_macbook.jpg){: width="210" height="210"}

데브옵스 업무를 시작하기 전에 생산성을 높일 유용한 도구들을 먼저 설치해 보겠습니다.  
다만, 최근 대부분의 회사들에서 맥북을 지급하고 있기에 맥북 M1을 기준으로 셋팅해 보겠습니다.

### Kubernetes 작업 도구들
kubernetes는 Cluster API 서버를 통해 요청을 보내기에 가장 기본 툴인 kubectl cli를 설치합니다.  
~~~shell
brew install kubernetes-cli
~~~
더불어 kubectx는 kube context와 namespace를 편하게 변경 가능합니다.  
~~~shell
brew install kubectx
~~~
이 때, kubectx나 kubens를 실행하면 나오는 리스트에서 방향기로 선택할 수 있는 fzf도 같이 설치 합니다..  
~~~shell
brew install fzf
~~~
최근에는 이것들을 하나의 화면에서 작업 가능한 terminal UI인 [k9s](https://k9scli.io/)도 많이 사용하고 있습니다.  
~~~shell
brew install derailed/k9s/k9s
~~~
<!--more-->
