[요약지](https://github.com/park0ho/park0ho.github.io/blob/d626896921a989fbd85fb579835c8769a2fc409e/docs/%5B%EC%9A%94%EC%95%BD%EC%A7%80%5D%20%EB%AF%B8%EB%8B%88%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8_Ver3_(%EB%B0%95%EC%98%81%ED%98%B8).pdf)

[보고서](https://github.com/park0ho/park0ho.github.io/blob/d626896921a989fbd85fb579835c8769a2fc409e/docs/MiniProjectVer3.pdf)

## ㅇ 교육과정
  - 기 간 : '22. 8. 17.(수) ~ 12.30.(금)
  - 기 관 : 대한상공회의소 서울기술교육센터
  - 교육명 : AI활용 Big Data 시스템 개발자

## ㅇ 교육내용 : JSP(Html5)


## ㅇ Project : Mini Project(Ver 3.0)
- 언어 : JSP
- 환경 : Web(Chrome에 최적화)
- 내용 : Server-Side Image Processing Using JavaScript
- 지도교수 : 우재남  
  상기 내용은 본 포스팅의 개요이다.
  대한상공회의소 서울기술교육센터에서 'AI 활용 Big Data 시스템 개발자' 과정을 수강하면서 배운 내용이다.

## ㅇ Project 변화 내용
- Mini Project V1.0 : Gray Image / JavaScript, Html5 / PC
- Mini Project V2.0 : Color Image / JavaScript, Html5 / PC
- Mini Project V3.0 : Color Image / JSP, Html5 / Server + PC
  '디지털 영상처리' 주제로 약 4주간의 수업을 수강하였다.
  처음에 Gray Image로 영상처리 기법을 중심으로 한 JavaScript, 화면에 시현하기 위한 Html5를 배웠다.
  그 이후에는 동일환경에서 Color Image(JPG)파일로 보다 다양한 효과 및 Event Listener, 색 추출 등에 대한 기법을 알게 되었다. 이번에는 비록 일주일 남짓 짧은 시간이지만 JSP를 통해서 실제 Web환경과 가장 유사한 프로그래밍을 해볼 수 있었다.


## ㅇ Project 주제 선정(스마트폰 게임 - Dream Blast)
- 최소 몇십년간은 스마트폰으로 게임을 하는 사람들이 많을 것이다. 스마트폰의 기술 발전 그리고 게임의 다양화 등 관련 환경은 급속도로 변하고 있다. 따라서 관련 기술에 대한 주제는 지금도 그렇지만 향후에도 꾸준히 코딩 및 밥벌이에 좋은 주제가 될 것이다.
- 지금 보니 난 이 게임을 나름 열심히 하고 있었다. 레벨 6820
- 한번에 한 레벨을 꺨 수 없는 경우가 많았으니 적어도 10,000번 이상은 게임을 했다고 볼 수 있다.
- 
![game6820](https://user-images.githubusercontent.com/108249298/200246638-ca365609-54af-4c0f-8c5d-323593cb384c.png)

- 지난 Mini Project 2.0에서도 언급한 것 처럼 내 목표는 이 게임을 내가 아닌 '내가 만든 AI'가 하는 것이다.
- 관련 필요 기술은 영상처리(기 완료), 서버/PC/스마트폰 입출력 연동, AI 모델 개발 등 많이 있다.
- 현재는 아직 높은 수준은 아니지만 Color 영상처리로 내가 원하는 블록 색깔을 추출 할 수 있고 해당 내용을 서버/PC 간에 파일 업로드/다운로드가 가능한 상태이다.
- 이번 교육과정에서 AI 도 학습하게 되면 어느정도는 내가 원하는 목적을 달성할 수 있지 않을까.


## ㅇ 아래부터는 이전 포스팅처럼 프로그램 source code를 중심으로 설명하듯이 작성하려고 한다.
> 지금의 '나'는 내용을 어느정도 이해하고 활용할 수 있지만 몇 개월 후의 '나'를 위해서 자세히...~!!!!

## ㅇ서버-클라이언트 구조 이해
- 가장 먼저 선행되어야 할 것이 서버, 클라이언트 개념에 대한 이해이다.
(나는 약 10년간 공군 정보통신장교로 근무하면서 OO 체계의 서버를 24시간 교대근무하면서 무중단 운영한 경험이 있다. 그 떄 서버-클라이언트-네트워크에 대한 아주 얇은 기본적인 지식은 머리와 몸에 체득하였다.)
![server_client](https://user-images.githubusercontent.com/108249298/200246734-881a025a-7738-4761-b7e7-d2d45c0f8508.png)

## ㅇ Client(PC) 소스코드 : Html5로 작성

- PC → 서버로 정보를 전송하기 위해서는 submit 이라는 기능을 사용 하여야 한다.
- 아래 그림은 PC 에서 보이는 화면이다. submit 은 버튼처럼 생겼으며 'processing!!' 이라고 이름을 주었다.

  (디자인...CSS... 언젠가 필요하면 공부해서 다른 홈페이지들 처럼 예쁘게 꾸며야지)
![sw_Ui](https://user-images.githubusercontent.com/108249298/200246817-aaba69fb-54d5-4bac-9feb-b867af1c6cb8.png)

- submit 을 위해서는 'form' 안에 사용자가 입력하는 부분을 작성하여야 하며 이번 프로젝트에서는 총 3개의
 사용자 입력이 있다.
1. 영상처리 알고리즘 종류
2. 파라미터 2개(밝게/어둡게, 색 추출 범위 등)

```java
<h1> Digital Image Processing(Color) </h1>
<form action="Color_pyh_server.jsp" method="post" enctype="multipart/form-data">
	
	<p> <select name="algo">
			<option value=""> -------- Algorithm -------- </option>
			<option value="101"> 반전영상 </option>
			<option value="102"> 밝게/어둡게 </option>
			<option value="103"> 상하 미러링</option>
			<option value="104"> 좌우 미러링</option>

```

## ㅇ Server-Side 소스코드

- JSP = JAVA ?
JSP는 JAVA와 거의 유사하다. 아니 같다고 해도 무방할 정도 이다.
    <%@ page 이후에는 JAVA처럼 필요한 class import문 작성 %>
- 기본적인 io, util class
    파일의 업로드/다운로드에 필요한 oreilly class
    칼라 이미지 처리에 필요한 imageio, awx.image class

```java
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<%@ page import="java.io.*" %>   
<%@ page import="java.util.*" %>   
<%@ page import="com.oreilly.servlet.*" %>   
<%@ page import="com.oreilly.servlet.multipart.*" %>  
<%@ page import="javax.imageio.*" %>  
<%@ page import="java.awt.image.*" %>

```

## ㅇ 전역 변수부 : Mini Project 1,2와 거의 유사
- JavaScript에서는 let, var 등으로 모든 변수를 선언 하였다.
  (심지어는 선언하지 않은 변수도 가능하다)
- 하지만 JSP에서는 int, float, File, String, 배열 등 각 변수에 맞는 변수들을 정확히 선언하여야 한다.
- 아직 Java는 배우기 시작한 단계여서 변수의 선언부 부터 많은 의문과 때로는 고생을 한 부분도 있다.

```java
/////////////
// 전역 변수부//
/////////////
int[][][] inImage;
int inH, inW;
int[][][] outImage;
int outH, outW;
File inFp, outFp;

float[] rgb = new float[3];
float[] hsv = new float[3];
float[] abc = new float[3];
float[] def = new float[3];

//Parameter Variable
String algo, para1, para2;
String inFname, outFname;
```

## ㅇ 영상처리 함수부 - reverseImage(반전영상)
- Mini Project 1,2와 거의 유사하다. 출력 영상을 위한 배열 선언 부분을 제외하고는 동일
```java
public void reverseImage(){
	// (3-1) 반전 영상
	// (중요!) 출력 영상의 크기 결정 (알고리즘에 의존)
	outH = inH;
	outW = inW;
	outImage= new int[3][outH][outW];
	/// ** Image Processing Algorithm **
	for (int rgb=0; rgb<3; rgb++){
		for (int i=0; i< inH; i++) {
			for (int k=0; k<inW; k++) {
				outImage[rgb][i][k] = 255 - inImage[rgb][i][k];
			}
		}
	}
}  // reverseImage
```

> 이후에 중복되는 알고리즘은 따로 서술하지 않았다.
  (Mini Project 1,2편 포스팅 참고)


## ㅇ 구현한 기능
![구현한 기능](https://user-images.githubusercontent.com/108249298/200264263-e7517d4f-733e-470e-9d22-fa6dc9c74153.png)

## ㅇ PC → Server 파일 업로드/다운로드 관련
![파일 업로드 다운로드 관련](https://user-images.githubusercontent.com/108249298/200264378-29a9ae51-f077-454b-ba64-70d04bfe1f54.png)

- Client의 'form' 부분에서 입력 받은 파라미터들을 MultipartRequest 기능을 통해서 서버에서 변수로 입력 받을 수 있다. 
(주의할 점은 파라미터 순서가 반대라는 것이다)
- client : (사용자가 보았을때 위에서 아래로) 알고리즘 종류 - 파라 1 - 파라2 순서
- 서버(JSP) 코드 : 파라2(para2) - 파라1(para1) - 알고리즘 종류(algo)
> Enumeration file을 통해서 여러개 파일의 이름을 서버로 입력받을 수 있으나, 이번 프로젝트에서는 1개의 파일만 upload 되는 것으로 가정하였다.
![upload 파일 선언](https://user-images.githubusercontent.com/108249298/200264552-f4207e20-68f5-4a45-96e7-da105788e622.png)

- upload 파일 선언 부분에서 경로(C:/upload/)는 서버에서의 경로이다. 사용자가 영상처리 하고싶은 파일을 선택하고 processing 버튼을 눌렀을때 서버의 해당 경로에 파일이 전송되고, 서버는 그 파일을 메모리에 입력시켜서 영상처리를 수행한다.
- ImageIO class를 활용하면 입력 영상의 폭, 높이를 바로 알아낼 수 있다.(getHeight, getWidth)

- 칼라 사진에 대한 영상처리이므로 당연히 3차원의 변수를 선언해야 한다.(rgb/폭/높이)


## ㅇ 서버로 업로드 된 파일 → 메모리 입력
![서버로 업로드 된 파일](https://user-images.githubusercontent.com/108249298/200264670-ab8b1833-6017-4447-8fab-ff3d35867599.png)
- 이중 for문(width, height)를 활용하여 각 좌표에서의 rgb 정보를 r, g, b 각 변수에 입력 받는다.
- 상기 코드의 주석 부분은 RGB가 F3 77 D6 일때의 예시이며 0xFF와 &(AND) 연산을 통하여 r, g, b 값을 구할 수 있다. 이 값을 입력영상(inImage0의 0,1,2(r,g,b)에 입력 받으면 영상처리 알고리즘을 수행할 준비가 완료 된다.
![파일 저장](https://user-images.githubusercontent.com/108249298/200264774-c157bd21-e75f-4bec-a806-77cd7594f281.png)

- 영상처리가 완료된 파일은 Client가 download 받을 수 있도록 서버의 특정 경로에 저장하여야 한다. 본 프로젝트에서는 (C/out/) 경로에 out_ 으로 시작하는 파일을 저장하였다.
- 위에서 파일을 메모리에 저장하는 것과 반대로 이번에는 메모리에 있는 정보를 파일로 저장하여야 한다.
- and(&) 연산이 아닌 or(|) 연산을 활용하여 출력영상(outImage)의 r, g, b의 변수에 저장되어 있는 값을 추출하여 파일로 저장하였다.
-  Image.setRGB(폭, 높이, 값) // image class의 기능
    ImageIO.write(변수, 사진 포멧)

## ㅇ S/W 수행 절차 및 결과

- 엠보싱을 수행한 결과는 아래와 같다. Mini Project1,2와 당연히 동일하게 나온다.
![엠보싱 결과](https://user-images.githubusercontent.com/108249298/200264885-beb0b6f3-d528-4b07-b1e0-8d111dff3215.png)
- 그 외 코딩한 다른 효과들의 알고리즘, 결과는 이전 Mini Project 1,2의 포스팅을 참고하면 된다.

## ㅇ JavaScript → Java (RGB to HSV , HSV to RGB 함수)
- 이번 프로젝트에서 가장 고생한 부분이다. 몇 줄 안되는 코드를 거의 하루내내 수정하고 또 수정하면서 해결!!!
- 사진에 대한 칼라 처리를 위해서는 아래의 과정을 수행하여야 한다.
 > RGB로 되어 있는 사진을 HSV로 변환 → H, S, V 각 변수를 변경
   → 화면 시현 및 파일 다운로드를 위해서 HSV를 다시 RGB로 변환
- JavaScript 프로젝트를 수행할 때는 RGB to HSV, HSV to RGB 함수를 제공 받았다.
 (Special Thanks to 우재남 교수님)
- 이번 프로젝트에서는 해당 코드가 없었다. Google 께서 몇 개의 소스코드를 제공해주었으나 내가 지금까지 배운 소스코드와 맞지 않았다. 변수명이 다른 것을 변경하고 적용해도 원하는 영상처리가 되지
않고 에러가 발생하거나 검은 화면만 보였다.
- 교수님의 JavaScript 코드는 아래와 같다.
![rgb2hsv](https://user-images.githubusercontent.com/108249298/200265228-ce1eb3c7-1d90-4837-bc07-a7c1f012d4ce.png)

![hsv2rgb](https://user-images.githubusercontent.com/108249298/200265302-f908075e-37c4-46db-9bbc-0abd2f773b27.png)

- 내가 작성한 코드는 아래와 같다.

```java
public float[] rgb2hsv
   (float r, float g, float b) {
	
	float max1 = Math.max(r,g);
	float max2 = Math.max(g,b);
	float max = Math.max(max1,max2);
	float min1 = Math.min(r,g);
	float min2 = Math.min(g,b);
	float min = Math.min(min1, min2);
	float d = max - min; 
	float h=0, s;
	float v = max / 255;
	
	if (max==0)
		 s = 0;
	else
		 s = d/max;	   
	
	if(max==min){
		h = 0; }

	else if(max==r){
		h = (g - b) + d * 
			(g < b ? 6: 0); h /= 6 * d; }
	else if(max==g){
		h = (b - r) + d * 2; h /= 6 * d; }
	else{
		h = (r - g) + d * 4; h /= 6 * d; }	
								 
	hsv[0] = (float)(h);
	hsv[1] = (float)(s);
	hsv[2] = (float)(v);
	
	return hsv;
	}


public float[] hsv2rgb(float h, float s, float v){
	float r=0, g=0, b=0, f, p, q, t;
	 h=h*360; s=s*100; v=v*100;
	 
     h = Math.max(0, Math.min(360, h));
     s = Math.max(0, Math.min(100, s));
     v = Math.max(0, Math.min(100, v));        
     	
     h /= 360;   s /= 100;     v /= 100;
     int i = (int) Math.floor(h * 6);
     f = h * 6 - i;
     p = v * (1 - s);
     q = v * (1 - f * s);
     t = v * (1 - (1 - f) * s);
          
     if(i%6==0){
    	 r = v; g = t; b = p;   }     
     else if(i%6==1){
    	 r = q; g = v; b = p;   }
     else if(i%6==2){
    	 r = p; g = v; b = t;   }
     else if(i%6==3){
    	 r = p; g = q; b = v;   }
     else if(i%6==4){
    	 r = t; g = p; b = v;   }
     else if(i%6==5){
    	 r = v; g = p; b = q;   }
    
  	rgb[0] = (float) r*255;
  	rgb[1] = (float) g*255;
  	rgb[2] = (float) b*255;
  
    return rgb;
}
```

- 문제점 1) max, min 값 구하기
    1. JavaScript에서는 Math.max, min 함수에 (r, g, b) 값을 입력하면 최대, 최소값을 구할 수 있다.
    2. 하지만 JSP에서의 Math.max, min은 두 개의 값만 비교할 수 있다.
    3. 따라서 Math.max, min을 세번 이용하여 최대값, 최소값을 구할 수 있었다.
![minmax](https://user-images.githubusercontent.com/108249298/200265427-f727e87f-ec09-43ee-b238-3dd549a41603.png)

- 문제점 2) JSP에서 Switch~Case문
    1. 이 부분이 가장 오랜 시간을 투자하게 만들었다.
    2. JSP에서는 Switch 문의 비교할 변수(또는 수식)에는 한가지 조건이 있는데 '정수' 여야만 한다는 것이다.
    3. 처음에는 JSP에서도 동일하게 Switch~case문을 활용하였고 정수로 만들고자 (int) i%6을 선언하고 아래의 r, v, g, t, b, p에도 동일하게 (int) 로 float 변수를 int로 변환을 하였다. 

   ![jsSwitchCase](https://user-images.githubusercontent.com/108249298/200265610-f247800b-c305-4952-b480-2ddd10228f38.png)
    4. 하지만 문제는 여기서 발생한다. rgb to hsv를 하였을때 h, s, v 값의 범위는 0 ~ 1.0 사이의 값이 나온다.
    이 값에 (int)를 선언하면......... 모든 값은 0 또는 1로만 변한다. 당연히 결과는 엉망이 나온다.(대부분의 사진에서 온통 검은색에 점 한두개가 찍혀 나온다)
  5. (해결방안) Switch~case 문을 if 문으로 변경한다. if문에서 비교하는 값은 제한이 없다.
   (int, float... 등 모두 가능하다)
  6. 다른 방법은 없을까?
  7. 아직 못 찾았고, 안 찾아 보았다. 다른 좋은 방법을 아는 분은 댓글로 알려주세요...

- 문제점 3) 리턴 값
    1. JavaScript에서는 리턴 값의 갯수에 제한이 없다. 하지만 JSP에서는 1개의 값만 리턴이 가능하다.
    2. 다만, 배열도 1개의 값으로 간주되어서 여러개의 값이 필요할때에는 배열을 선언하는 것으로 대체할 수 있다.
 
![return](https://user-images.githubusercontent.com/108249298/200265718-2a5a06a9-1d10-46cc-8880-ecb56f57ba0c.png)


- 문제점 4) JSP에서 변수형 지정
    1. 이것은 문제점이라기 보다는 아직 내가 JSP(즉.. JAVA)를 공부하는 과정이어서 그렇다고 볼 수 있다.
    2. 함수 선언시에 리턴값에 해당하는 함수 선언, 각 자료형에 대한 충분한 이해(int, float, double, String...)
    3. 추후 교육과정이 진행되면서 JAVA, Phython 등의 언어를 배우면 자연스레 해결 될 것이다.

- 오랜시간 걸려서 만든 몇 줄 짜리 코드이지만 수업 듣는 카페(빅데이터 4)에 공유하여 많은 동료 수강생들이 활용하고 있는 것을 보고 내심 뿌듯하고 고생한 보람도 느꼈다.
(하지만.. 시행착오를 겪으며 수정한 경험은 전부 나의 재산이 되겠지.!!)


## ㅇ 실제 활용 예시
![game](https://user-images.githubusercontent.com/108249298/200265812-c192abda-034c-4791-afab-c870cb801e38.png)

- 결과는 Mini Project 2와 동일하다.
- 원하는 블록의 색을 선택하였을 때, 각 색깔 블록만 표시되고 해당 파일은 서버에 저장되며 Client에서 다운로드 가능하다.
- 내가 원하는 시나리오
    1. 스마트폰 - PC 연동
    2. PC에서 스마트폰 화면 캡처
    3. 캡처 된 화면 서버로 전송
    4. 서버에서 블록 색깔 인식 및 추출
    5. AI가 최적의 블록 색깔 판단 후 PC로 결과 전송
    6. PC에서 스마트폰으로 해당 결과 전송 및 게임에서 가장 효율적인 블록 터치
    7. 게임 성공
- 현재 가능한 부분 2, 3, 4 / 나머지 추후 학습 및 구현 예정

## ㅇ 결론 및 추후 계획
![conclusion](https://user-images.githubusercontent.com/108249298/200265901-66502a8f-ac1c-4cf6-ae84-287c30c667dc.png)
- 동영상에 효과 구현 및 Web 구현 모두 아직은 먼 미래의 이야기 처럼 느껴지지만
- 지금처럼 꾸준히 시간과 노력을 투자하면 미래가 금방 다가 오지 않을까...


## ㅇ 최종 결론
- 이제 JavaScript, Html5, JSP 세 가지의 언어에 대한 수업이 모두 끝났다.
- 거의 대부분 교수님께서 주신 코드이지만 내가 어느정도 이해하고 활용하고 있는 것일까?
- 최종적으로 개발하고자 하는 AI가 나 대신에 게임하는 모습을 언제쯤 볼 수 있을까?
- 앞으로 배울 Java, Phython, R... 등의 언어는 지금보다 수월하게 배울 수 있을까?
- 다른 Mini Project 또는 언어를 하나씩 배울 때마다 지금처럼 블로그에 나름 친절히(!) 정리 할 수 있을까?



이제 끝.  감사합니다. 또 오세요~^^
