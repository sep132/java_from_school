# 4월 20일 객체지향 프로그래밍 실기, 필기 (해석)
---
## 주석에다가 해석을 달았고 그 밑에 상세한 설명을 덧붙였다

```
  interface B {                  // 인터페이스 B 선언
    int NUM = 10;             // 상수 NUM 선언 (자동으로 public static final)
}

class A implements B {        // 클래스 A가 인터페이스 B를 구현
    int NUM = 20;             // A 클래스 내부의 인스턴스 변수 NUM (B의 NUM과 별개)

    void print() {            // print 메서드 정의
        System.out.print(NUM + " ");    // A 클래스의 NUM 출력 (자기 자신의 변수 → 20)
        System.out.print(B.NUM + " ");  // 인터페이스 B의 NUM 출력 → 10
    }
}

public class Main {           // 메인 클래스
    public static void main(String[] args) {  // 프로그램 시작점
        A a = new A();       // A 객체 생성

        System.out.print(a.NUM + " "); // a 객체의 NUM 출력 → 20 (A의 변수)
        a.print();                    // print 메서드 호출 → "20 10" 출력
    }
}
```
B.NUM = 인터페이스 상수
A.NUM = 객체 변수
