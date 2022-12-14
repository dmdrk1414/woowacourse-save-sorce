## :rocket:1주차 온보드 과제입니다. 

이번과제는 프리코스의 1주차입니다. 1주차지만 어렵네요😂😂



## 🎈문제를 풀면서 생각한 다시 공부를 해야하는 것들을 정리했어요 😁😁

#### 1. map key 값으로 정렬하기

1. ```java
   public static void main(String[] args) {
   		// Map 선언
   		Map<Integer, String> testMap = new HashMap<Integer, String>();
   
   		// Map에 데이터 추가
   		testMap.put( 1, "apple");
   		testMap.put( 4, "pineapple");
   		testMap.put( 2, "orange");
   		testMap.put( 5, "strawberry");
   		testMap.put( 3, "melon");
   
   		// 키로 정렬
   		Object[] mapkey = testMap.keySet().toArray();
   		Arrays.sort(mapkey);
   
   		// 결과 출력
   		for (Integer nKey : testMap.keySet())
   		{
   			System.out.println(testMap.get(nKey));
   		}
   	}
   ```

   

#### 2. entry 다시 보기

2. ![image-20221101082906643](C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221101082906643.png)

#### 3. iterator 사용

1. **iterator 메서드**

   - ![image-20221101082143083](C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221101082143083.png)

2. ListIterator

   - ![image-20221101082347731](C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221101082347731.png)

3. ```java
   //  1. map의 iterator 사용
       private static void printEntrySet(Map map) {
           Iterator it = map.entrySet().iterator();
           while (it.hasNext()) {
               System.out.println(it.next());
           }
       }
   
   //  2. list의 iterator 사용     Collection을 오버라이딩을 하여도 괜찮다.
       public static   void printIterator(Collection collection) {
           Iterator it = collection.iterator();
           while (it.hasNext()) {
               System.out.println(it.next());
   
   //             it.next의 리턴값은 Object이다.
   //            Object obj = it.next();
   //            System.out.println(obj);
           }
       }
   
   
   
   //  3. list의 ListIterator 양방향 검색
       public static   void printListIterator(List list){
           ListIterator it = list.listIterator();
           while (it.hasNext()) {
               System.out.println("it.next() = " + it.next());
           }
           System.out.println( );
   
           // 역순 출력
           while (it.hasPrevious()) {
               System.out.println("it.previous() = " + it.previous());
           }
           System.out.println( );
       }
   
   // 4. iterator의 remove 메서드; => [3, 4, 5, 6, 7, 8, 9, 10]
      public static   void removeIterator(Collection collection) {
           Iterator it = collection.iterator();
           it.next();
           it.remove();
           it.next();
           it.remove();
       }
   ```

#### 4. List set map 다시 공부

#### 5. map 순환하는 법 다시 보기

- map을 초기화 하는 방법

- ```java
         Map <String, Integer> map = new HashMap<>(){
              {
                  put("하나", 1);
                  put("둘", 2);
                  put("삼", 3);
              }
          };
          map.put("사", 4);
          System.out.println("map.toString() = " + map.toString());
        
   // map.of를 이용한 초기화는 변경 불가능 ImmutableCollections.java:71)
          Map <String, Integer> map2 = Map.of(
                  "하나", 1,
                  "둘", 2,
                  "삼", 3
          );
          // map.of를 이용한 초기화는 변경 불가능 ImmutableCollections.java:71)
          map2.put("사", 4);
          System.out.println(map2.toString());
  ```

#### 6. 정규표현식 다시 확인

#### 7. stream 공부

#### 8. 문자열 equals 다시 보기

- Object - equals
  - equals메서드는 **객체의 주소를 비교를 합니다.** 
  - **인스턴스의 멤버 변수의 값을** 비교하기 위해서는 **오버라이딩을** 해야합니다.
- 그외 - equals
  - 모든 것은 Object의 equals를 오버라이딩 한것입니다. 값을 비교한다고 생각하면 되는 것같아요.
- hashcode
  - Object
    - 주소기반으로 해시코드 반환(암호) 무조건 다르다 하지만 64비트 컴퓨터는 같을수 있다
  - 그외
    - 값으로 해시코드를 만들었다  같은 값의 String 2개를 생성하고 해시코드를 비교하면 같다.

#### 9. comparator class 다시보기.

#### 10. 예외 처리

- <img src="C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221102131300569.png" alt="image-20221102131300569" style="zoom:80%;" />
- 예외 처리 방법 Problem_1
  - ![image-20221102132054363](C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221102132054363.png)
- 예외 처리 방법 Problem_2
  - <img src="C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221102132929362.png" alt="image-20221102132929362" style="zoom:80%;" />
