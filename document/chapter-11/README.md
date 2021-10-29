# API 리팩터링 

모듈과 함수는 소프트웨어를 구성하는 블록이고 API 는 이 블록들을 서로 연결시켜주는 요소다.

그러므로 API 를 이해하기 쉽고 사용하기 쉽게 만드는 일은 중요하다.

좋은 API 는 데이터를 갱신하는 함수와 그저 조회하는 함수를 명확히 구별한다.

두 기능이 섞여 있다면 __질의 함수와 변경 함수 분리하기 (11.1 절)__ 을 적용하자.

값 하나 때문에 여러 개로 나뉜 함수들은 __함수 매개변수화하기 (11.2 절)__ 을 적용해 하나로 합칠 수 있다.

한편 어떤 매개변수는 그저 함수의 동작 모드를 전환하는 용도로 쓰이는데 이 경우에는 __플래그 인수 제거하기 (11.3 절)__ 을 적용하면 좋다.

데이터 구조가 함수 사이를 건너다니면서 분해되는 경우는 __객체 통째로 넘기기 (11.4 절)__ 을 적용해 하나로 유지하면 깔끔하다.

무언가를 매개변수로 건네 피호출 함수가 판단할지 아니면 호출 함수가 직접 정할지에 관해서는 진리가 없으므로 상황에 맞게 __매개변수를 질의 함수로 바꾸기 (11.5 절)__ 이나 __질의 함수를 매개변수로 바꾸기 (11.6 절)__ 을 적용하자.

클래스는 모듈이고 모듈이 불변으로 바뀌길 원한다면 기회가 될때 __세터 제거하기 (11.7 절)__ 을 적용하자.

한편 호출자에 새로운 객체를 만들어 반환하려 할 때 일반적인 생성자의 능력만으로 부족하다면 __생성자를 팩토리 함수로 바꾸기 (11.8 절)__ 을 적용하자.

마지막 두 리팩토링은 수 많은 데이터를 받는 복잡한 함수를 잘게 쪼개는 문제를 다룬다.

__함수를 명령으로 바꾸기 (11.9 절)__ 을 적용하면 이런 함수를 객체로 변환할 수 있는데 그러면 해당 함수 본문에서 함수 추출하기를 적용하기 편해진다.

나중에 이 함수를 단순화 해서 명령 객체가 더 이상 필요 없어진다면 __명령을 함수로 바꾸기 (11.10 절)__ 을 적용해 함수로 되돌리자. 
