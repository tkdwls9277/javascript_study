node.js
===

## define Node

- 서버사이드 js (node자체는 웹서버가 아님. js 런타임으로 웹서버를 만들 수 있는 하나의 방법)
- features
    - 빠른속도 : 구글의 js engine인 V8 기반으로 구성된 sw system
    - 비동기 I/O 처리 : 이벤트 기반으로 개발, Non-Blocking I/O 를 지원 -> 비동기식 프로그래밍 가능
    - 단일 쓰레드와 뛰어난 확장성 : Node는 쓰레드를 한개만 사용하고 아파치와 같은 웹서버보다 훨씬 많은 요청을 처리 가능

<br>

----------------------
<br>

## what Node?

기존에는 클라이언트가 서버로의 요청에 대해 각각 새로운 쓰레드를 생성하고 그에 따라 메모리를 할당하여 사용자의 요청을 처리했던 반면, 노드에서는 각 연결이 하나의 이벤트로서 노드 엔진에서 처리됩니다. 

노드는 일반적으로 어떤 일을 끝마치고 나면 Callback이 실행됩니다. 오직 한번에 한개의 콜백만 실행됩니다.
그 콜백의 수행이 종료되기 전까지는 다른 콜백은 계속 그 라인에 기다려야합니다. 작업은 병렬로 실행되지만 종료되는것은 한개씩 종료됩니다.

"여러사람에게 동시에 일을 주고 한번에 한명에게서만 결과 보고를 받는 개념으로 이해 할 수 있을 것 같습니다." 

(+그러므로 어느 콜백이 먼저 실행될지는 보장할 수 없습니다.)

=> JavaScript single-threaded : 같은 데이터 스트럭쳐에 동시에 접근될 거에 대해서 걱정할 필요가 없습니다.

<br>

-----------------------
<br>

## why Node?

- 효율이 높습니다. 웹어플리케이션에서는 주요 응답시간 비용 = 모든 데이터 쿼리 수행에 걸리는 시간의 합

  노드를 사용하면 모든 쿼리를 한번에 실행 가능 => 가장 느린 쿼리를 실행하는 소모시간이 감소됨

- 자바스크립트를 사용합니다. 백엔드단과 브라우저단에서 코드를 공유할 수 있다는 장점이 있습니다.
    
  (같은 조직내의 공통된 언어를 사용함으로써 공유의 용이성을 높일 수 있습니다.)

- 속도가 높다. V8은 인터프리터 언어중 가장 빠른속도를 자랑합니다.

  더불어 노드의 I/O가 정말 가볍기 때문에 시스템의 최대한 빠른 I/O 성능을 이끌어낼 수 있습니다.

<br>

-----------------------
<br>

### Node.js를 쓰기 적합한 곳

- 낮은 응답시간과 높은 동시성이 중요한 곳

- 데이터의 실시간 처리가 필요한 애플리케이션(알림, 실시간 대화 등)

- 사용자의 입력과 출력이 잦은 애플리케이션

- 단일 페이지 기반의 애플리케이션

### Node.js를 쓰기 적합하지 않은 곳

- 데이터 분석, 데이터 엔지니어링 등 데이터 사이언스분야 같이 복잡한 데이터를 다뤄야 하는 곳에는 적합하지 않음

  (하드코어한 처리 목적으로는 적합하지 않음)

- 덩치가 큰 프로젝트(사용가능한 라이브러리와 자원들을 고려해야합니다.)

<br>
<br>

참고 : >https://programmingsummaries.tistory.com/328