- 예외 처리 방법 Problem_3
  - <img src="C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221102135146090.png" alt="image-20221102135146090" style="zoom:80%;" />
- 예외 처리 방법 Problem_4
  - <img src="C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221102135404800.png" alt="image-20221102135404800" style="zoom:80%;" />
- 예외 처리 방법 Problem_5
  - ![image-20221102140126377](C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221102140126377.png)

- 예외 처리 방법 Problem_6
  - <img src="C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221102140716529.png" alt="image-20221102140716529" style="zoom:80%;" />

- 예외 처리 방법 Problem_7

  - 7_1

  - ![image-20221102141335570](C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221102141335570.png)

  - 7_2
  - ![image-20221102141613568](C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221102141613568.png)

  - 7_3
  - ![image-20221102141754410](C:\Users\Park-Seung-Chan\AppData\Roaming\Typora\typora-user-images\image-20221102141754410.png)

#### 11. 

## 🎈다시 자바의 정석 공부를 하면서 정리를 해야 겠습니다. ㅎㅎ😋 



## 🎈문제를 풀면서 느낀점 

```
문제1번
left와 right가 연달아 있는가를 가장 늦게 알아 차렸습니다. 어떤 사물을 볼때 생각을 해야할점이 
많다는 것을 느껴서 재미있었습니다.ㅎㅎ
```



```
문제2번
제가 월래 싫어하던 반복문자 제거입니다. 공부를 했다는 느낌이 나는 문제였습니다.
반복이 나오면 반복 이전의 문자와 반복 이후의 문자를 subString을 한후 저장을 하고
StringBuffer 에 저장하는 이런 과정을 생각할수 있다는 것이 재미있었습니다. 맛있는 문제 였던것 같습니다.
```



```
문제3번
3.6.9 게임을 할때 33은 두번을 더해야한다는 점을 생각하고 
어떤 문제가 나왔을때 게임이 진행되는 과정을 머릿속에 정돈을 해도 좋을꺼 같다는 생각을 하였습니다.
```



```
문제4번
역시 생각이 없는 if문 보다는 규칙을 찾아서 접근하는 것이 재미 있었습니다.
학교에서 반복대치 분할 정복을 배웠는데 도움이 되었습니다.
```



```
문제5번
학교에서 많이 했던 지폐나누기를 메서드와 ArrayList로 이용해 풀어보았는데
list와 2차 배열에 대한 생각을 많이 할수있어서 재미있었습니다.
```



```
문제 6번
리스트 안 리스트를 사용할일이 별로 없었는데 
연습할수 있어서 감사했습니다.
```



```
문제 7번
분할을 할 자신이 없습니다.
기능을 하나하나 쪼개서 구현을 했습니다. 
map을 이용한적이 별로 없었는데 연습을 해야한다는 생각을 했습니다. 

더이상의 생각이 안들어 다른사람들의 깃을 확인했습니다. 
api의 함수를 이용해서 푸는 것이 너무 효율적이라는 점을 느겼습니다.
```



---

##  :heavy_check_mark: 1번 문제

### 🚀 기능 요구 사항

포비와 크롱이 페이지 번호가 1부터 시작되는 400 페이지의 책을 주웠다. 책을 살펴보니 왼쪽 페이지는 홀수, 오른쪽 페이지는 짝수 번호이고 모든 페이지에는 번호가 적혀있었다. 책이 마음에 든 포비와 크롱은 페이지 번호 게임을 통해 게임에서 이긴 사람이 책을 갖기로 한다. 페이지 번호 게임의 규칙은 아래와 같다.

1. 책을 임의로 펼친다.
2. 왼쪽 페이지 번호의 각 자리 숫자를 모두 더하거나, 모두 곱해 가장 큰 수를 구한다.
3. 오른쪽 페이지 번호의 각 자리 숫자를 모두 더하거나, 모두 곱해 가장 큰 수를 구한다.
4. 2~3 과정에서 가장 큰 수를 본인의 점수로 한다.
5. 점수를 비교해 가장 높은 사람이 게임의 승자가 된다.
6. 시작 면이나 마지막 면이 나오도록 책을 펼치지 않는다.

포비와 크롱이 펼친 페이지가 들어있는 리스트/배열 pobi와 crong이 주어질 때, 포비가 이긴다면 1, 크롱이 이긴다면 2, 무승부는 0, 예외사항은 -1로 return 하도록 solution 메서드를 완성하라.

#### 제한사항

- pobi와 crong의 길이는 2이다.
- pobi와 crong에는 [왼쪽 페이지 번호, 오른쪽 페이지 번호]가 순서대로 들어있다.

