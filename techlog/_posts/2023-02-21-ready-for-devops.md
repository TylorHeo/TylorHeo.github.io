---
layout: post
title: "데브옵스 준비하기"
subtitle: "Ready for DevOps"
category: techlog
tags: devops
---

![tylor](/assets/img/tylor_macbook.jpg){: width="210" height="210"}

데브옵스 업무를 시작하기 전에 생산성을 높일 유용한 도구들을 먼저 설치해 보겠습니다.  
최근의 거의 모든 회사들이 맥북을 업무용 PC로 지급하고 있기에 맥북 M1을 기준으로 셋팅해 보겠습니다.

### ITerm2와 zsh로 터미널 변경
기본 터미널에 bash shell은 정말 검은 바탕에 흰색 글씨만 있기에 좀 더 아름답고 효울적인 터미널 환경으로 변경하고자 합니다.
#### zsh 및 oh-my-zsh 설치
oh my zsh에서 제공하는 테마나 플러그인을 위해 우선은 zsh을 먼저 설치하고 기본 쉘로 변경 합니다.
~~~shell
$ brew install zsh
$ which zsh #결과로 /usr/local/bin/zsh 출력
$ chsh -s `which zsh` # which 명령 대신 위의 출력 결과를 아래와 같이 직접 입력해도 됨
$ chsh -s /usr/local/bin/zsh # 위의 which zsh를 직접 입력해도 됨
~~~
설치 이후 터미널을 재시작하면 zsh로 변경이 된 것을 확인 합니다.
그러면 oh my zsh를 다운 받고 설치 합니다.
~~~shell
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
~~~
oh my zsh까지 설치가 되면 [ITerm2](https://iterm2.com/)에서 설치파일을 다운받습니다.  

![iterm2](/assets/img/techlog/iterm2_web.png){: width="50%" height="50%"}
### Kubernetes 작업 도구들
kubernetes는 Cluster API 서버를 통해 요청을 보내기에 가장 기본 툴인 kubectl cli를 설치합니다.  
~~~shell
brew install kubernetes-cli
~~~
더불어 kubectx는 kube context와 namespace를 편하게 변경 가능합니다.  
~~~shell
brew install kubectx
~~~
이 때, kubectx나 kubens를 실행하면 나오는 리스트에서 방향기로 선택할 수 있는 fzf도 같이 설치 합니다.
~~~shell
brew install fzf
~~~
최근에는 이것들을 하나의 화면에서 작업 가능한 terminal UI인 [k9s](https://k9scli.io/)도 많이 사용하고 있습니다.  
~~~shell
brew install derailed/k9s/k9s
~~~
<!--more-->
