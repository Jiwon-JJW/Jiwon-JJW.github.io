---
layout: post
title:  "Programmers - 이상한 문자열 만들기"
date:   2021-01-20 17:41:00 +0800
categories: Algorithm
tags: [java, Algorithm, Programmers]
comments: true
---

## [Java] Programmers - 이상한 문자열 만들기

* [문제 링크](https://programmers.co.kr/learn/courses/30/lessons/12930)



* 나의 답:

  ```java
  class Solution {
      public String solution(String s) {
  
      //String의 글자들을 char형의 배열로 나눈다.
      char[] c  = s.toCharArray(); 
      int count = 0;
      StringBuilder answer = new StringBuilder();
  
      for(int i =0; i<c.length; i++){
        if(c[i] == ' '){
          // 띄어쓰기 일 경우, StringBuilder 안에 공백 추가.
          // 글자수를 세는 count의 값을 0으로 변경
          answer.append(" ");
          count = 0;
          continue;
        }else {
          if(count%2 == 0){
            // 글자수가 짝수일 경우, 대문자로 변경
            answer.append(Character.toUpperCase(c[i]));
        } else {
            // 글자수가 홀수일 경우, 소문자로 변경
            answer.append(Character.toLowerCase(c[i]));
          }
          count++;
        }
      }
  
      return String.valueOf(answer);
    }
  }
  ```



* 처음에 toLowerCase를 안해서, 실패가 떴었다... 당연히 대문자로 문자열이 들어올 수도 있다고 생각했어야 했는데, 이를 생각하지 못한 실수였다.
  다음번엔 좀 더 주의깊게 살펴보자.





* 결과:
  ![스크린샷 2021-01-20 오후 5 48 46](https://user-images.githubusercontent.com/69128652/105150156-bf95c000-5b47-11eb-87f5-6e2460d07bf9.png)