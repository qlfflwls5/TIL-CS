# [웹] Django_MTV&ORM&Serializer

<br/>

<br/>

<br/>

## Django

+ 웹 프레임워크
  + 웹 페이지를 개발하는 과정에서 겪는 어려움을 줄이는 것이 주 목적으로 통상 데이터 베이스 연동, 템플릿 형태의 표준, 세션 관리, 코드 재사용 등의 기능을 포함하고 있는 어플리케이션 프레임워크의 일종. 프로그래밍에서 미리 규격화된 표준 구조를 구현하는 클래스와 라이브러리의 모임이다.

+ Django는 MTV 디자인 패턴으로 이루어진 Web Framework이다 . 

  + M

      Model

      MVC 디자인 패턴의 M과 매칭된다.

      데이터 관리(DB)의 역할을 한다.

      데이터의 구조를 정의하고 데이터베이스 기록을 관리

  + T

      Template

      MVC 디자인 패턴의 V와 매칭된다.

      사용자의 눈에 보여지는 부분을 표현하는 역할을 한다.

      내용을 보여주고 레이아웃 등을 결정

  + V

      View

      MVC 디자인 패턴의 C와 매칭된다.

      중간 관리자의 역할로, 요청과 응답을 중간에서 받고 전달한다.

      요청에 맞는 함수를 호출하여 처리하고 응답을 반환

      Model을 통해 요청에 알맞는 데이터를 가져와서 템플릿에 보여줄 수도 있음

<br/>

<br/>

<br/>

## ORM

 SQL 구문 대신 객체지향 프로그래밍 언어를 사용하여 호환되지 않는 유형의 시스템 간에 데이터를 변환하는 프로그래밍 기술로, 객체와 관계를 매핑하는 기술이다. 프로그래밍 언어에서 사용할 수 있는 가상 객체 데이터베이스를 만들어 사용한다. 작성한 ORM문을 ORM이 SQL문으로 읽어 DB에 전달해주고 그 역의 기능도 한다. SQL문을 잘 알지 못하더라도 이 ORM을 통해 DB조작이 가능하다는 장점이 있지만, 당연하게도 SQL문을 직접 작성하는 것만큼 완전한 서비스를 구현하기는 어렵다는 단점이 있다. 

<br/>

<br/>

<br/>

## Serializer

시리얼라이저는 ‘직렬화’를 해주는 도구로, 데이터 구조나 객체 상태를 동일하거나 다른 컴퓨터 환경에 저장하고 나중에 재구성할 수 있는 포맷으로 변환시켜준다. django rest framework의 시리얼라이저는 데이터를 json 또는 xml 등의 유형으로 쉽게 변환할 수 있는 python의 데이터 타입으로 만들어준다.

