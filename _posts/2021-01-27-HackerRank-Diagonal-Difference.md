---
layout: post
title:  "HackerRank - Diagonal Difference"
date:   2021-01-27 19:41:00 +0800
categories: Algorithm
tags: [java, Algorithm, HackerRank]
comments: true
---

* ## [Java] HackerRank - Diagonal Difference

  - [문제 링크](https://www.hackerrank.com/challenges/diagonal-difference/problem)

    

  - 정사각 행렬이 주어지면, 왼쪽에서 오른쪽 대각선의 합과 오른쪽에서 왼쪽 대각선의 합의 차를 구하여 반환하는 문제.
  
  
  
- 나의 답:
  
    ```java
    import java.util.*;
    
  public class DiagonalDifference {
    
      public static int diagonalDifference(List<List<Integer>> arr) {
            // Write your code here
  
            int sum1 = 0;
          int sum2 = 0;
    
            for (int i = 0; i < arr.size(); i++) {
                for (int j = 0; j < arr.size(); j++) {
                    if (i == j) { // 왼쪽에서 오른쪽 대각선
                        sum1 += arr.get(i).get(j);
                      // 행렬로 이뤄진 리스트의 값을 구하여 더함.
                    }
                    if ((i == (arr.size() - 1) && j == 0) || -(i - (arr.size() - 1)) == j) { // 오른쪽에서 왼쪽 대각선
                        sum2 += arr.get(i).get(j);
                    }
                }
            }
    
            int answer = sum1 - sum2 > 0 ? sum1 - sum2 : -(sum1 - sum2);
          // sum1과 sum2의 차가 음수일 경우, 양수로 변환
    
            return answer;
        }
    }
    
    ```
    
    

