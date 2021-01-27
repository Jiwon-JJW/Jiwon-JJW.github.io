---
layout: post
title:  "HackerRank - Save the Prisoner!"
date:   2021-01-27 19:42:00 +0800
categories: Algorithm
tags: [java, Algorithm, HackerRank]
comments: true
---

* ## [Java] HackerRank - Save the Prisoner!

  - [문제 링크](https://www.hackerrank.com/challenges/save-the-prisoner/problem)

    

  - 죄수가 n명이 순서대로 의자에 앉아있고, m개의 사탕이 있는데
    s번째 죄수부터 차례대로 사탕을 나누어준다.
    마지막 사탕은 무조건 아주 신 사탕인데, 이 것을 먹은 사람의 번호를 반환하는 문제. 
  
  
  
- 나의 답:
  
    ```java
    public class SaveThePrisoner {
    
        // Complete the saveThePrisoner function below.
        static int saveThePrisoner(int n, int m, int s) {
            int t = (m-1)% n + s;
    
            return t > n ? t -n : t;
          // 위의 수식을 계산 한 값이 죄수 수 보다 크다면, 계산 한 값에서 죄수 값을 빼서 값을 반환.
        }
    }
  ```
    
      

