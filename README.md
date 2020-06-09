#Java Programing



### this()와 this는 다르다


```markdown
class ConstructExample{
   int x ;
  ConstructExample(String a){
      this(1);
      System.out.println("생성자 호출입니다");
   }
   ConstructExample(int B){
       System.out.println("A");
   }
   public void setX(int x){this.x = x;}
   public int getX(){
      return x;
   }

   public static void main(String[] args){
      ConstructExample a = new ConstructExample("H");
      int n = a.getX();
      System.out.println(n);
   }
}
```

### this()는 같은 클래스 내에서 서로 다른 생성자를 호출할 때 쓰인다.

ConstructExample(String a){생략}에서 this(1)를 사용하는 부분이 있는데 
여기서는 자기자신이 아닌 int 형을 매개변수로 받는 ConstructExample(int B){생략}을 호출하는 것 이다.



### this은 x 를 구분지어주기 위하여 사용한다.

**public void setX(int x){
this.x = x;
}**

의 매소드의 매개변수로 받은 int x를 글로버 변수 int x와 구분지어주기 위하여 사용한다.
즉 SetX(int x)의 매소드에서 **this.x는 글로벌 변수 x이다.**

### 만약 구분 지어줄 필요가 없다면 this를 사용할 이유가 있을까?
this.는 **구분을 지어주기 위한 것**이라고 설명했다.
답을 먼저 말하자면
당연히 없다.
만약 글로벌 변수가 int y라면
this.y = x가 아닌  ( this.y로 해도 오류는 발생하지 않는다. )                                    
y= x ;로 사용할 수 있다.



### 주의할점
**this()는 반드시 생성자의 첫 문장이어야 한다.**

**this()는 같은 클래스 내 다른 생성자를 호출할 때 사용된다.**

**this()는 생성자 코드에서만 호출할 수 있다.**

**- 위의 사항을 어길 시 에러가 발생한다.**
