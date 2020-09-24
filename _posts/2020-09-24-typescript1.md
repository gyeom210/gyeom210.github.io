---
layout: posts
title: "TypeScript 1주차"
date:   2020-09-24
categories: /typescript
comments:
toc: true
toc_sticky: true
---
> 타입스크립트, AWS 서버리스로 들어올리다

# ✏️Chapter 01
## 서버리스(Serverless)
서버리스는 단순하게 번역하면 '서버가 없다'라는 의미이다. 하지만 사실상 서버가 없는것은 아니며, 특정 작업을 수행하기 위해서 컴퓨터를 혹은 가상머신에 서버를 설정하고 이를 통하여 처리 하는 것이 아님을 의미합니다.
<br>
**백엔드형서비스(BaaS)**와 **함수형서비스(FaaS)** 두가지로 나뉜다.

## 백엔드형서비스(BaaS:Backend as a Service)

백엔드인 관리자 영역을 모듈화하여 제공하는 서비스
<br>
필요한 기능을 쉽고 빠르게 구현할 수 있기때문에 개발 시간을 단축할 수 있다는것과 서버 확장 작업이 필요없다는 장점이 있다. 하지만 무료 구간을 넘어가 서비스 규모가 커진다면 지출되는 비용이 사용하는 만큼 늘어나는 단점이 있다.
<br>
실시간 데이터베이스 같은 경우에는 NoSQL 기반에 JSON 형태로 데이터가 저장되어 있기때문에 관계형데이터베이스(RDBMS:relational database management system)에서와 같이 복잡한 쿼리를 만들기 어렵다.

## 함수형서비스(FaaS:Function as a Service)

원하는 로직을 함수로 등록 해 놓은뒤 특정 이벤트가 발생했을 때 실행과 종료를 제공하는 서비스
<br>
대표적인 서비스가 AWS의 람다(Lambda)이다.
<br>
서버가 대기하면서 사용자의 요청을 처리하는 것이 아니라 요청한 횟수만큼 요금을 지불하면 되며 요청량에 따라 서버는 알아서 확장 및 축소한다.
<br>
하지만 특정 시간 동안 함수의 호출이 없다면 비활성화(deactivate) 상태로 들어가게 되어 응답이 지연된다는 단점이 있다.

## AWS 람다([AWS Lambda](https://docs.aws.amazon.com/ko_kr/lambda/latest/dg/welcome.html))

아마존 웹 서비스(AWS:Amazon web servier)에서 제공하는 서버리스 컴퓨팅 서비스
<br>

# ✏️Chapter 02
## AWS

AWS에서는 전 세계의 주요 지역에 리전을 위치시키고 가까운 리전으로 접속해서 빠른 속도를 낼수 있다.
<br>
리전(Regions)은 운영되는 서버의 물리적 위치이며 리전 내에서는 가용영역으로 나눠 있다. 기본적으로 리전은 2개 이상의 가용영역을 가지고 있으며 예상하지 못한 재해가 발생할경우 다른 리전에 데이터가 백업 되어있다면 정상적으로 서비스 운영이 가능하다.

## EC2(Elastic Compute Cloud)

실제 서버를 임대하는 것이 아니라, 가상 서버를 필요한 만큼 비용을 지불하고 임대해서 사용하는 웹 서비스이며 AWS의 대표적인 서비스

## Route 53

웹 기반의 DNS 서비스
<br>
사용자의 요청을 EC2 instance, [Elastic Load Balancing](https://m.blog.naver.com/ijoos/221545031458), S3 bucket 등 AWS에서 실행되는 인프라에 효과적으로 DNS와 연결해준다.

## VPC(Virtual Private Cloud)

AWS상의 논리적으로 격리된 가상 네트워크를 생성할 수 있는 웹 서비스
<br>
보안을 위해 AWS 리소스간 허용을 최소화하고 그룹별로 손쉽게 네트워크를 구성하기 위해 사용

## S3(Amazon Simple Storage Service)

제공하는 단순한 웹 서비스 인터페이스를 통해 웹에서 언제 어디서나 원하는 데이터를 저장할 수 있는 인터넷용 스토리지 서비스
<br>
데이터의 사용 빈도에 따라 여러 저장분류 선택 가능하다.

## 관계형 데이터베이스(RDS:Relational Databases Store)

참조 무결성을 유지하면서 사전에 정의된 스키마(schema)와 이들 사이의 관계로 데이터를 저장하며 ACID 트랜잭션을 지원한다.
