---
layout: post
title:  "Programmers - K번째 수"
date:   2021-01-20 17:41:00 +0800
categories: Algorithm
tags: [java, Algorithm, Programmers]
comments: true
---

## [Java] Programmers - K번째 수

* [문제 링크](https://programmers.co.kr/learn/courses/30/lessons/42748?language=java)



* 나의 답:

  ```java
  import java.util.*;
  
  class Solution {
      static public int[] solution(int[] array, int[][] commands) {
          int[] answer = new int[commands.length];
  
  
  
          for (int i = 0; i < commands.length; i++) {
              ArrayList<Integer> a = new ArrayList<>();
  
              int x = commands[i][0];
              int y = commands[i][1];
              int k = commands[i][2];
  
              for (int j = x; j <= y; j++) {
                  a.add(array[j-1]);
              }
  
              Collections.sort(a);
              answer[i] = a.get(k-1);
          }
  
          return answer;
      }
  }
  
  ```







* 결과:
  ![스크린샷 2021-01-20 오후 5 44 26](https://user-images.githubusercontent.com/69128652/105149679-25357c80-5b47-11eb-9b37-27cb70f4c4a6.png)