# [FRONT] AJAX

<br/>

<br/>

<br/>

## AJAX

AJAX - Asynchronous Javascript And XML 비동기식 자바스크립트와 XML이라는 뜻으로, XMLHttpRequest 객체를 활용해서 페이지 전체를 리로딩하지 않아도 되는 비동기식 통신을 할 수 있게 합니다. AJAX는 특정 기술이 아닌 기존의 여러 기술을 사용하는 새로운 접근법을 설명하는 용어입니다. 비동기식 통신을 하기 위해 적극적으로 사용되는데, 비동기식이란 병렬적 태스크 수행으로서 요청을 보낸 다음 응답을 기다리지 않고 바로 다음 작업이 수행되는 형태를 말합니다. 이는 사용자의 경험을 위해서 매우 중요한 요소입니다. 하지만 자바스크립트는 싱글 스레드이며, 실제로 작업을 병렬처리하는 것이 아니라 동시에 처리되는 것처럼 보이게 하는 동시성 모델을 구현합니다. 이 동시성을 확보하기 위해 자바스크립트에서는 event loop을 활용하는데, 요청이 들어올 때마다 해당 요청을 순차적으로 처리하는 콜 스택으로 보냅니다. 그리고 이 콜스택에 들어온 요청 중 즉시 처리하지 못하는 요청들은 자바스크립트 영역이 아닌 브라우저 영역의 web API로 보내 처리되게 합니다. web API에서 처리된 작업들은 Task queue에 순서대로 줄세워지고, event loop은 콜스택이 비는 것을 확인하다가 비워진 때에 태스크 큐의 앞에 있는 작업부터 콜스택으로 푸시합니다. 이런 일련의 동시성 모델을 통해 비동기 작업이 이루어지고 작업들이 동시에 처리되는 것처럼 보일 수 있습니다.