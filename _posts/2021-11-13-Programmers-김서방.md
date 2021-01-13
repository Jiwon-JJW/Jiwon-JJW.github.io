---
layout: post
title:  "Programmers - 서울에서 김서방 찾기"
date:   2021-01-13 19:37:00 +0800
categories: Algorithm
tags: [java, Algorithm, Programmers]
comments: true

---

## [Java] Programmers - 서울에서 김서방 찾기

* [문제 링크](https://programmers.co.kr/learn/courses/30/lessons/12919)

![스크린샷 2021-01-13 오후 6 39 28](https://user-images.githubusercontent.com/69128652/104434539-ada7a080-55ce-11eb-86a0-cd7e712f0559.png)



* 나의 답:

  ```java
  class Solution {
    public String solution(String[] seoul) {
  
      int x = 0;
      for(int i = 0; i<seoul.length; i++){
          if(seoul[i].equals("Kim")){
            x = i;
            break;
          }
      }
      String answer = "김서방은 "+x+"에 있다";
      return answer;
    }
  }
  ```



* 그냥 심심풀이로 해봤다.
  위 배열을 한 줄로 표현한 분의 풀이도 있던데, 나도 그렇게 획기적인 방법을 사용할 수 있도록 노력하는게 좋겠다..



* 결과:
  ![스크린샷 2021-01-13 오후 7 38 50](https://user-images.githubusercontent.com/69128652/104441398-f8c5b180-55d6-11eb-8018-c777756bfe0e.png)