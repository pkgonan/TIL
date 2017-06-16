# Inheritance 
- 자바의 상속


## Type Checking
- instanceof 연산자 : 해당 참조 변수의 타입을 검사하여 참과 거짓을 리턴, 업 캐스팅 되었을 때도 동작한다.

- 사용법 : 참조변수 instanceof 타입


## Method Overriding
- 상속 관계에서 서브 클래스에서 메소드를 재정의한 경우, 업 캐스팅을 하더라도 서브클래스에서 오버라이딩한 메소드가 동작한다.
오버라이딩 된 상위 클래스의 메소드는 자동으로 은닉된다.

      public class test {
          public static void main (String[] args) throws java.lang.Exception
          {
              Parrent p = make(-1);
              System.out.println(p.a);
              System.out.println(p.get());
              Son s = (Son)p;
              System.out.println(s.a);
              System.out.println(s.get());
          }
      
          static Parrent make(int i){
              if(i>0) return new Parrent();
              else return new Son();
          }
      }
      
      class Parrent{
          int a = 5;
          int get(){
              return a;
          }
      }
      
      class Son extends Parrent{
          int a = 10;
          int get(){
              return a;
          }
      }

      // 출력 : 5 10 10 10
      // 자식 클래스를 생성하면 객체가
      // son - a = 10;
      //     - Parrent.a = 5;
      // 의 형태로 부모 클래스의 변수까지 Parrent.a 형태로 저장된다.
      
      
## super()
- 상속관계에서 상위 클래스의 생성자를 호출하는 메소드이다.

- 기본적으로 디폴트 생성자에는 super()가 은닉되어 있다.
   상속 관계에서 하위 클래스의 객체를 생성하게 되면 하위클래스의 데이터를 현재 객체에 담고, 최상위 클래스까지 super()를 호출하여 반복 작업을 한다. 최 상위 클래스에 도달하면 데이터를 현재 객체에 담고 재귀적으로 최 하위클래스로 돌아오며 객체 생성 작업을 마친다.
      
      
## this()
- 현재 클래스의 생성자를 호출하는 메소드이다.