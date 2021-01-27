---
layout: post
title:  "HackerRank - Time Conversion"
date:   2021-01-27 19:42:00 +0800
categories: Algorithm
tags: [java, Algorithm, HackerRank]
comments: true
---

* ## [Java] HackerRank - Time Conversion

  - [문제 링크](https://www.hackerrank.com/challenges/time-conversion/problem)

    

  - 10:54:22PM 의 형식으로 값을 받으면, 22:54:22 처럼 형식을 변환하여 출력시킴.
  
  
  
- 나의 답:
  
    ```java
    public class TimeConversion {
        static String timeConversion(String s) {
          String[] time = s.split(":");
          if(time[2].contains("AM")){
            // String에 AM이 있는지 확인.
              if (time[0].equals("12")){
                  time[0] = "00";
              }
              time[2] = time[2].replace("AM","");
            // time[2]의 뒤에 붙은 AM을 제거.
  
              return String.join(":", time);
          }
  
          if(time[2].contains("PM")){
              if (!time[0].equals("12")){
                  int hh = Integer.parseInt(time[0]);
                  time[0] = String.valueOf(12+hh);
              }
              time[2] = time[2].replace("PM","");
              return String.join(":", time);
          }
  
          return s;
      }
  }
  ```
  
    

