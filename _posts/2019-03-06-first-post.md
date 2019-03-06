---
layout: post
title:  "Apache Tomcat Tuning_1"
date:   2019-03-06 12:30:25
categories: tomcat
tags: featured
---

이 글에서는 가장 대중적으로 사용하는 Apache Tomcat WAS에 대하여 작성해보도록 하겠습니다.

처음으로 Tomcat Tuning Parameter에 관하여 설명드리겠습니다.

톰캣 대부분의 튜닝은 파라미터는 server.xml에 정의된다.
Connector 설정에 추가 <a>http://tomcat.apache.org/tomcat-8.5-doc/config/http.html</a> 참고

* protocol : protocol setting인데, Tomcat은 네트워크 통신하는 부분에 대해서 3가지 정도의 옵션을 제공. NIO, NIO2, APR 3가지.
* acceptCount : 가능한 모든 요청 처리 스레드가 사용 중일 때 들어오는 연결 요청의 최대 대기열 길이입니다 (큐 길이).
대기열이 가득 찼을 때 받은 요청은 거부됩니다. 기본값은 100입니다.
*	maxConnections : 최대 연결 수. NIO 및 NIO2의 경우 기본값은 10000, ARP 및 네이티브의 경우 기본값은 8192 입니다.
*	maxKeepAliveRequests : 서버가 연결을 닫을 때까지 파이프 라인 될 수있는 최대 HTTP 요청 수입니다. 이 속성을 1로 설정하면 HTTP / 1.0 keep-alive 및 HTTP / 1.1 연결 유지 및 파이프 라이닝이 비활성화됩니다. 이 값을 -1로 설정하면 파이프 라인 또는 연결 유지 HTTP 요청을 무제한으로 허용합니다. 지정하지 않으면 이 속성은 100으로 설정.
(Client가 접속된 시간 동안 Server에 요청할 수 있는 처리 process 개수)
*	maxThreads : 스레드 의 최대 수. 따라서 처리 할 수있는 최대 동시 요청 수를 결정합니다. 지정되지 않으면 이 속성은 200으로 설정됌
*	tcpNoDelay : TCP 프로토콜은 기본적으로 패킷을 보낼때 바로 보내지 않는다. 작은 패킷들을 모아서 버퍼 사이즈가 다 차면 모아서 보내는 로직을 사용한다. 그래서 버퍼가 4K라고 가정할때, 보내고자 하는 패킷이 1K이면 3K가 찰 때 까지 기다리기 때문에, 바로바로 전송이 되지 않고 대기가 발생한다.
*	tcpNoDelay 옵션을 사용하면, 버퍼가 차기전에라도 바로 전송이 되기 때문에, 전송 속도가 빨라진다. 반대로, 작은 패킷을 여러번 보내기 때문에 전체적인 네트워크 트래픽은 증가. 기본적으로 true로 설정됨.


참고. NIO/APR 설명 
<a>http://palpit.tistory.com/645</a>
<a>https://gs.saro.me/#!m=elec&jn=535</a>
<a>http://gyrfalcon.tistory.com/entry/JAVA-NIO</a>
