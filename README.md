# 2023136075 오현우 - TIL 리포지토리

## To-Do List:
### Week 1
- Hello World Flutter 실행 ✅
### Week 2
- Dart를 사용하여 구구단 만들고 실행하기 ✅
- Dart를 사용하여 정사각형 별사탕 입력 프로그램 만들고 실행하기 ✅
- Dart를 사용하여 날짜를 입력하면 요일 출력 프로그램 만들고 실행하기 ✅
### Week 3
- 과제 없음. 다만 Dart 언어의 기본 중 고급 기능을 많이 배움. ✅
### Week 4
- 장비 문제로 수업 사실상 취소. 단, 원래 이 때 Flutter의 기본 클래스들에 대해 배울 예정이었음.
- StatelessWidget, MaterialApp, StatefulWidget UI 클래스
- 상태 변경과 State 클래스, Scaffold와 AppBar 클래
- 계획: 4주차 과제 완료할 것 - 현재 시각을 표시하는 앱 (1초 갱신)을 상단 앱바 타이틀 중앙에 표시하여 코드를 올리기
### Week 5
- 화면 배치에 쓰거나 위치, 정렬, 크기 변경, 그리고 버튼 계열과 화면 표시용에 사용하는 기본적인 위젯들에 대해 알고 실습함.
- 과제: 다음과 같은 화면 만들기 (유사하면 됨)
![image](https://github.com/user-attachments/assets/1ca6baf4-8a63-4083-8534-a01e999be2fb)
- 계산기를 화면만 만들기 (똑같을 필요 없음)
![image](https://github.com/user-attachments/assets/7c736fd0-0046-4f9b-9076-6dbd89678d6a)


## Today I Learned:
### 📖 Week 1 - 오리엔테이션 ✏️
Hello World 업로드 완료

### 📖 Week 2 - Dart 언어의 정의 I ✏️
- Google에서 설계하여 만든 JavaScript와 유사하지만 다른 "정적 언어", 유사한 언어로 JS, Java와 C#가 있음.
- JS의 동적 언어의 단점인 성능과 일관성의 문제를 보완하기 위해서 Google이 설계함.
- 기본 문법으로 주석, 문장, 변수 (int 정수, double 실수, String 문자열, bool 참/거짓), 상수 (final, const), 연산자가 있음. 주석문은 //, /** **/, ///이 있음.
- 변수 타입을 추론할 수 있으면 var로 변수 선언 가능
- 익명 함수와 람다식 함수 기본도 포함됨.
- 선택 매개변수 형태의 함수는 void 이름() 의 소괄호 내부에 중괄호 {}를 넣고, 뒤에 {} 삽입
- 예시: void something({String name, int age}) {}
- if else, 삼항 연산자, switch case, for를 사용하여 분기와 반복이 가능하며, 이는 C 계열과 유사
- 특히 삼항 연산자의 예시로 var 조건 ? '참의 결과' : '거짓의 결과'; 가 있음.

### 📖 Week 3 - Dart 언어의 정의 II ✏️
- 객체 지향이란: 현실 세계에서 우리가 바라보는 사물의 쓰임새가 각각 고유한 것처럼,
  프로그래밍에서도 목적에 따라 쓰임새를 각각 고유하게 정의한 것이 객체 (Object); 객체와 객체의 상호작용으로 프로그램이 동작하게 하는 것이 객체 지향 프로그래밍 (Object-Oriented Programming; OOP)
  고유한 쓰임새를 상태 (값 / 필드)와 행위 (기능 / 메서드)로 구성된 단위이며, 생성 전 형태를 클래스 (Class), 하나의 객체를 인스턴스 (Instance)라고 한다.
- 클래스: 객체의 설계도를 클래스라 하며, 그 설계도에 의해 만들어진 형태를 객체라고 한다. 객체는 또한 인스턴스라고 불린다.
  예: 자동자 설계도 'Car': 클래스 (인스턴스) / 문 4개, 바퀴 4개, 기타 부품들: 프로퍼티 / 주행하기, 멈추기 등 기능: 메서드 
- 접근 지정자: 이름 앞에 '_'를 붙이면 외부에서 접근할 수 없음 (Java의 Private). 없을 때 외부에서 접근 가능 (Java의 Public)
- 생성자 (Constructor): 객체가 생성될 때 자동으로 실행되어 초기값을 설정하거나 준비 작업을 수행한다.
  대표적으로 init나 this가 있으며, 또한 매개변수를 설정하거나 하지 않을 수도 있다. (+메소드 오버라이딩)
- 게터 (Getter), 세터 (Setter): get/게터는 필드 (멤버 변수)의 값을 가져오는 메소드고, set/세터는 필드의 값을 설정(변경)하는 메소드이다.
  둘 다 접근 지정자가 제한될 때 (여기서는 _를 쓰지만 자바에서는 private) 유용하게 쓰인다.
- 상속 (Inheritance): 부모가 자식에게 재산을 물려주듯이 부모 클래스의 상태와 행위, 즉 고유함을 자식 클래스에게 물려주는 것이다.
  클래스에서는 extends를 사용하고, 인터페이스에서는 implements를 사용한다.
  상속하지 않고 다른 클래스의 기능을 가져오거나 오버라이드를 하려면 with를 사용한다.
- 추상 클래스 (Abstract): 구현하지 않고 선언만 하고, 자식 클래스에서 모든 기능을 구현하는 클래스이다.
- 열거 타입 (enum): 상수를 정의하는 특수한 형태의 클래스이다.
- 컬렉션 (Collection): 배열의 역할로, List (대괄호), Map ('중괄호 : 키값'), Set (중괄호)이 있다.
    - List는 순서가 있는 연속된 자료를 표현할 때 사용한다.
    - Map은 키와 값으로 쌍 지어진 사전 형태 (Python: 딕셔너리)의 자료 구조를 표현할 때 사용한다.
    - Set은 중복되지 않는 집합을 표현할 때 사용한다.

### 📖 Week 4 - 프로젝트 구조와 웹 구조 ✏️
- 핫 리로드 (Hot Reload) 자동반영은 실행 중 Ctrl+S 저장으로 자동 반영 가능
- 위젯에서 위젯으로 값 전달은 생성자를 사용함
- State 클래스를 이용해 상태를 변경하고 변경된 상태에 따라 UI 화면을 변경함
- _incrementCounter()에 의해 setState()가 호출됨
- setState() 호출됨에 따라 Scaffold 영역이 갱신
- MyApp >> MaterialApp >> Scaffold >> appBar, body
### 📖 Week 5 - 기본 위젯 ✏️
