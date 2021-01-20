---
layout: post
title:  "Programmers - 모의고사"
date:   2021-01-20 17:41:00 +0800
categories: Algorithm
tags: [java, Algorithm, Programmers]
comments: true
---

## [Java] Programmers - 모의고사

* [문제 링크](https://programmers.co.kr/learn/courses/30/lessons/42840)



* 나의 답:

  ```java
  import java.util.ArrayList;
  import java.util.Collections;
  
  class Solution {
    public Integer[] solution(int[] answers) {
      int[] students = new int[3];
  
      int[] student1= {1,2,3,4,5};
      int[] student2= {2,1,2,3,2,4,2,5};
      int[] student3= {3, 3, 1, 1, 2, 2, 4, 4, 5, 5};
      ArrayList<Integer> winner = new ArrayList<>();
  
      // 배열만큼 돌면서 정답이 맞는지 비교한다.
      for(int i = 0; i < answers.length; i++){
        if(answers[i]== student1[i%student1.length]){
          students[0] +=1;
        }
        if(answers[i]== student2[i%student2.length]){
          students[1] +=1;
        }
        if(answers[i]== student3[i%student3.length]){
          students[2] +=1;
        }
      }
      
      // 최고 점수를 max에 넣는다.
      int max = Math.max(Math.max(students[0],students[1]),students[2]);
  
      // max의 값과, 학생들의 점수를 비교하여 같은 사람을 list에 넣는다.
      if(max == students[0]){winner.add(1);}
      if(max == students[1]){winner.add(2);}
      if(max == students[2]){winner.add(3);}
  
      // 순서대로 정렬
      Collections.sort(winner);
  
      Integer[] answer = winner.toArray(new Integer[winner.size()]);
  
      return answer;
    }
  }
  ```







* 결과:
  ![스크린샷 2021-01-20 오후 5 44 26](https://user-images.githubusercontent.com/69128652/105149679-25357c80-5b47-11eb-9b37-27cb70f4c4a6.png)