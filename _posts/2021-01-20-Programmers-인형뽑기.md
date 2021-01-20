---
layout: post
title:  "Programmers - 인형뽑기"
date:   2021-01-20 17:37:00 +0800
categories: Algorithm
tags: [java, Algorithm, Programmers]
comments: true
---

## [Java] Programmers - 인형뽑기

* [문제 링크](https://programmers.co.kr/learn/courses/30/lessons/64061)



* 나의 답:

  ```java
  import java.util.Stack;
  
  class Solution {
  
    public int solution(int[][] board, int[] moves) {
      int result = 0;
  
      Stack<Integer> stack = new Stack<>();
      for (int k = 0; k < moves.length; k++) {
        int x = moves[k] - 1;
        
        for (int i = 0; i < board.length; i++) {
          
          int num = board[i][x];
          
          if (num == 0) {
            continue;
          }
          if (!stack.empty() && stack.peek() == (num)) { 
            // stack.peek() 넣어진 값들 중, 가장 위에 있는 값을 얻는다.
            stack.pop();
            // stack내에 있는 값 중, 가장 위에 있는 값을 삭제한다.
            result += 2;
            
            
          } else {
            stack.push(num);
          }
            board[i][x] = 0;
         	// 인형을 뺐으니, 값을 0으로 돌린다.
            break;
        }
      }
  
      return result;
    }
  }
  ```



* 원래는 stack말고 ArratList를 사용해봤는데, 바구니의 구조와 stack의 구조가 비슷하다고 생각되어 stack으로 변경하였다.
  



* 결과:
  ![스크린샷 2021-01-20 오후 5 39 51](https://user-images.githubusercontent.com/69128652/105149088-814bd100-5b46-11eb-818c-75e8456aa679.png)