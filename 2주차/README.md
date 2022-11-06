# 낙서장

```
 // 스트라이크 3 , 볼 0
 123
 
 // 스트라이크 2 , 볼 0
 124, 143, 423
 
 // 스트라이크 1 , 볼 2
 132, 321, 213
 
 // 스트라이크 1 , 볼 1
 182, 134, 521, 324, 813, 283
 
 // 스트라이크 1 , 볼 0
184, 826, 483

 // 스트라이크 0 , 볼 1
416, 651, 247, 562, 357, 635

// 스트라이크 0 , 볼 2
712, 218, 251, 238, 732, 352, 314, 381, 431

// 스트라이크 0 , 볼 3
312, 231

 // 스트라이크 0 , 볼 0
798, 486, 589, 497, 465, 564, 464, 564, 654, 899, 789
```

```
입력 : "123", "234", "345", "456", "678", "789"
값 : true

입력 : "112", "121", "211", "111", "556", "565", "655", "555"
값 : false
```

```
   List<String> hints = new ArrayList<>(
            List.of(
                "3스트라이크",
                "2스트라이크",
                "2볼 1스트라이크",
                "1볼 1스트라이크",
                "1스트라이크",
                "1볼 ",
                "2볼 ",
                "3볼 ",
                "낫싱"
            )
        );
```

```
 List<Integer> numInputUser = new ArrayList<>(List.of(
            // 3스트라이크
            123,
            // 2스트라이크
            124,
            // 2볼 1스트라이크
            132,
            // 1볼 1스트라이크
            182,
            // 1스트라이크
            184,
            // 1볼
            416,
            // 2볼
            712,
            // 3볼
            312,
            // 낫싱
            798
        ));
```

```
  @Test
    void 커퓨터가_유저에게_힌트를_준다() throws Exception {
        //given
        List<List<Integer>> numInputUser = new ArrayList<>(List.of(
            // 스트라이크 3 , 볼 0
            List.of(123),
            // 스트라이크 2 , 볼 0
            List.of(124, 143, 423),
            // 스트라이크 1 , 볼 2
            List.of(132, 321, 213),
            // 스트라이크 1 , 볼 1
            List.of(182, 134, 521, 324, 813, 283),
            // 스트라이크 1 , 볼 0
            List.of(184, 826, 483),
            // 스트라이크 0 , 볼 1
            List.of(416, 651, 247, 562, 357, 635),
            // 스트라이크 0 , 볼 2
            List.of(712, 218, 251, 238, 732, 352, 314, 381, 431),
            // 스트라이크 0 , 볼 3
            List.of(312, 231),
            // 스트라이크 0 , 볼 0
            List.of(798, 486, 589, 497, 465, 564, 464, 564, 654, 899, 789)
        ));
        Computer computer = new Computer();
        computer.numThreeRanOfComputerList = new ArrayList<>(List.of(
            1, 2, 3
        ));
        List<String> hints = new ArrayList<>(
            List.of(
                "스트라이크 3 , 볼 0",
                "스트라이크 2 , 볼 0",
                "스트라이크 1 , 볼 2",
                "스트라이크 1 , 볼 1",
                "스트라이크 1 , 볼 0",
                "스트라이크 0 , 볼 1",
                "스트라이크 0 , 볼 2",
                "스트라이크 0 , 볼 3",
                "스트라이크 0 , 볼 0"
            )
        );
        List<String> hintResult = new ArrayList<>();
        // when
        for (List<Integer> list : numInputUser) {

            for (int num : list) {
                if (computer.isRealRightNumOfUser(num)) {
                    computer.initComputer();
                }
            }
            hintResult.add(computer.toString());
        }
        // then
        assertThat(hintResult).containsAll(hints);
    }
```

```
스트라이크 : 볼 = 3:0, 2:0, 1:2, 1:1, 1:0, 0:1, 0:2, 0:3, 0:0 의 결과를 만든다
```



