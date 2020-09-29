---
layout: posts
title: "TypeScript 2주차"
date:   2020-09-29
categories: /typescript
comments:
toc: true
toc_sticky: true
---
> 타입스크립트, AWS 서버리스로 들어올리다

# 🔗Chapter 03
## Node.js

V8이라는 구글에서 개발한 고성능 자바스크립트 엔진으로 네트워크 애플리케이션 개발에 주로 사용되는 소프트웨어 플랫폼

## npm(Node Package Manager)

자바스크립트 언어를 위한 패키지 매니저이고 Node.js에서는 npm을 기본 패키지 매니저로 사용
<br>
프로젝트 기본정보 입력 `$ npm init`

## cli(Command line interface)

윈도우는 명령어 프롬프트(cmd.exe), 맥OS나 리눅스는 터미널(terminal)창에서 작업 명령을 직접 입력과 출력을 통해서 원하는 작업을 처리하는 방식

## 포스트맨(PostMan)

개발한 API를 테스트하고, 테스트 결과를 공유하여 API 개발의 생산성을 높여주는 플랫폼

# 🔗Chapter 04
## AWS console

직관적이지만 소프트웨어를 업데이트 하거나 변경하려고 하면 그 작업을 다시 진행하거나 수정해야함
<br>
과정을 빼먹거나 잘못하는 경우가 있을 수 있음

## AWS-cli

한번 전체 과정을 제작하고 테스트와 배포를 스크립트화시켜두면 소스 관리가 가능해짐
<br>
aws의 서비스를 이해하고 운영해야하는 단점이 있음

## API 게이트웨이

|Authorizers|HTTP API|REST API|
|------|---|---|
|AWS Lambda||✔️|
|IAM||✔️|
|Amazon Cognito|✔️|✔️|
|Native OpenID Connect/OAuth 2.0|✔️||

# 🔗Chapter 05
### 서버리스 프레임워크

- 소프트웨어 개발만 전념할 수 있다
- 배포(Deploy)와 테스트(Test)는 자동화가 가능하고 간편하다
- 개발과 테스트에 드는 시간을 절약할 수 있다
- 초기 개발 세팅이 간편하다