8# 클린코더

***
## 의미있는 이름


### 클래스 이름
- 클래스 이름과 객체 이름은 명사나 명구사 가 적합
- Customer, WikiPage, Account, AddressParser 등이 좋은 예
- Manager, Procesor, Data, Info 등과 같은 단어는 피하고, 동사는 사용하지 않음


### 메서드 이름
- 메서드 이름은 동사나 명구사 가 적합 
- postPayment, deletePage, save 등이 좋은 예
- 접근자, 변경자, 조건자는 javabean 표준에 따라 값 앞에 get, set, is를 붙인다


- 생성자 중복 정의할 때는 정적 팩토리 메서드를 사용
> ```Java
> Complex fulcrumPoint = Complex.FromRealNumber(23.0);
> ```
> 위 코드가 아래 코드보다 좋다
> ```Java
> Complex fulcrumPoint = new Complex(23.0);
> ```


***
### 함수
- 모든 시스템은 특정 응용 분야 시스템을 기술할 목적으로 프로그래머가 설계한 도메인 특화 언어 DSL로 만들어진다. (참조 p.62 목록 3-7)


***
### 주석
- 나쁜 코드에 주석을 달지 마라. 새로 짜라. (참조 p.92 목록 4-8)
 > 코드에 주석을 추가하는 일반적인 이유는 코드 품질이 나쁘기 때문이다. 모듈을 짜고 보니 짜임새가 엉망이고 알아먹기 어렵다. 주석을 달지말고, 코드를 정리해야 한다!


***
### 형식 맞추기
- 변수선언. 변수는 사용하는 위치에 최대한 가까이 선언
- 인스턴스 변수. 인스턴스 변수는 클래스 맨 처음 선언
- 종속 함수. 한 함수가 다른 함수를 호출한다면 두 함수는 세로로 가까이 배치
- 개념적 유사성. 어떤 코드는 서로 끌어당긴다. 개념적인 친화도가 높기 때문이다. 친화도가 높을수록 코드를 가까이 배치한다.
- 들여쓰기 무시한기. 때로는 간단한 if 문, 짧은 while 문, 짧은 함수에서 들여쓰기 규칙을 무시하고픈 유혹이 생긴다. 이럴때마다 원점으로 돌아가 들여쓰기를 한다.
- 형식 규칙 참조, 목록 5-6


***
### 오류 처리
- Try-Catch-Finally 문부터 작성하라
- null을 반환하지 마라
- null을 전달하지 마라

```Java
  assert p1 != null : "p1 should not be null";
  assert p2 != null : "p2 should not be null";

```

깨끗한 코드는 읽기도 좋아야 하지만  안전성도 높아야 한다

- log4j 익히기 8장 경계 147~149


***
*** 단위 테스트
- TDD 법칙 세 가지
  > 1. 실패하는 단위 테스트를 작성할 때까지 실제 코드를 작성하지 않음
  > 2. 컴파일은 실패하지 않으면서 실행이 실패하는 정도로만 단위 테스트를 작성
  > 3. 현재 실패하는 테스트를 통과할 정도로만 실재 코드를 작성한다.

- 깨끗한 테스트 코드 유지 하기
- 테스트당 assert 하나 or 테스트강 개념 하나
  > - JUnit으로 테스트 코드를 짤 때는 함수마다 assert 문을 단 하나만 사용해야한다.
  > - assert 문이 단 하나인 함수는 결론이 하나라서 코드를 이해하기 쉽고 빠르다. (목록 9-7 164)
- F.I.R.S.T.
 > 깨끗한 테스트는 다음 다섯 가지 규칙을 띠른다.
 > 빠르게,Fast: 테스트는 빨라야 한다. 테스트가 느리면 자주 돌릴 엄두를 못낸다. 코드를 마음껏 정리하지도 못한다. 결국 코드 품질이 망가진다.
 > 독립적으로,Independent: 각 테스트는 서로 의전하면 안 된다. 한 테스트가 다음 테스트가 살행될 환경을 준비해서는 안 된다.  각 테스트는 독립적으로 그리고 어떤 순서로 실행해도 괜찮아야 한다. 테스트가 서로에게 의존하면 실패할때 나머지도 잇달아 실패하므로 원인을 진단하기 어려워지며 후반 테스트가 찾아내야 할 결함이 숨겨진다.
 > 반복가능하게,Repeatable: 테스트는 어떤 환경에서도 반복 가능해야 한다. 실제 환경, QA 환경, 버스를 타고 집으로 가는 길에 사용하는 (네트워크에 연결되지 않은) 노트북 환경에서도 실행할 수 있어야 한다. 테스트가 돌아가지 않는 환경이 하나라도 있다면 실패한 이유를 둘러댈 변명이 생기고, 환경이 지원되지 않기에 테스트를 수행하지 못하는 상황에 직면한다.
 > 자가검증하는,Self-Validating: 테스트는 bool값으로 결과를 내야 한다. 통과 여부를 알려고 로그 파일을 읽게 만들어서는 안 된다. 통과 여부를 보여고 텍스트 파일 두 개를 수작업으로 비교하게 만들어서도 안 된다. 테스트가 스스로 성공과 실패를 가늠하지 않는다면 판단은 주관적이 되며 지루한 수작업 평가가 필요하게 된다.
> 적시에,Timely: 테스트는 적시에 작성해야 한다. 단위 테스트는 테스트하려는 실제 코드를 구현하기 직전에 구현한다. 실제 코드를 구현한 다음에 테스트 코드를 만들면 실제 코드가 테스트하기 어렵다는 사실을 발견할지도 모른다. 어떤 코드는 테스트하기 어렵다공 판명날지 모른다. 테스트가 불가능하도록 실제 코드를 설계할지도 모른다.
- 테스트 코드는 실제 코드의 유연성, 유지보수성, 재사용성을 보존하고 강화한다. 그러므로 테스트 코드는 지속적으로 깨끗하게 관리하고, 표현력을 높이고, 간결하게 정리하자. 테스트 API를 구현해 도메인 특화 언어 DSL를 만들면 그만큼 테스트 코드를 짜기가 쉬워진다.


***
