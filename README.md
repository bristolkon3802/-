# 클린코더

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