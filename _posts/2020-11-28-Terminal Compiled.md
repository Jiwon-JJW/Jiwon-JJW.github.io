---
layout: post
title:  "자바 파일 shell로 upload 하는 방법 - MAC"
date:   2020-11-28 19:10:13 +0800
categories: Study
tags: java javafile shell
---



## 이클립스 없이 혼자 컴파일 하기

* 이클립스나 다른 자바 프로그램 도구가 없이도 컴파일 하는 것에서 가장 필요한 것:
  * 자바 파일을 스스로 **컴파일** 할 수 있어야한다.
  * 컴파일 한 클래스 파일을 **실행**하는 과정을 거쳐야한다.



* 필요한 도구:

  * Mac: terminal

    기본적으로 스포트라이트 에서 terminal을 입력해서 **터미널**을 실행하면 된다.



* 사용하는 명령어:

  * javac :

    * 터미널에서 javac 만 누르고 엔터를 누를 시, 어떻게 사용하는지 방법을 알려준다.

      ```java
      Usage: javac <options> <source files>
      ```

      그 중, 아주 기본적인 사용 방법만을 가져왔다.

    * java 파일을 컴파일 하여, class 파일을 만들어 주는 기능.

  * java :

    * 컴파일된 파일을 가상 머신에서 실행(=컴파일된 클래스파일을 실행) 하는 작업을 한다.



### shell로 컴파일 하기:

1. 파인더에서 java 파일이 있는 프로젝트 디렉토리로 들어가, 경로를 복사한다.

2. 터미널에서 `cd` 를 입력한 후, 프로젝트 디렉토리로 이동한다.
   (이 때, 프로젝트 디렉토리의 내부 정보를 확인하고 싶다면 `ls`를 입력하자.)

3. `javac` 를 입력하여 사용 방법을 확인 한 후, 원하는 파일을 컴파일 한다.

   ```shell
   javac 자바 파일이름.java
   ```

   이후 `ls`를 입력하면, 내부 구조 안에 java파일과 같은 이름의 class파일이 컴파일되어 생성 된 것을 볼 수 있다. 

   * 에러가 발생 할 경우:

     ```shell
     javac -cp "." Program.java
     ```

     * cp : class path
     * "." : 현재 디렉토리



### shell로 실행 하기:

1. `java`명령어를 입력하여 class파일을 실행시킨다.

   ```shell
   java Program
   ```

   이 때, 파일 명의 뒤에 `.class` 는 붙이지 않는다.

   * 에러가 발생 할 경우:

     ```java
     java -cp "." Program
     ```

     



* javac 와 java 명령어가 어디에 있는 명령어인지 확인하고 싶을 경우, 아래의 방법을 따라하면 알 수 있다:
  

  1. pwd 명령어로 현재 경로를 확인한다.
  2. /usr/libexec/java_home 을 입력하여 자바의 설치경로를 확인한다.
  3. cd 명령어로 위에서 나온 자바의 설치경로로 이동한다.
  4. ls 명령어로 현재 경로에 있는 파일들의 목록을 확인한다.
  5. 그 중 bin 폴더로 이동하면, java와 javac가 있는 것을 확인 할 수 있다.
     javac 명령어는 이 곳의 javac 파일이 실행 되는 것.

  

  > 사용 된 명령어:
  >
  > * pwd(Print Working Directory) : 
  >
  >   * 현재 경로를 확인하는 명령어.
  >
  > * /usr/libexec/java_home :
  >
  >   * 자바의 설치 경로를 확인하는 명령어.
  >
  >   * 명령어를 확인하면 cd명령어를 사용하여, 해당 경로로 이동 할 수 있다.
  >
  > * cd(Change Directory) :
  >
  >   * cd /디렉토리 주소/ 의 형식으로 입력 시, 해당 디렉토리로 이동할 수 있다.
  >   * 경로로 제대로 이동되었는지 확인하고싶다면, pwd를 한 번 더 사용하면 된다.
  >
  > * ls(list segments) :
  >
  >   * 현재 경로에 있는 파일들의 목록을 확인한다.



## 라이브러리를 사용하는 프로그램을 컴파일 하는 방법

* OKJavaGoInHome.java 라는 외부 프로그램을 사용하는 파일을 컴파일 해보고자 한다.

  ```java
  import org.opentutorial.iot.Elevator;
  import org.opentutorial.iot.Lighting;
  import org.opentutorial.iot.Security;
  
  public class OkJavaGoInHome{
    public static void main(String[] args){
      
      ...
    }
  }
  ```

* 위의 파일은 import구문을 통해 OkJavaGoInHome 클래스가 있는 폴더의 org.opentutorial.iot의 클래스들을 불러들이고 있기 때문에, 
  컴파일을 시작 할 때 자동적으로 클래스 안의 Elevator, Lighting, Security 클래스들도 컴파일을 해준다.

* 이 때, lib폴더를 새로 만들어, org폴더를 lib폴더 안으로 이동시킨다.
  lib 라이브러리의 일부로 만드는 것이다.



### 외부 라이브러리도 포함해서 컴파일 하기

1. 외부 라이브러리도 포함해서 컴파일 하려면, `-cp(--class-path)`를 이용하여 외부 라이브러리도 함께 지정을 해줘야한다.

   ```shell
   javac -cp ".:lib" OkJavaGoInHome.java
   ```

   `-cp ".:lib"`의 경우, 현재 폴더(.)와 lib 폴더에서 필요한 자바파일을 함께 컴파일 하라는 의미이다.



### 외부 라이브러리도 포함해서 실행하기

1. 외부 라이브러리를 포함해서 컴파일 하였듯이, 실행도 `-cp`를 사용하여 외부 라이브러리도 포함하여 실행 시켜야한다.

   ```shell
   java -cp ".:lib" OkJavaGoInHome
   ```

   

### 실행하려는 파일에 argument(아규먼트)의 값을 필요로 하는 경우

1. 위에서 외부 라이브러리를 lib폴더에 넣었던 것과는 반대로, 외부 라이브러리를 lib안에 넣지 않고 시작한다.
   즉, org 파일이 main java 파일과 함께 있는 상태에서 실행한다.

   ```
   ㄴOkJavaGoInHome.java
   ㄴOkJavaGoInHomeInput.java
   ㄴProgram.java
   ㄴorg
   	ㄴopentutorials
   		ㄴiot
   			ㄴ ...
   ```

2. OkJavaGoInHomeInput.java 를 컴파일 한다.

   ```shell
   javac OkJavaGoInHomeInput.java
   ```

   * 위의 파일의 경우...

     ```java
     import org.opentutorials.iot.DimmingLights;
     import org.opentutorials.iot.Elevator;
     import org.opentutorials.iot.Lighting;
     import org.opentutorials.iot.Security;
      
     public class OkJavaGoInHomeInput {
      
         public static void main(String[] args) {
              
             String id = args[0];
             String bright = args[1];
             
             ....
      
         }
      
     }
     
     ```

     id 변수와 bright 변수가 args 파라미터를 이용해서 값을 받고 있다.
     이클립스 내에서는 Run Configuration의 Argument탭에서 입력했지만, 터미널에서는 다른 방식으로 아규먼트를 입력한다.

3. 실행하고자 하는 클래스 파일 이름 다음에 띄어쓰기를 이용하여 값을 입력한다.

   ```shell
   java OkJavaGoInHomeInput "JAVA APT 507" 15.0
   ```

   