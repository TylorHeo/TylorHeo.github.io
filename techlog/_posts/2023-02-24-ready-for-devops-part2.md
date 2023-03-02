---
layout: post
title: "데브옵스 준비하기 - Kubernetes Cluster 접근 구성"
subtitle: "Ready for DevOps Part2"
category: techlog
tags: devops
---

![tylor](/assets/img/techlog/k9s.png){: width="320" height="320"}

DevOps 조직이 있는 회사라면 대부분 Kubernetes를 운영하고 계실꺼라 생각합니다.  
이전글에서 Iterm2와 oh my zsh을 설치했다면, 여기에 더해서 Kubernetes를 운영하기 위한 환경을 구성해 보겠습니다.
## Kubernetes 작업 도구들
kubernetes는 Cluster API 서버를 통해 요청을 보내기에 가장 기본 툴인 `kubectl cli`를 설치합니다.  
~~~shell
$ brew install kubernetes-cli
~~~
더불어 kubectx는 `kube context`와 `namespace`를 편하게 변경 가능합니다.  
~~~shell
$ brew install kubectx
~~~
이 때, kubectx나 kubens를 실행하면 나오는 리스트에서 방향기로 선택할 수 있는 `fzf`도 같이 설치합니다.
~~~shell
$ brew install fzf
~~~
최근에는 이것들을 하나의 화면에서 작업 가능한 terminal UI인 [k9s](https://k9scli.io/)도 많이 사용하고 있습니다.  
~~~shell
$ brew install derailed/k9s/k9s
~~~
## AWS 인증 구성
AWS EKS에 접근하기 위해서는 credentials 파일에 access_key와 secret_key 구성이 우선 되어야 합니다.
~~~shell
$ vi ~/.aws/credentials

[default]
aws_access_key_id=[access_key]
aws_secret_access_key=[secret_key]

[tylor-live]
aws_access_key_id=[access_key]
aws_secret_access_key=[access_key]
~~~
참고로 위의 key 계정에는 권한을 부여하지 않습니다.  
대신 role을 연결하여 임시자격증명을 얻을 수 있도록 아래와 깉이 config도 구성을 합니다.
~~~shell
$ vi ~/.aws/config

[default]
role_arn = [user_role_arn]
source_profile = default
region = ap-northeast-2
mfa_serial = [access_key_account_mfa_arn]

[profile tylor-live]
role_arn = arn:aws:iam::[account_id]:role/[role_name]
source_profile = tylor-live
region = ap-northeast-2
mfa_serial = arn:aws:iam::[account_id]:mfa/[iam_key_user]
~~~
<!--more-->
