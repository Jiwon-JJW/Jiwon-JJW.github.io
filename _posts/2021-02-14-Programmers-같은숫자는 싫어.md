---
layout: post
title:  "Programmers - 같은 숫자는 싫어"
date:   2021-02-14 19:37:00 +0800
categories: Algorithm
tags: [java, Algorithm, Programmers]
comments: true
---

## [Java] Programmers - 같은 숫자는 싫어

* [문제 링크](https://programmers.co.kr/learn/courses/30/lessons/12906)



* 나의 답:

  ```java
  import java.util.*;
  
  class Solution {
  
      public int[] solution(int[] arr) {
          List<Integer> a= new ArrayList();
  
          for(int i = 0; i < arr.length; i++){
              if(i == 0){
                  a.add(arr[i]);
                  continue;
              }
              if(arr[i] == arr[i-1]){
                  continue;
              } else {
                  a.add(arr[i]);
              }
          }
          int[] answer =a.stream().mapToInt(i -> i).toArray();
  
          return answer;
      }
  }
  ```



* 결과:
  ![스크린샷 2021-02-14 오후 7 45 16](https://user-images.githubusercontent.com/69128652/107874462-421e5f00-6efd-11eb-8fc1-566cdf09abd8.png)

