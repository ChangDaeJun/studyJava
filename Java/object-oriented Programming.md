### 클래스, 객체, 인스턴스의 차이
* 클래스 : 객체 생성을 위한 청사진(blueprint)
* 객체 : 클래스의 인스턴스, 모든 인스턴스를 대표하는 포괄적 의미
* 인스턴스 : 구체적으로 구현된 실체, 메모리에 적제된 상태(?)

### 변수의 종류
* 클래스 변수 : static 선언, 모든 인스턴스가 공통된 저장공간을 공유, 클래스가 메모리에 적제 시 생성
* 인스턴스 변수 : 일반적인 선언, 각 인스턴스가 독립된 저장공간을 갖음, 인스턴스 생성시 생성
* 지역 변수 : 메서드 내 선언, 메서드 종료 시 소멸, 변수 선언문 실행 시 생성
* 기본형 매개변수 : 변수의 값만 읽을 수 있음
* 참조형 매개변수 : 값을 읽고 변경 가능

### JVM 메모리 구조
* Method Area : 클래스 데이터 저장(클래스 변수도 저장)
* Call stack : 메서드 작업에 필요한 메모리 공간, 지역변수, 매개변수 등 저장
* Heap : 프로그램 실행 중 생성되는 모든 인스턴스 저장

### 오버로딩
* 이름은 같지만, 매개변수의 개수나 타입이 다른 여러개의 메서드를 정의하는 것
* 반환타입은 오버로딩의 조건에 포함되지 않는다. 반환타입이 달라도, 매개변수가 동일하면 오버로딩 되지 않는다. 
* 가변인자는 오버로딩 시 메서드 구분에 혼동이 올 수 있다. 사용에 주의

### 가변인자(args)
* 매개변수의 개수를 동적으로 지정해줄 수 있는 기능
* 매개변수 선언 시 String... args 처럼 선언

### 생성자
* 인스턴스의 생성은 생성자가 아닌 연산자 new 이다.
* 작동 절차 : 연산자 new 는 메모리에 인스턴스 생성 -> 생성자 실행 -> 변수에 주소 저장
* 기본 생성자 : 컴파일 시 클래스에 생성자가 하나도 존재하지 않으면 컴파일러가 자동으로 기본 생성자를 추가하여 컴파일
* 생성자에서 다른 생성자를 호출 : this(a, b, c) 사용, 반드시 첫 줄에서만 호출 가능
* this : 인스턴스 자신을 가리키는 참조변수, 모든 인스턴스에는 지역변수로 숨겨져 있음.
* 생성자는 리턴값을 만들 수 없다.

### 초기화 블럭
* 클래스 초기화 블럭 : static {} 사용
* 인스턴스 초기화 블럭 : {} 사용
* 생성자보다 인스턴스 초기화 블럭이 먼저 수행
* 여러 생성자를 만들 때 코드 중복을 낮출 수 있다.

### 초기화 순서
* 클래스 변수 : 기본값 -> 명시적 초기화 -> 클래스 초기화 블럭
* 인스턴스 변수 : 기본값 -> 명시적 초기화 -> 인스턴스 초기화 블럭 -> 생성자