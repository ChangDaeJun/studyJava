### 데이터베이스의 특징
* 실시간 접근성
* 지속적인 변화
* 동시 공유
* 내용에 따른 참조

### 릴레이션
* 릴레이션은 여러 도메인 간의 관계 집합이다.
* ```
  예) 사람에 대한 릴레이션은 성별, 나이, 이름, 주소지 도메인의 관계로 구성될 수 있다.
  이때 각 도메인의 집합을 A, B, C, D라고 하자.(예를 들면 나이 집합은 0 ~ 200 까지의 집합일 수 있다.)
  전체 집합의 곱 A X B X C X D을 생각할 수 있으며, 릴레이션은 전체 집합의 곱의 부분집합이다.
  릴레이션의 한 원소로는 (남, 20, 홍길동, 서울시)가 있을 수 있으며, 이를 튜플 또는 인스턴스라고 한다.
  ```
* 릴레이션의 특징
  * 속성은 단일값을 갖는다.
  * 속성은 서로 다른 이름을 갖는다.(수학적 의미에서는 필요 없지만, 사용자가 도메인의 순서를 기억할 필요 없도록 이와 같은 제한을 둠)
  * 속성의 순서는 상관없다.(위의 이유이며, 수학에서는 속성의 순서가 중요했다)
  * 한 속성의 값은 모두 같은 도메인 값을 가진다.
  * 릴레이션 내의 중복된 투플은 허용하지 않는다.
  * 투플의 순서는 상관 없다.

### 데이터베이스 키 
* 슈퍼키 : 튜플을 유일하게 식별할 수 있는 하나 이상의 속성 집합
* 후보키 : 슈퍼키 중 최소 집합
* 복합키 : 여러 속성으로 이루어진 키
* 기본키 : 여러 후보키 중 하나를 선정하여 대표로 정한 키, 값의 변동이 없으며, 문제의 소지가 없어야 한다.
* 대리키 : 마땅한 기본키가 없을 경우 가상 속성을 만들어 기본키로 삼는 경우
* 대체키 : 기본키로 선정되지 않은 후보기
* 외래키 : 다른 릴레이션의 기본키를 참조하는 속성

### 무결성 제약조건
* 데이터베이스에 저장된 데이터의 일관성과 정확성을 지키는 것
* 도메인 무결성 제약조건 : 각 튜플의 속성은 도메인이 지정한 값만 가져야 한다.
* 개체 무결성 제약조건 : 기본키는 not null이며, 유일하야 한다.
* 참조 무결성 제약조건 : 자식 릴레이션의 외래키는 부모 릴레이션의 기본키와 도메인이 일치해야 하고, 자식 릴레이션의 변경이 부모 릴레이션의 제약을 받음

### 관계대수 연산자
* 순수 관계 연산 : 셀렉션, 프로젝션, 조인, 디비전, 개명
* 일반 집합 연산 : 합집합, 차집합, 교집합, 키티전 곱
* 셀랙션 : 하나의 릴레이션을 대상으로 하는 단항 연산자, 투플의 조건을 명시하고, 조건에 맞는 투플을 반환
* 프로젝션 : 릴레이션의 속성을 추출하기 위한 단한 연산자
* 조인 : 두 릴레이션의 공통속성을 기준으로 속성값이 같은 투플을 결합하는 연산, 프로덕트 곱 이후 셀렉션 연산을 한 것과 동일
* 세타조인 : 조인에 참여하는 두 릴레이션의 속성값을 비교함. 비교 시 = 을 사용하면 동등조인이라 한다.
* 자연조인 : 동등 조인 후 동일한 속성이 두번 나타나는데, 두번째 나타난 속성을 제거해준다.
* 외부조인 : 조인한 뒤 조인에 실패한 튜플에 대해서는 비어있는 속성 값을 null로 채워서 반환한다. 왼쪽, 오른쪽, 완전 외부조인이 가능하다.
* 세미조인 : 자연조인 후 한쪽의 릴레이션 튜플만 반환
* 디비전 : 도메인의 집합이 포함관계인 두 릴레이션(A > B)에 대해 A / B 가능. 이는 A 튜플 중 B의 튜플의 속성값과 일치하는 튜플을 B을 제외하고 보여준다.