[요약지](https://github.com/park0ho/park0ho.github.io/blob/a13f3492e7ef06261500de126a1a173e4469ada3/docs/%5B%EC%9A%94%EC%95%BD%EC%A7%80%5D%20%EB%AF%B8%EB%8B%88%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8_Ver2_(%EB%B0%95%EC%98%81%ED%98%B8).pdf)

[보고서](https://github.com/park0ho/park0ho.github.io/blob/a13f3492e7ef06261500de126a1a173e4469ada3/docs/MiniProjectVer2.pdf)

## ㅇ 교육과정

- 기 간 : '22. 8. 17.(수) ~ 12.30.(금)

- 기 관 : 대한상공회의소 서울기술교육센터

- 교육명 : AI활용 Big Data 시스템 개발자


## ㅇ 교육내용 : JavaScript(Html 5 기반)

## ㅇ Project : Mini Project(Ver 2.0)
- 언어 : JavaScipt
- 환경 : Web(Chrome에 최적화)
- 내용 : Color Image Processing Using JavaScript
- 지도교수 : 우재남


상기 내용은 본 포스팅의 개요이다.

대한상공회의소 서울기술교육센터에서 'AI 활용 Big Data 시스템 개발자' 과정을 수강하면서 배운 내용이다.

JavaScript를 활용해서 Web에 'PhotoShop' 또는 스마트폰 APP 중에서 사진 편집 하는 기능을 구현하였다.

Mini Project(Ver 1.0)에서는 흑백인 Raw 파일에 대한 영상 처리를 구현 하였다.


## ㅇ Mini Project(Ver 1.0) 관련 블로그
[Mini Project(Ver1.0) Blog](https://blog.naver.com/hkpyh/222874503307)


## ㅇ Ver 1.0과 2.0의 차이점

- 영상 : 흑백(RAW) --> 칼라(JPG)

- 사진 크기 : 256 또는 512px(가로, 세로 동일) --> 다양한 크기

- 마우스 이벤트, 색 추출 등 사용자 편의 기능 추가


## ㅇ 본 포스팅에서는 PPT 보다는 코딩 위주의 설명을 통해서 color 영상처리에 대한 이해를 높이고자 한다.
(흑백 영상 처리와 중복되는 부분은 설명 생략)


## ㅇ openImage : 영상 파일을 입력

```javascript
function openImage() {
            // inFile = document.getElementById("inFile").files[0]; // 선택한 RAW 파일(LENNA512.RAW)
            var fileNum = document.getElementById('fileNum').value; // "55", "5"
            if (parseInt(fileNum) < 10)
                fileNum = "0" + fileNum; // "05"
            else 
                fileNum = fileNum
            var inFname = "Nature99(Small)/picture" + fileNum + ".jpg";  // Nature99(Small)/picture05.jpg
            // 그림 파일 --> 이미지 객체
            var imageObject = new Image(); // 빈 이미지 객체 생성
            imageObject.src = inFname; // 파일이 이미지객체에 쏙~~~ 들어감.
```
- 영상처리 코딩을 위해서 폴더에 picture00 ~ 99.jpg 이름의 100개 파일을 사전에 준비하였다.
- 처리 하고 싶은 파일의 번호를 선택(fileNum)하면 변하지 않는 변수와 더해서 경로 및 파일명을 입력 시킨다.
  (예시) 05번 파일 선택시 "Nature99(Small)/picture" + fileNum(05) + .jpg

- JavaScript의 Image 함수에 해당 파일을 입력 시킨다.

```javascript
imageObject.onload = function () {
                // 중요! 입력 영상 크기 알아내기
                inH = imageObject.height;
                inW = imageObject.width;
                // 도화기 크기를 이미지 크기로 조절
                inCanvas.height = inH;
                inCanvas.width = inW;
                // 이미지 객체 --> 캔버스(화면)
                inCtx.drawImage(imageObject,0,0,inW,inH);

                // 메모리 할당 (3차원 배열)
                inImage = new Array(3); // 3면
                for(var m=0; m<3; m++) {
                    inImage[m] = new Array(inH);
                    for(let n=0; n<inH; n++)
                        inImage[m][n] = new Array(inW);
                }
```

- 대부분의 사진은 가로, 세로 크기가 다르므로 이미지에서 높이, 너비(imageObject.height, width)를 찾아서 변수에 입력 하여야 한다.
- inCtx.drawImage(입력받은 사진, 시작 x축 좌표, 시작 y축 좌표, 사진 가로, 세로)
- RGB 포멧은 3차원으로 메모리 할당을 하여야 한다.(RGB, 가로, 세로)
```javascript
var colorBlob = inCtx.getImageData(0,0,inW,inH);
                var R, G, B, Alpha;
                for (var i=0; i<inH; i++) {
                    for (var k=0; k<inW; k++) {
                        var pos = (i*inW + k) * 4; // 1픽셀 == 4byte
                        R = colorBlob.data[pos+0];
                        G = colorBlob.data[pos+1];
                        B = colorBlob.data[pos+2];
                        Alpha = colorBlob.data[pos+3];
                        inImage[0][i][k] = R;
                        inImage[1][i][k] = G;
                        inImage[2][i][k] = B;
                    }
                }
```
- colorBlob이라는 변수에 사진의 정보 전체를 입력 시킨다.
- 영상처리를 위해서는 각 점에 대한 정보를 알아야 하므로 RGB 포멧에 맞게 데이타를 추출해서 inImage[rgb][i][k]에 각각 입력 시켜야 한다.
- RGB 데이타는 아래의 그림과 같이 R,G,B, Alpha 순서로 저장되어 있다.
- 따라서 이중 for문 안에서 (i*inW + k) + 0 (i*inW + k) + 1 (i*inW + k) + 2 (i*inW + k) + 3 의 수식으로 R,G,B,Alpha 값을 추출할 수 있다.
![RGBalpha](https://user-images.githubusercontent.com/108249298/199449529-51854997-b8bf-4995-aaf4-9353eab4a0eb.png)

## ㅇ Display Image
```javascript
function displayImage() {
            // 도화기 크기를 이미지 크기로 조절
            outCanvas.height = outH;
            outCanvas.width = outW;

            outPaper= outCtx.createImageData(outW, outH); // 이미지 크기의 빈 종이를 준비
            for (let i=0; i<outH; i++) {
                for (let k=0; k<outW; k++) {
                    let R = outImage[0][i][k];  
                    let G = outImage[1][i][k];  
                    let B = outImage[2][i][k];  
                    outPaper.data[(i*outW + k)*4 + 0] = R; // Red
                    outPaper.data[(i*outW + k)*4 + 1] = G; // Green
                    outPaper.data[(i*outW + k)*4 + 2] = B; // Blue
                    outPaper.data[(i*outW + k)*4 + 3] = 255; // Alpha (투명도)
                }
            }
            outCtx.putImageData(outPaper,0,0);
        }
```

- Raw 포멧에서의 2차원을 RGB를 추가한 3차원으로 변환하여야 한다.


ㅇ equal Image(동일 이미지 출력)  
- 1차원 : RGB / 2차원 : 가로 / 3차원 : 세로
```javascript
function equalImage() { // 동일 영상 알고리즘
            // (중요!) 출력 이미지의 크기가 결정 ---> 알고리즘에 의존...
            outH = inH;
            outW = inW;
            // 출력 영상의 3차원 메모리 할당
            outImage = new Array(3); // 3면
            for(var m=0; m<3; m++) {
                outImage[m] = new Array(outH);
                for(let n=0; n<outH; n++)
                    outImage[m][n] = new Array(outW);
            }
            // **** 진짜 영상처리 알고리즘 *****
            for (var rgb=0; rgb<3; rgb++) {
                for (let i=0; i<inH; i++) {
                    for (let k=0; k<inW; k++) {
                        outImage[rgb][i][k] = inImage[rgb][i][k];
                    }
                }
            }
            // ******************************
            displayImage();
        }
```
> 이후의 각 기능은 나머지는 동일하여 핵심 알고리즘만 설명 하겠다.

## ㅇ function grayImage(그레이 스케일)

```javascript
for (let i=0; i<inH; i++) {
                for (let k=0; k<inW; k++) {
                    let sumValue = inImage[0][i][k]  + inImage[1][i][k] + inImage[2][i][k] ;
                    let avgValue = sumValue / 3;
                    
                    outImage[0][i][k] = avgValue;
                    outImage[1][i][k] = avgValue;
                    outImage[2][i][k] = avgValue;
                }
            }
```

- gray scale은 칼라로 되어 있는 사진을 흑백으로 바꾸는 과정을 의미한다.

- 한 점에서 R,G,B 값을 모두 더한 후 3으로 나눈 값이 그 결과이다.

![grayimageResult](https://user-images.githubusercontent.com/108249298/199450432-126675cd-5fcb-4eb2-ae5c-7e00efb322b5.png)


## ㅇ Event Listener - Mouse

- 사용자의 요구사항에 따라서 S/W 및 소스코드가 변경 되어야 하는 경우가 많다.
- 그 예시로 이번 프로젝트에서는 마우스 입력에 대한 Event Lisener에 대한 코딩을 수행하였다.
- 그 전까지는 사진 전체에 대하여 원하는 효과를 선택 및 처리하여 출력하였으나,
- 사용자가 원하는 영역을 사각형으로 드래그 하여 표시하면 해당 부분에 대해서만 원하는 효과를 적용한다.


## ㅇ mouse 관련 event listener

- event listener : 쉽게 표현하면 특정 이벤트가 이루어지기를 계속 기다렸다가 해당 이벤트에서 특정한 기능(보통은 함수로 선언)을 수행하는 것을 말한다.

> Listener 라는 단어 자체가 '듣는 사람'이므로 사용자(또는 특정 동작)를 바라보며 조건에 맞는 동작이 수행되기를 계속 기다린다. 
마치 레스토랑의 종업원이 홀을 바라보며 손님이 부르기를 기다리는 것과 마찬가지라고 생각하면 될 것이다.

![eventListener](https://user-images.githubusercontent.com/108249298/199450583-00c6fda9-ab81-4b7e-8fb6-46e98226936d.png)


> 여러 종류가 있으나 이번 프로젝트에서는 mousedown, up, move에 대하여만 코딩 하였다.
- mousedown : 마우스 왼쪽버튼 누를 떄
- mouseup : 마우스 왼쪽버튼에서 손을 뗄 때
- mousemove : 마우스를 이동시킬 때(x,y 좌표가 변경될 때)

## ㅇ function onEventListener
- mousedown/up/move에 대한 listener 켜기
```javascript
// 마우스 이벤트 리스너 켜기
            inCanvas.addEventListener("mousedown", __downMouse, false);
            inCanvas.addEventListener("mouseup", __upMouse, false);
            inCanvas.addEventListener("mousemove", __moveMouse, false);
```

## ㅇ function reverseImage_mouse
![ui](https://user-images.githubusercontent.com/108249298/199451019-2d592dce-2423-46d5-a83a-50c4412f457c.png)

- 상기 화면은 본 프로젝트에서 코딩한 S/W의 UI(User Interface, 사용자 입력)이다.
- 마우스로 영역 선택 아래의 '영상반전'을 클릭하면 아래 함수가 실행된다.

![reverseimage](https://user-images.githubusercontent.com/108249298/199451226-39b7d538-e517-40fc-9283-8b9861369fa3.png)


- EventListener의 mousedown/up/move를 모두 실행한다.
- function __downMouse : 사용자가 마우스 왼쪽 버튼을 클릭 하였을 때 실행
    a. 마우스의 x,y좌표를 변수 startX,Y에 각각 입력 받는다.
    b. pressYN 변수를 true로 변경
    c. 현재 상태를 imageData에 입력

- function __upMouse : 사용자가 마우스 왼쪽버튼을 땔 때 실행
```javascript
 function __upMouse(event) {
                inCtx.putImageData(imageData,0,0);
                endX = event.offsetX;
                endY = event.offsetY;
                // 선택한 네모 박스 안쪽만 영상처리 되기
                // 시작과 끝을 재배치
                if (startX > endX) {
                    let tmp = startX;
                    startX = endX;
                    endX = tmp;
                }
                if (startY > endY) {
                    let tmp = startY;
                    startY = endY;
                    endY = tmp;
                }

                // 마우스 이벤트 리스터 끄기
                inCanvas.removeEventListener("mousedown", __downMouse, false);
                inCanvas.removeEventListener("mouseup", __upMouse, false);
                inCanvas.removeEventListener("mousemove", __moveMouse, false);

                pressYN = false;

                __reverseImage();                
            }
```

- 마우스의 x,y좌표를 변수 endX,Y에 각각 입력 받는다.
- startXY, endXY 값을 재배치 한다.(코딩 기법 중에 하나)
사용자가 좌상단 --> 우하단 또는 우하단 --> 좌상단 등 어느 순서로 mousedown/up 하여도 좌상단 --> 우하단 순서로 클릭 한 것처럼 재배치 한다. 그래야 (endX-startX) , (endY-startY) 두 값이 모두 양수가 된다.

- 마우스 왼쪽버튼을 떼면 이후에는 EventLister를 remove하여 더이상 사진을 클릭하여도 반응이 없게 한다.
(요구사항에 따라서 영역 선택을 여러번 할 수도 있으나, 본 프로젝트에서는 1번의 입력만 있는 것으로 간주)
- 이후에 reverseImage 함수 실행(startXY ~ endXY) 범위에서만 reverseImage가 실행된다.

아래 PPT는 좌측 원본 영상에서 빨간색 네모 부분에 대해서 revese 처리를 수행한 결과이다.
![eventlistenerResult](https://user-images.githubusercontent.com/108249298/199451533-208431ae-3dd5-4db2-8fc5-e96bec259992.png)

- function __moveMouse
```javascript
 function __moveMouse(event) {
                if (!pressYN)
                    return;

                inCtx.putImageData(imageData,0,0);

                endX = event.offsetX;
                endY = event.offsetY;
                
                inCtx.beginPath(); // 선그리기 시작
                inCtx.strokeStyle = 'blue';
                inCtx.lineWidth = 1;

                inCtx.rect(startX, startY, (endX-startX), (endY-startY));

                inCtx.stroke();
                inCtx.closePath(); // 선그리기 끝

            }
```

a. 사용자가 선택하고 있는 영역을 시각적으로 보여주기 위해서 마우스 시작점 ~ 끝점 까지 사각형을 그린다.(러버 밴드)


#### ㅇ function __reverseImage : 사용자가 지정한 네모 박스 안쪽만 reverseImage 수행
![code of reverseImage](https://user-images.githubusercontent.com/108249298/199452523-adbed500-16fe-41ea-9a78-6d610e394290.png)

## ㅇ 이미지 색상 추출 및 변경
![rgbHSV](https://user-images.githubusercontent.com/108249298/199452605-ee23b834-70b3-47c4-81bb-3506ed3bd6ac.png)

- 상기 PPT는 RGB, HSV에 대한 설명이다.
- 주로 색을 추출하기 위한 코딩을 수행하려고 하는데, RGB로는 코딩이 어려워지고 한계가 있다고 한다.
(실제로 코딩을 해보지는 못하였다)
- 따라서 RGB --> HSV 변경 후 이미지 색 추출 등 원하는 알고리즘을 수행한다.
- 그 이후에 JPG파일의 포멧에 맞게 다시 RGB로 변환하여 화면에 출력하게 된다.
- 아래는 교수님께서 작성하신 RGB, HSV 간 변환 함수이다.
(수학적인 공식을 코딩으로 나타낸 것이다. 이해 보다는 함수의 사용에 초점을 맞추었다)
```javascript
 function rgb2hsv(r, g, b) {
            var max = Math.max(r, g, b), min = Math.min(r, g, b),
                d = max - min,
                h,
                s = (max === 0 ? 0 : d / max),
                v = max / 255;

            switch (max) {
                case min: h = 0; break;
                case r: h = (g - b) + d * (g < b ? 6: 0); h /= 6 * d; break;
                case g: h = (b - r) + d * 2; h /= 6 * d; break;
                case b: h = (r - g) + d * 4; h /= 6 * d; break;
            }
            return {
                h: h,    s: s,    v: v
            };
        }

        function hsv2rgb(h, s, v) {
            var r, g, b, i, f, p, q, t;

            h = h*360;  s = s*100;    v = v*100;

            h = Math.max(0, Math.min(360, h));
            s = Math.max(0, Math.min(100, s));
            v = Math.max(0, Math.min(100, v));
            
            h /= 360;   s /= 100;     v /= 100;

            i = Math.floor(h * 6);
            f = h * 6 - i;
            p = v * (1 - s);
            q = v * (1 - f * s);
            t = v * (1 - (1 - f) * s);
            switch (i % 6) {
                case 0: r = v, g = t, b = p; break;
                case 1: r = q, g = v, b = p; break;
                case 2: r = p, g = v, b = t; break;
                case 3: r = p, g = q, b = v; break;
                case 4: r = t, g = p, b = v; break;
                case 5: r = v, g = p, b = q; break;
            }
            return {
                r: Math.round(r * 255),
                g: Math.round(g * 255),
                b: Math.round(b * 255)
            };
        }
```


## ㅇ function satur_Image : 채도(saturation) 변경
```javascript
 let s_value = parseFloat(prompt("숫자 입력(0~1)", "-0.2"));
                for (let i=0; i<inH; i++) {
                    for (let k=0; k<inW; k++) {
                        let R = inImage[0][i][k];
                        let G = inImage[1][i][k];
                        let B = inImage[2][i][k];

                        // RGB --> HSV
                        let hsv = rgb2hsv(R,G,B);  // {h : 0~360, s : 0 ~ 1.0, v : 0 ~ 1.0}
                        let H = hsv.h;
                        let S = hsv.s;
                        let V = hsv.v;
                        // 채도를 변경하자
                        S = S + s_value;
                        // HSV --> RGB
                        let rgb = hsv2rgb(H,S,V);
                        R = rgb.r;
                        G = rgb.g;
                        B = rgb.b;

                        // 출력 영상에 넣기
                        outImage[0][i][k] = R;
                        outImage[1][i][k] = G;
                        outImage[2][i][k] = B;
                    }
                }            

```

- RGB, HSV 변환 함수를 통해서 각 점에 대한 H, S, V 값을 알 수 있게 되고 본 코딩에서는 채도 값을 변경하였다.(채도 -0.2)
![saturImageResult](https://user-images.githubusercontent.com/108249298/199452869-2d505dc8-3e58-4c45-b712-3a1f6d76024e.png)

## ㅇ function orange_Image : 원하는 색 추출

> 코딩 학습시 아래 사진에서 오렌지 색을 찾는 연습을 하였고 기억의 편의를 위해서 함수명은 변경하지 않음
![orangeImageBefore](https://user-images.githubusercontent.com/108249298/199452960-5be3a31c-2ecd-49eb-a14f-d176540c35d9.png)

```javascript
for (let i=0; i<inH; i++) {
                for (let k=0; k<inW; k++) { 
                    let R = inImage[0][i][k];
                    let G = inImage[1][i][k];
                    let B = inImage[2][i][k];

                    // RGB --> HSV
                    let hsv = rgb2hsv(R,G,B);  // {h : 0~360, s : 0 ~ 1.0, v : 0 ~ 1.0}
                    let H = hsv.h;
                    let S = hsv.s;
                    let V = hsv.v;

                    // H 값에 따른 범위를 추출. 예시) 오렌지 : h 범위 8 ~ 30 (대략 그렇게 나옴)
                    // 오렌지 제외 나머지는 gray scale 처리
                        if (col1 <= (H*360) && (H*360) <=col2) {           // h 범위가 0~1.0 으로 나와서
                            outImage[0][i][k] = R;
                            outImage[1][i][k] = G;
                            outImage[2][i][k] = B;
                        } else {   // 나머지는 그레이 스케일
                            let avg = parseInt((R+G+B)/3);
                            outImage[0][i][k] = avg;
                            outImage[1][i][k] = avg;
                            outImage[2][i][k] = avg;
                        }
                    }
                }
```
- rgb2hsv에서 생성된 H 값은 0~1의 범위 이므로 0~360으로 표현되어 있는 HSV 색상표를 사용하기 위해서 (H*360)으로 설정 하였다.

- 아래의 블로그는 RGB, HSV 색상 코드표 이다.
[RGB, HSV 색상코드표](https://myyac.tistory.com/133)

- 사용자가 입력한 두 값(col1, col2)에 해당하는 색은 RGB로 그 외는 그레이 스케일로 표시하였다.
- 아래의 결과는 노란색 꽃만 표현하고자 하였다.
![extractUI](https://user-images.githubusercontent.com/108249298/199453207-a38b5c8a-240f-42da-a73b-2a4d2c7385d1.png)

![resultOfExtractImage](https://user-images.githubusercontent.com/108249298/199453306-b855cba8-fd5d-41c4-b852-0880925ce8a6.png)


## ㅇ 이미지 영상처리 실제 활용 예시
- 아래 그림의 AI 로봇 처럼..... 이미지 영상처리를 실제에서 어떻게 활용 할 수 있을지 잠시 고민해본 결과이다.
![robotAI](https://user-images.githubusercontent.com/108249298/199453411-436dca2a-c29d-44b4-87ac-a423c51c450c.png)

- 아래는 내가 가끔 심심풀이로 하는 스마트폰 게임이다.
![dreamBlastGame](https://user-images.githubusercontent.com/108249298/199453505-496a5563-edf9-47d9-9514-00a0df3d1ddf.png)


- 같은 색의 블록을 터치하면 아이템이 생기고 그 아이템을 활용하여 정해진 턴 이내에 블럭 깨기 등의 미션을 해결하는 게임이다.
- 이미지 프로세싱을 코딩하며 이 게임을 자동으로 하는 S/W를 개발하고 싶었다.
- 내가 하고자 하는 개발 순서이다.
>1. 게임 프로세스 이해(기 완료)
>2. 같은 색의 칼라 블록 구분 하기(본 프로젝트로 완료)
>3. AI를 활용하여 가장 효율적으로 게임을 진행하도록 S/W 개발
>4. 스마트폰에 해당 S/W 설치 및 구동
>  (3, 4번은 추후 과제로 남겨두었고 2번의 칼라 블록 구분한 결과이다.

![exampleOfGame](https://user-images.githubusercontent.com/108249298/199453640-772c7500-2f34-4a47-b170-227697b585cf.png)


- 실제 게임화면을 입력 받고, 사용자가 원하는 색 블록에 해당하는 버튼을 누르면 오른쪽의 결과와 같이 해당 블록이 구분되어 시현되도록 하였다.


## ㅇ 결론 및 추후 과제
![Conclustion](https://user-images.githubusercontent.com/108249298/199453697-b5907c40-c130-4390-b16d-4890cb370147.png)


- 현재는 RAW, Color 사진에 대하여 일부 기능만 코딩하였다.

- 9월 4주 부터 배우게 될 JSP를 활용하여 본 S/W를 서버에 올리고 클라이언트(PC)에서 실행하여 결과를 확인

- 이후 사용자 UI 및 스마트폰 연동 기능 개발을 진행할 예정이다.


## ㅇ JavaScript 수업 수강을 마치며
- 처음에는 JavaScript가 무엇인지도, 단 한줄도 코딩할 수 없었다.
- 우재남 교수님의 수업을 들으며 '영상처리'라는 실전과 함께 JavaScript, HTML5에 대하여 코딩하였다.
- 실제 눈으로 보이는 결과를 가지고 학습하는 과정이 상당히 흥미로웠고 여러가지 기능 및 결과를 얻을 수 있었다.
- 하지만 실제 개발자로 업무를 하기 위해서는 아직은 많은 노력과 시간이 필요하다고 생각한다.
- 지금 학습한 내용이 JavaScript 뿐만이 아니라 프로그래밍 언어 전반에도 응용하여 활용 할 수 있도록 꾸준히 학습 및 코딩에 도전할 예정이다.