#### 실행 결과 예시

| pobi       | crong      | result |
| ---------- | ---------- | ------ |
| [97, 98]   | [197, 198] | 0      |
| [131, 132] | [211, 212] | 1      |
| [99, 102]  | [211, 212] | -1     |

##  :heavy_check_mark: 2번 문제

### 🚀 기능 요구 사항

암호문을 좋아하는 괴짜 개발자 브라운이 이번에는 중복 문자를 이용한 새로운 암호를 만들었다. 예를 들어 "browoanoommnaon"이라는 암호문은 다음과 같은 순서로 해독할 수 있다.

1. "browoanoommnaon"
2. "browoannaon"
3. "browoaaon"
4. "browoon"
5. "brown"

임의의 문자열 cryptogram이 매개변수로 주어질 때, 연속하는 중복 문자들을 삭제한 결과를 return 하도록 solution 메서드를 완성하라.

### 제한사항

- cryptogram은 길이가 1 이상 1000 이하인 문자열이다.
- cryptogram은 알파벳 소문자로만 이루어져 있다.

### 실행 결과 예시

| cryptogram        | result  |
| ----------------- | ------- |
| "browoanoommnaon" | "brown" |
| "zyelleyz"        | ""      |

##  :heavy_check_mark: 3번 문제

### 🚀 기능 요구 사항

배달이가 좋아하는 369게임을 하고자 한다. 놀이법은 1부터 숫자를 하나씩 대면서, 3, 6, 9가 들어가는 숫자는 숫자를 말하는 대신 3, 6, 9의 개수만큼 손뼉을 쳐야 한다.

숫자 number가 매개변수로 주어질 때, 1부터 number까지 손뼉을 몇 번 쳐야 하는지 횟수를 return 하도록 solution 메서드를 완성하라.

### 제한사항

- number는 1 이상 10,000 이하인 자연수이다.

### 실행 결과 예시

| number | result |
| ------ | ------ |
| 13     | 4      |
| 33     | 14     |

##  :heavy_check_mark: 4번 문제

### 🚀 기능 요구 사항

어느 연못에 엄마 말씀을 좀처럼 듣지 않는 청개구리가 살고 있었다. 청개구리는 엄마가 하는 말은 무엇이든 반대로 말하였다.

엄마 말씀 word가 매개변수로 주어질 때, 아래 청개구리 사전을 참고해 반대로 변환하여 return 하도록 solution 메서드를 완성하라.

| A    | B    | C    | D    | E    | F    | G    | H    | I    | J    | K    | L    | M    | N    | O    | P    | Q    | R    | S    | T    | U    | V    | W    | X    | Y    | Z    |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| Z    | Y    | X    | W    | V    | U    | T    | S    | R    | Q    | P    | O    | N    | M    | L    | K    | J    | I    | H    | G    | F    | E    | D    | C    | B    | A    |

### 제한사항

- word는 길이가 1 이상 1,000 이하인 문자열이다.
- 알파벳 외의 문자는 변환하지 않는다.
- 알파벳 대문자는 알파벳 대문자로, 알파벳 소문자는 알파벳 소문자로 변환한다.

### 실행 결과 예시

| word         | result       |
| ------------ | ------------ |
| "I love you" | "R olev blf" |

##  :heavy_check_mark: 5번 문제

### 🚀 기능 요구 사항

계좌에 들어있는 돈 일부를 은행에서 출금하고자 한다. 돈 담을 지갑이 최대한 가볍도록 큰 금액의 화폐 위주로 받는다.

돈의 액수 money가 매개변수로 주어질 때, 오만 원권, 만 원권, 오천 원권, 천 원권, 오백원 동전, 백원 동전, 오십원 동전, 십원 동전, 일원 동전 각 몇 개로 변환되는지 금액이 큰 순서대로 리스트/배열에 담아 return 하도록 solution 메서드를 완성하라.

### 제한사항

- money는 1 이상 1,000,000 이하인 자연수이다.

### 실행 결과 예시

| money | result                      |
| ----- | --------------------------- |
| 50237 | [1, 0, 0, 0, 0, 2, 0, 3, 7] |
| 15000 | [0, 1, 1, 0, 0, 0, 0, 0, 0] |

##  :heavy_check_mark: 6번 문제

### 🚀 기능 요구 사항

우아한테크코스에서는 교육생(이하 크루) 간 소통 시 닉네임을 사용한다. 간혹 비슷한 닉네임을 정하는 경우가 있는데, 이러할 경우 소통할 때 혼란을 불러일으킬 수 있다.

