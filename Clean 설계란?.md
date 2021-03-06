# Clean 설계란?

켄트 벡에 따르면 다음 네가지 규칙을 따르기만 하면 우수한 설계가 나온다고 한다.

## 1. 모든 테스트를 실행한다

의도한대로 돌아가는 시스템이어야하기 때문에,

테스트를 철저히 거쳐야 함.

- 모든 테스트 케이스를 항상 통과하는 시스템은 ‘테스트가 가능한 시스템’이라는 뜻.

테스트가 가능한 시스템을 만들려면?

- SRP를 준수 & 낮은 결합도 필요 (by DI, 인터페이스, 추상화)

테스트 케이스가 많을수록 쉽게 테스트 코드 작성할 수 있음

## 2. 중복을 없앤다

리팩토링을 해나가자.

새로 추가한 코드가 있다면, 정리하면서(=응집도 높이고, 결합도 낮추고, 관심사 분리, 중복 제거, 프로그래머의 의도를 표현 등..) SW 품질 높이자

한 예로, Template method 패턴.

## 3. 프로그래머 의도를 표현한다

코드는 개발자의 의도를 분명히 표현해야 한다

개발자가 명백한 코드를 짤수록 타인도 그 코드를 이해하기 쉬워진다

- 결국 유지보수 비용 & 결함이 줄어든다

의도를 어떻게 분명히 표현할 수 있을까?

- 좋은 이름을 선택하고,
- 함수와 클래스 크기를 가능한 줄인다
- 표준 명칭(command / visitor / invoice / fetch 등)을 사용하고
- 단위 테스트 케이스를 꼼꼼히 작성하자

## 4. 클래스와 메서드 수를 최소로 줄인다

단, 무의미한 클래스와 메서드를 생성하지 말자.

클래스마다 무조건 인터페이스를 생성하진 말자.

클래스와 함수의 수를 줄이는 작업도 중요하지만 위의 세 가지 작업이 더 우선순위다!!