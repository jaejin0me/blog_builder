---
title: "책뿌수기 - 기초가 든든한 데이터 베이스 4"
date: 2018-11-28T01:15:56+09:00
draft: false
tags: ["database"]
categories: ["database"]
author: "Jaejin Jang"
---

*인용하는 그림은 다양한 곳에서 가져왔음을 밝힙니다*

# Ch 4. 관계 대수

## Section 1. 관계 대수

* 관계 대수는 릴레이션을 처리하는 연산의 집합
 * 관계 대수의 피연산자는 릴레이션
 * 연산 결과도 릴레이션
 * 원하는 정보를 유도하는 절차적 언어

![Fig](/posts94_1.jpg "posts94_1.jpg")

![Fig](/posts94_2.jpg "posts94_2.jpg")

## Section 2. 일반 집합 연산자

* 합/교/차집합 연산은 두 릴레이션이 합병 가능(union-compatible = 속성의 개수가 같고, 도메인이 같아야 한다) 해야 한다.

## Section 3. 순서 관계 연산자

3.3 조인 연산자
* 두 개의 릴레이션의 공통 속성을 기준으로 속성값이 같은 튜플들을 수평으로 결합해 하나의 릴레이션을 만드는 것
* 카티션 프로덕트를 적용한 후 셀렉트를 한것과 같다.

3.3.1 동등 조인
* 속성값이 같은 튜플 결합
3.3.2 자연 조인
* 동등 조인의 결과에서 중복 속성 제거
3.3.3 외부 조인
* 상대 릴레이션에 대응 되는 튜플을 갖지 못하거나 NULL인 튜플을 다룬다. 관련된 튜플이 없으면 속성을 NULL로 채운다
3.3.4 디비전 조인
* 속성이 일치하는 튜플에서 해당 속성만 제외한 릴레이션 만들기