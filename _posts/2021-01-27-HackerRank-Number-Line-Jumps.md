---
layout: post
title:  "HackerRank - Number Line Jumps"
date:   2021-01-27 19:35:00 +0800
categories: Algorithm
tags: [java, Algorithm, HackerRank]
comments: true
---

* ## [Java] HackerRank - Number Line Jumps

  - [문제 링크](https://www.hackerrank.com/challenges/kangaroo/problem)

    

  - 입력값 (x1, v1, x2, v2)
    캥거루 1 : x1의 자리에서 v1칸씩 점프 한다.
    캥거루 2 : x2의 자리에서 v2칸씩 점프 한다.
    같은 횟수로 점프했을 때, 만난다면 YES, 못만난다면 NO를 반환한다.

    * 예시:
      입력: 0 3 4 2
      출력: YES
      ![image](https://s3.amazonaws.com/hr-assets/0/1516005283-e74e76ff0c-kangaroo.png)

  

  

  - 나의 답:

    ```java
    public class NumberLineJumps {
    
        // Complete the kangaroo function below.
        static String kangaroo(int x1, int v1, int x2, int v2) {
    
            if (v1 < v2) { 
    // 캥거루 1은 2보다 뒤에서 시작하는데, 점프량이 더 적다면 만날 일이 없으므로, NO를 반환.
                return "NO";
            }
    
            while (true){
                if (x1 > x2){
                  // 캥거루 1이 2를 앞서 간다면, 만날 일이 없으므로 NO를 반환
                    return "NO";
                }
              
              // 캥거루들을 점프량 만큼 점프시킴
    
                x1+=v1;
                x2+=v2;
    
                if(x1 == x2){
                    return "YES";
                }
            }
        }
    
    }
    ```
    
    

