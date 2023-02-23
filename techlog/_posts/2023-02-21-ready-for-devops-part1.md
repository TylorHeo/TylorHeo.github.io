---
layout: post
title: "데브옵스 준비하기 - iterm2 터미널 설치 및 셋팅"
subtitle: "Ready for DevOps part1"
category: techlog
tags: devops
---

![tylor](/assets/img/tylor_macbook.jpg){: width="210" height="210"}

데브옵스 업무를 시작하기 전에 생산성을 높일 유용한 도구들을 먼저 설치해 보겠습니다.  
최근에는 거의 모든 회사들이 맥북을 업무용 PC로 지급하고 있기에, 모든 설치 가이드는 맥북 M1을 기준으로 셋팅해 보겠습니다.
### ITerm2와 zsh로 터미널 변경
기본 터미널에 bash shell은 정말 검은 바탕에 흰색 글씨만 있기에 좀 더 아름답고 효울적인 터미널 환경으로 변경하고자 합니다.
#### zsh 및 oh-my-zsh 설치
oh my zsh에서 제공하는 테마나 플러그인을 위해 우선은 zsh을 먼저 설치하고 기본 쉘로 변경합니다.
~~~shell
$ brew install zsh
$ which zsh #결과로 /usr/local/bin/zsh 출력
$ chsh -s `which zsh` # which 명령 대신 위의 출력 결과를 아래와 같이 직접 입력해도 됨
$ chsh -s /usr/local/bin/zsh # 위의 which zsh를 직접 입력해도 됨
~~~
설치 이후 터미널을 재시작하면 zsh로 변경이 된 것을 확인합니다.
그러면 oh my zsh를 다운 받고 설치합니다.
~~~shell
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
~~~
oh my zsh까지 설치가 되면 [ITerm2](https://iterm2.com/)에서 설치파일을 다운받습니다.

![iterm2](/assets/img/techlog/iterm2_web.png){: width="60%" height="60%"}  

설치하고 spotlight에서 iterm으로 실행하면 아래와 같은 터미널을 만날 수 있습니다.
![iterm2](/assets/img/techlog/iterm2_first.png){: width="70%" height="70%"}

이제 oh my zsh을 이용하여 나에게 맞는 zsh 환경을 만들어 보겠습니다.
먼저 .zshrc에서 ZSH_THEME를 `agnoster` 변경합니다.
~~~shell
$ vi ~/.zshrc
~~~
![iterm2](/assets/img/techlog/zsh_theme.png){: width="70%" height="70%"}

그리고 iterm에서 `command + ,` 조합키를 눌러서 `Preferences` 를 실행하고, `Profiles > Colors` Tab에서 `Colorpresets를 Solarized Dark` 로 변경합니다.  
그 다음으로는 `Text` Tab에서 Font를 바꾸기 위해 [Ubuntu_Mono_derivative_Powerline.ttf](https://github.com/HeeTop/images/blob/master/myblog/oh-my-zsh/Ubuntu_Mono_derivative_Powerline.ttf?raw=true)를 받아서 설치하고, 해당 폰트와 `18pt`로 셋팅합니다.

![iterm2](/assets/img/techlog/iterm2_text.png){: width="80%" height="80%"}

#### oh-my-zsh 플러그인 설치