클래스 멤버 필드 종류 : 인스턴스 변수(멤버 변수), 멤버 상수 필드(final), 클래스 필드(전역변수, static)

새로운 객체 인스턴스를 생성할 때 기존 스택 메모리에서는 4byte(혹은 8byte, 참조 변수의 크기)에 새로운 인스턴스의 위치를 저장하고,
새로운 인스턴스는 힙의 공간에 생성한다.

<h1>배열</h1>
배열은 참조 자료형, 객체 취급, 원시형 레퍼런스 데이터 형 모두 가능
int[] arr, int arr[], int []arr 가능.