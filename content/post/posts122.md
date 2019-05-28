---
title: "자바 쓰레드 관련 정리"
date: 2017-12-23T01:37:56+08:00
draft: false
tags: ["java"]
categories: ["java"]
author: "Jaejin Jang"
---

자바에서 쓰레드를 사용하는 건 참 쉽죠잉~. 쓰레드 관련 공부한 내용 정리합니다.

쓰레드란 ?  하나의 프로세스 안에서 실제적으로 작업을 처리하는 단위이다

main인 메솓를 실행하는 스레드가 기본적으로 존재한다.

join() 메소드 : 특정한 쓰레드가 실행 된 후에 다른 쓰레드가 실행되도록 제어하는 메소드이다. join()메솓를 호출한 스레드가 끝날때까지 다른 쓰레드는 대기한다.
(여담으로 이름으 join인 이유는, 예전에 프로세스를 fork=분기 해서 복사한 다음에 마칠때는 다같이 합쳐서=join해서 마친다는 의미로 해석하시면 이해하기 편합니다.

쓰레드의 우선 순위가 높으면 CPU를 더 많이 사용할 수 있다. 해야할 작업이 많은 쓰레드의 우선순위를 높여줌으로써 더 많은 작업을 하게 해준다. .setPriority() 메소드를 이용한다.

하나의 자원에 여러개의 쓰레드가 동시에 접근하지 못하도록 동기화 기능이 필요하다. 동기화는 메소드에 synchronized를 붙여서 메소드를 동기화 하는 방법과 클래스에서는 sychronized(this)와 같이 동기화 블럭을 사용하여 클래스 접근의 동기화를 해주는 두가지 방법이 있다.

동기화 기능에 더하여 제어권을 직접적으로 제어할 수 있다면 더 많은 작업을 할 수 있을것이다. 이 제어를 위한 메소드들이 wait(), notify(), notifyAll()이다. 이 메소드드들은 동기화 블럭 안에서만 사용할 수 있다. 참고로 Thread 클래스에서 제공되는 메소드가 아니라 Object 메소드에서 제공되는 메소드 이다. notify(), notifyAll()을 해주면 wait하던 쓰레드가 바로 Running이 되는건 아니고 Runnable상태가 되는 것이다.

Thread 클래스에서 내가 몰랐던 메소드들
void interrupt() : 쓰레드에 인터럽트 생성
void sleep(long millis) : 밀리초 동안 실행 정지
void yield() : 다른 쓰레드에게 CPU 양보