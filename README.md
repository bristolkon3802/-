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
    2. 컴파일은 실패하지 않으면서 실행이 실패하는 정도로만 단위 테스트를 작성
    3. 현재 실패하는 테스트를 통과할 정도로만 실재 코드를 작성한다.