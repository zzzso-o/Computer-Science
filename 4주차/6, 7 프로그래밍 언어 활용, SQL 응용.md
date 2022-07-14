# 프로그래밍 언어 활용, SQL 응용



## 프로그래밍 언어 활용

### 1.  다음 Java 프로그램의 실행 결과를 쓰시오.

```java
abstract class Animal{
   abstract void value();
   void key(){
     System.out.print("animal");   // 줄 안띄고 이어서 출력 python. ex) print("animal", end="")
     System.out.println("animal"); // 줄 한칸 띄고 출력 
   }
}
class Dog extends Animal{
   void value(){
     System.out.print("dog");
   }
}
class Soojebi {
   public static void main(Strings[] args) {
     Animal d = new Dog();
     d.key();
     d.value();
   }
}
```

태희 : 

```java
animaldog
```

지수 :

```java
animal
dog
```

우창 :

```java
animal
dog
```

수홍 :

```java
animaldog
```



<details> <summary>답</summary> <div markdown="1">  animaldog  </div> </details>

<details> <summary>해설</summary> <div markdown="1">  추상클래스(abstract class)는 하나 이상의 추상 메소드를 포함한 클래스를 의미합니다.  추상 메소드는 추상 메소드가 포함된 클래스를 상속받는 자식 클래스가 반드시 추상 메소드를 구현하도록 하기 위함입니다. 추상 클래스는 미완성이기 때문에 객체를 생성할 수 없습니다. 문제를 보면 new Dog()로 생성되는 것을 볼 수 있습니다. d.key()는 extends로 추상클래스 Animal의 key메소드가 실행되고, d.value()는 Dog클래스의 메소드 value가 실행됩니다. printIn이 아닌 print이므로 줄바꿈은 일어나지 않습니다. </div> </details>

[출처] [2022년 제2회 기사 실기 출제예상 문제] (6과목) 프로그래밍 활용 - 11 (수제비- IT 커뮤니티 (정보처리기사,빅데이터분석기사 등)) | 작성자 수제비쌤



### 2. 다음 자바 프로그램 결과를 쓰시오.

```java
public class Soojebi
{
    public static int isPrime(int num){
        for(int i=2;i<num;i++){
            if(num%2 == 0){
                return 0;
            }
        }
        return 1;
    }
    
	public static void main(String[] args) {
		int num=100, cnt=0;
		for(int i=2;i<num;i++){
		    cnt = cnt + isPrime(i);
		}
		
		System.out.println(cnt);
	}
}
```

우창 : 7

지수 : 49

태희 : 25 O

수홍 : Fail



<details> <summary>답</summary> <div markdown="1">  25  </div> </details>

<details> <summary>해설</summary> <div markdown="1">  static은 객체를 생성하지 않아도 존재하는 변수나 함수이고, 위에 isPrime은 함수라고 볼 수 있다. 2 이상 100 미만까지 for문이 돌면서 cnt의 값이 변한다. 함수명에서도 알 수 있듯이 소수이면 1, 아니면 0을 return한다. 2 이상 100 미만의 소수의 개수가 출력된다.  </div> </details>



[출처] [2022년 제2회 기사 실기 출제예상 문제] (6과목) 프로그래밍 활용 - 5 (수제비- IT 커뮤니티 (정보처리기사,빅데이터분석기사 등)) | 작성자 보안쌤



## SQL 응용



### 3. 다음 중 [직원] 테이블에서 부서별로 그룹을 묶었을 때 부서의 급여합계가 500 이상인 부서, 해당 부서의 급여합계를 출력하는 쿼리를 작성하시오.



[직원]

| 이름   | 부서   | 급여 |
| ------ | ------ | ---- |
| 장길산 | 영업   | 300  |
| 임꺽정 | 마케팅 | 400  |
| 조맹달 | 기획   | 200  |
| 홍길동 | 기획   | 500  |
| 고길동 | 마케팅 | 100  |



[결과]

| 부서   | 급여합계 |
| ------ | -------- |
| 마케팅 | 500      |
| 기획   | 700      |

<details> <summary>답</summary> <div markdown="1">  SELECT 부서, SUM(급여) AS 급여합계 FROM 직원 GROUP BY 부서 HAVING SUM(급여) >= 500;  </div> </details>

<details> <summary>해설</summary> <div markdown="1">  무엇을 보겠다? (SELECT 부서, SUM(급여) AS 급여합계), 어느 테이블로부터? (FROM 직원), 부서별로 그룹을 묶었을 때 (GROUP BY 부서), 부서의 급여합계가 500 이상인 (HAVING SUM(급여) >= 500;)  </div> </details>



[출처] [[2022년 제2회 기사 실기 출제예상 문제\] (7과목) SQL 응용 - 9 (수제비- IT 커뮤니티 (정보처리기사,빅데이터분석기사 등))](https://cafe.naver.com/soojebi/125511) | 작성자 [수제비쌤](https://cafe.naver.com/soojebi.cafe?iframe_url=%2Fca-fe%2Fcafes%2F29835300%2Fmembers%2FlWANQ6Kv4mT2djJ2exybfg)