혼란을 막기 위해 크루들의 닉네임 중 **같은 글자가 연속적으로 포함** 될 경우 해당 닉네임 사용을 제한하려 한다. 이를 위해 같은 글자가 연속적으로 포함되는 닉네임을 신청한 크루들에게 알려주는 시스템을 만들려고 한다.

신청받은 닉네임 중 **같은 글자가 연속적으로 포함** 되는 닉네임을 작성한 지원자의 이메일 목록을 return 하도록 solution 메서드를 완성하라.

### 제한사항

- 두 글자 이상의 문자가 연속적으로 순서에 맞추어 포함되어 있는 경우 중복으로 간주한다.
- 크루는 1명 이상 10,000명 이하이다.
- 이메일은 이메일 형식에 부합하며, 전체 길이는 11자 이상 20자 미만이다.
- 신청할 수 있는 이메일은 `email.com` 도메인으로만 제한한다.
- 닉네임은 한글만 가능하고 전체 길이는 1자 이상 20자 미만이다.
- result는 이메일에 해당하는 부분의 문자열을 오름차순으로 정렬하고 중복은 제거한다.

### 실행 결과 예시

| forms                                                        | result                                                       |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [ ["[jm@email.com](mailto:jm@email.com)", "제이엠"], ["[jason@email.com](mailto:jason@email.com)", "제이슨"], ["[woniee@email.com](mailto:woniee@email.com)", "워니"], ["[mj@email.com](mailto:mj@email.com)", "엠제이"], ["[nowm@email.com](mailto:nowm@email.com)", "이제엠"] ] | ["[jason@email.com](mailto:jason@email.com)", "[jm@email.com](mailto:jm@email.com)", "[mj@email.com](mailto:mj@email.com)"] |

##  :heavy_check_mark: 7번 문제

### 🚀 기능 요구 사항

레벨 2의 팀 프로젝트 미션으로 SNS(Social Networking Service)를 만들고자 하는 팀이 있다. 팀에 속한 크루 중 평소 알고리즘에 관심이 많은 미스터코는 친구 추천 알고리즘을 구현하고자 아래와 같은 규칙을 세웠다.

- 사용자와 함께 아는 친구의 수 = 10점
- 사용자의 타임 라인에 방문한 횟수 = 1점

사용자 아이디 user와 친구 관계 정보 friends, 사용자 타임 라인 방문 기록 visitors가 매개변수로 주어질 때, 미스터코의 친구 추천 규칙에 따라 점수가 가장 높은 순으로 정렬하여 최대 5명을 return 하도록 solution 메서드를 완성하라. 이때 추천 점수가 0점인 경우 추천하지 않으며, 추천 점수가 같은 경우는 이름순으로 정렬한다.

### 제한사항

- user는 길이가 1 이상 30 이하인 문자열이다.
- 사용자 아이디는 알파벳 소문자로만 이루어져 있다.
- 
- friends는 길이가 1 이상 10,000 이하인 리스트/배열이다.
- friends의 각 원소는 길이가 2인 리스트/배열로 [아이디 A, 아이디 B] 순으로 들어있다.
  - A와 B는 친구라는 의미이다.
  - 아이디는 길이가 1 이상 30 이하인 문자열이다.
  - 
- visitors는 길이가 0 이상 10,000 이하인 리스트/배열이다.
- 사용자 아이디는 알파벳 소문자로만 이루어져 있다.
- 동일한 친구 관계가 중복해서 주어지지 않는다.
- 추천할 친구가 없는 경우는 주어지지 않는다.

### 실행 결과 예시

| user   | friends                                                      | visitors                                      | result                    |
| ------ | ------------------------------------------------------------ | --------------------------------------------- | ------------------------- |
| "mrko" | [ ["donut", "andole"], ["donut", "jun"], ["donut", "mrko"], ["shakevan", "andole"], ["shakevan", "jun"], ["shakevan", "mrko"] ] | ["bedi", "bedi", "donut", "bedi", "shakevan"] | ["andole", "jun", "bedi"] |



7번 참고 

Java - 2차원 리스트 평탄화 (flatten)

https://codechacha.com/ko/java-flatten-list-of-lists/#3-stream%EA%B3%BC-reduce%EB%A1%9C-2%EC%B0%A8%EC%9B%90-%EB%A6%AC%EC%8A%A4%ED%8A%B8-%ED%8F%89%ED%83%84%ED%99%94

[[JAVA\] 자바 배열 ArrayList 중복제거 모든방법](https://lnsideout.tistory.com/entry/JAVA-자바-배열-ArrayList-중복제거-모든방법)
