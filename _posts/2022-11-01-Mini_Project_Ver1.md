# ㅇ 교육과정 

- 기 간 : '22. 8. 17.(수) ~ 12.30.(금)
- 기 관 : 대한상공회의소 서울기술교육센터
- 교육명 : AI활용 Big Data 시스템 개발자

# ㅇ 교육내용 : JavaScript(Html 5 기반) 

# ㅇ Project : Mini Project(Ver 1.0)

- 언어 : JavaScipt
- 환경 : Web(Chrome에 최적화)
- 내용 : Digital Image Processing Using JavaScript
- 지도교수 : 우재남

  상기 내용은 본 포스팅의 개요이다.
  대한상공회의소 서울기술교육센터에서 'AI 활용 Big Data 시스템 개발자' 과정을 수강하면서 배운 내용이다.
  JavaScript를 활용해서 Web에 'PhotoShop' 또는 스마트폰 APP 중에서 사진 편집 하는 기능을 구현하였다.
  아래부터는 작성한 PPT와 그림 및 코드 위주로 기록하여 추후에 비슷한 코딩시 참고 하고자 한다.

# ㅇ 제목 : Digital Image Processing Using JavaScript

![01-ppt01](https://user-images.githubusercontent.com/108249298/199362667-369e2e2b-03de-49b0-9f62-75ddc6bf495a.png)

> 영상처리를 JavaScript로 구현한 사례는 찾아보기 힘들다. 내가 가르친 학생들 외에는...(우재남 교수 曰)

- 처음에 문법 부터 시작해서 * 그리기, 구구단....으로 연상되는 일련의 코딩 학습 과정이 있다.
- 하지만 우재남 교수님의 강의는 달랐다. 처음에 간단한 문법은 당연히 배워야 하고 그 이후에는 영상처리의 각 코드를 기반으로 하여 수업을 하였고, 그 과정이 나는 좋았다.
- 예전(약 15년 전) 대학생때 배운 C언어는 구구단, 배열 이후 '포인터'를 배우다가 힘겨워 했던 기억이 났다.

# ㅇ 목차 : 소개, 알고리즘, 추후계획

![ppt contents](https://user-images.githubusercontent.com/108249298/199422608-3ea0f8bb-af5e-420c-8e28-6d19b6ff452b.png)

- Simple is Best. 목차는 군더더기 없이 간단히 구성하였다.
- 
  (지금 보니 구글에서 찾은 이 템플릿 꽤 마음에 든다.)

# ㅇ Introduce of Digital Image Processing

![Introduce of Digital Image Processing](https://user-images.githubusercontent.com/108249298/199424231-0d9e3d7f-8d0f-4e3e-8e0b-c8a310aee196.png)

- 우리가 일상에서 접하는 모든 사진, 영상은 (당연히) Analog 이다.
  (Analog, Digital 차이점은 언급하지 않겠다. 혹시 헷갈리는 분들은 Google 께서 친절히 답변해 주실거다.)

- 이번 코딩에서는 .RAW의 사진을 기반으로 작성하였다.
- Analog인 영상을 Digital로 변환하여 PC로 입력 받으면 PPT 4/15 우측의 그림과 같이 인식을 하게 된다.
- 사진의 포멧 및 크기에 따라 달라지지만 이번 코딩에서는 가로/세로 각각 256, 512 pixel을 기준으로 하였다.
  (다른 크기도 가능하지만 512 이상의 크기에서는 검증하지 않았다. 추후 color 사진 코딩시에 1024 이상의 사진 및 가로/세로 크기가 다른 사진에 대해서 코딩 및 확인 예정이다.)
- 사진의 좌측 상단이 (0,0)의 좌표이며 가로 512, 세로 512 각각의 좌표에 따라서 0~255의 값을 가지게 된다.
- 각각의 좌표에 따른 값을 필요한 영상처리 효과에 따라 각기 다른 Algorithm을 적용하여 DIgital로 처리한다.

# ㅇ Why Using Web & JavaScript

![why using web and javascript](https://user-images.githubusercontent.com/108249298/199424366-d71c6818-71e7-4145-a1c2-56fcf672e06f.png)


- 기존(As is)에는 Photoshop으로 대표되는 각종 S/W를 활용하여 사진 편집을 하였다. 하지만 여러가지 단점이 존재한다. 사진의 편집을 위해서 S/W를 구입, 설치가 필요하고 일정 수준 이상의 S/W 사용을 위해서는 당연히 비용의 지출도 필요하였다.(생각보다 비싸게 느껴진다)

- 따라서 모든 사람들이 사용할 수 없고 일부 제한된 사용자들만 S/W를 구매하여 활용하는 것이 현실이다.(일반 USER들은 그림판 등의 무료 S/W를 사용한다.)

- 요즘의 추세는 모든 것이 Web에서 이루어 진다. PC 앞에 앉으면 Chrome 등의 Web 브라우저를 켜는 것으로 시작 하는 것이 너무나도 익숙하다. 이러한 모든 사용자들을 대상으로 한 S/W의 필요성이 대두되고 있다.

- PhotoShop 등의 S/W와 유사한 기능을 Web 기반에서 수행하기 위한 코딩이 필요하고 그에 가장 적합한 언어는 JavaScript이다.

- HTML5와 JavaScript를 활용하면 Web에서도 이미지, 영상의 처리가 가능하며 Chrome(또는 Edge)로 누구나 사용할 수 있는 장점이 있다.

- 아래는 본 코딩를 그림으로 나타낸 구조도 이다. 구조도에 해당하는 소스코드는 아래에 자세히 설명 하겠다.


![코딩구조도](https://user-images.githubusercontent.com/108249298/199424575-512aae7f-9862-43a2-887d-eff892ab9609.png)

# ㅇ function openImage

1. infile 기능을 통하여 raw 파일을 PC의 메모리로 읽어들이기
2. 이미지의 크기를 확인(raw 파일은 한 pixel이 1 byte 이므로 file size의 루트값이 사진의 크기가 된다.
![사진의 크기](https://user-images.githubusercontent.com/108249298/199425439-ec80be00-5769-4c2f-89a1-5749efb92a09.png)



3. 사진 크기 만큼의 메모리를 확보한다.(inH, inW)
4. blob이라는 변수에 사진의 모든 정보를 한번에 가져온다.
5. blob을 inW, inH의 각 배열(사진의 한 점에 해당)에 입력 하기 위해서 이중 for 문을 활용하여 한 점씩 뽑아서 입력 시킨다.
6. inCanvas라는 변수 이름으로 도화지를 준비한다.
7. JavaScript에서는 변수(inH, inW)에 입력되어 있는 사진의 정보를 Canvas에 바로 입력 할 수 없다. 따라서 종이 하나(inPaper)를 준비해서 그 종이에 inH,inW의 정보를 한 점씩 찍은 다음에 inPaper를 Canvas에 붙이는 방식을 사용한다.
> 추후에 JavaScript가 발전하면 해당 기능이 개선되지 않을까 조심스럽게 생각해본다.


```javascript
function openImage() {
            inFile = document.getElementById("inFile").files[0]; // 선택한 RAW 파일(LENNA512.RAW)
            // (중요!) 선택한 이미지의 크기를 확인
            inH = inW = Math.sqrt(inFile.size); // 128, 256, 512, 1024.....
            // 이미지 크기의 메모리(2차원배열)를 확보
            inImage = new Array(inH);
            for (let i = 0; i < inH; i++)
                inImage[i] = new Array(inW);
            // 파일  --> 메모리
            let reader = new FileReader();
            reader.readAsBinaryString(inFile);
            reader.onload = function () {
                let blob = reader.result; // 파일을 한 덩어리(blob)으로 가져옴.
                // 덩어리(blob)에서 한점한점 뽑아서, 배열에 넣기... 몇번 반복? 512x512
                for (let i = 0; i < inH; i++) {
                    for (let k = 0; k < inW; k++) {
                        let sPixel = (i * inH + k); // 시작 위치
                        let ePixel = (i * inH + k) + 1; // 끝 위치
                        inImage[i][k] = blob.slice(sPixel, ePixel).charCodeAt(0); // 0~1까지 뽑아라. 0만 뽑힘.  //'뙓' -->  223
                    }
                }
                // 도화기 크기를 이미지 크기로 조절
                inCanvas.height = inH;
                inCanvas.width = inW;
                //** 입력 메모리(inImage)를 페이퍼에 콕콕 찍어서 출력한 후,  페이퍼를 캔버스에 떡 붙이기.
                inPaper = inCtx.createImageData(inH, inW); // 이미지 크기의 빈 종이를 준비
                for (let i = 0; i < inH; i++) {
                    for (let k = 0; k < inW; k++) {
                        let px = inImage[i][k];
                        inPaper.data[(i * inH + k) * 4 + 0] = px; // Red
                        inPaper.data[(i * inH + k) * 4 + 1] = px; // Green
                        inPaper.data[(i * inH + k) * 4 + 2] = px; // Blue
                        inPaper.data[(i * inH + k) * 4 + 3] = 255; // Alpha (투명도)
                    }
                }
                inCtx.putImageData(inPaper, 0, 0);
            }
        }
```

## ㅇ function displayImage : Canvas에 사진을 출력하기 위한 함수

1. Canvas를 출력이미지의 크기로 설정(outCanvas)
2. 이미지 크기의 빈 종이(outPaper)에 outImage[][]에 저장되어 있는 사진의 값을 한 점씩 출력

```javascript
function displayImage() {
            // 도화기 크기를 이미지 크기로 조절
            outCanvas.height = outH;
            outCanvas.width = outW;

            outPaper = outCtx.createImageData(outH, outW); // 이미지 크기의 빈 종이를 준비
            for (let i = 0; i < outH; i++) {
                for (let k = 0; k < outW; k++) {
                    let px = outImage[i][k];
                    outPaper.data[(i * outH + k) * 4 + 0] = px; // Red
                    outPaper.data[(i * outH + k) * 4 + 1] = px; // Green
                    outPaper.data[(i * outH + k) * 4 + 2] = px; // Blue
                    outPaper.data[(i * outH + k) * 4 + 3] = 255; // Alpha (투명도)
                }
            }
            outCtx.putImageData(outPaper, 0, 0);
        }
```

## ㅇ 동일 영상 시현(equalImage)

```javascript
function equalImage() { // 동일 영상 알고리즘
            // (중요!) 출력 이미지의 크기가 결정 ---> 알고리즘에 의존...
            outH = inH;
            outW = inW;
            // 출력 영상의 2차원 메모리 할당
            outImage = new Array(outH);
            for (let i = 0; i < outH; i++)
                outImage[i] = new Array(outW);
            // **** 진짜 영상처리 알고리즘 *****
            for (let i = 0; i < inH; i++) {
                for (let k = 0; k < inW; k++) {
                    outImage[i][k] = inImage[i][k];
                }
            }
            // ******************************
            displayImage();
        }
```

1. 출력 이미지의 크기를 설정(outH, outW)
2. 출력 영상(outImage)에 해당하는 2차원의 메모리 할당
3. 이중 for문을 활용하여 outIMage를 출력
4. 동일 영상이므로 outImage = inImage
5. 이후에는 영상처리 기법에 따라 아래의 ****진짜 영상처리 알고리즘**** 에 해당하는 코딩만 변경된다.
(아래 부터는 각 코드와 이에 해당하는 알고리즘 위주로 서술 하겠다.)

[Youtube 영상](https://www.youtube.com/watch?v=BVN6mdfI8Qk)

# ㅇ 영상처리 알고리즘
- 영상처리 알고리즘은 아래의 PPT에서 설명한 것과 같이 크게 4가지 종류로 나누고 있다.
- 본 프로젝트에서는 코딩의 난이도를 고려하여 프레임 처리를 제외한 3가지의 영상처리 기법을 구현 하였다.
  (프레임 처리는 추후에 코딩 실력 발전에 따라서 구현을 도전할 계획이다.)
   ![영상처리 알고리즘](https://user-images.githubusercontent.com/108249298/199425678-12c5928f-45c5-407f-890c-9a7142ef89cf.png)


# ㅇ 화소점 처리(1)
   ![화소점처리](https://user-images.githubusercontent.com/108249298/199425748-8c28cddd-60ff-499c-997d-15a5694e3b33.png)


### ㅇ 영상 반전(reverse Image)
- 최대 음영(255)에서 사진의 각 점의 값을 빼면 오른쪽의 예시와 같이 표현 된다
   (밝은 곳은 어둡게, 어두운 곳은 밝게)

```javascript
 for (let i = 0; i < inH; i++) {
                for (let k = 0; k < inW; k++) {
                    outImage[i][k] = 255 - inImage[i][k];
                }
            }
```

##ㅇ 화소점 처리(2)

![평활화](https://user-images.githubusercontent.com/108249298/199426444-565382bc-8693-4623-b3e0-368565afef07.png)

### 화소점 처리의 기본 개념
1. 히스토그램(Histogram) : 명도에 따른 빈도수를 그래프로 표현
![히스토그램1](https://user-images.githubusercontent.com/108249298/199426520-bc2c3c10-5e61-4c58-a9ad-d9d9aee0fe19.png)

![histogram2](https://user-images.githubusercontent.com/108249298/199426606-a9c10161-322c-4fa8-a494-40910a92f9e0.png)

### stretching : 명암대비가 낮은 영상의 품질 향상

1. 입력 영상의 최저, 최고 명도값을 구한 후 아래 공식에 대입하여 영상 출력

2. 영상처리를 위한 여러가지 공식이 있음. 해당 공식은 과학자들이 여러 연구를 통하여 도출한 결과이다.
(해당 공식에 대한 연구/분석은 하지 않고 영상처리를 위하여 활용하였다.)
3. 위의 히스토그램에서 (c)의 히스토그램을 (d)로 변환하는 알고리즘 이다.

![stretching fomula](https://user-images.githubusercontent.com/108249298/199426720-a9efccd1-cd5d-4e62-89ae-45c00c694c10.png)


### 평활화 
 - 어둡게 촬영된 영상의 히스토그램을 조절하여 명암분포가 빈약한 영상을 균일하게 처리

1. 아래의 3단계(명암 빈도수 → 각 명암갑의 누적합 → 누적 빈도수의 정규화)의 공식을 수행

![img](https://blogfiles.pstatic.net/MjAyMjA5MTZfNiAg/MDAxNjYzMzE2MDUzNDYw.-6Uqo_0nl-eZCuKUg2PrvSKKKM87n1AIyDugEQRZ1twg.4JEvbNinLFwPolhlg1gwNglaV6zQIrchYEnU2FcPMnMg.PNG.hkpyh/image.png?type=w1)

평활화 각 단계별 설명 및 공식

2. (a)의 원본영상은 사진의 명암이 가운데에 치우쳐저 있으나,
3. 평활화 과정을 통하여 전체 명암범위(0~255)로 균일하게 영상 표현 가능
![평활화1](https://user-images.githubusercontent.com/108249298/199426824-c565dec6-4321-4343-afd9-22b72f4ce813.png)


#ㅇ 기하학 처리

![기하학처리1](https://user-images.githubusercontent.com/108249298/199426935-6ea692b1-21b0-4831-80c6-78cb9bf106f7.png)


- 사진의 축소 : 출력영상(outImage)은 사용자가 입력한 배율(변수 : scale)에 따라서 입력영상 각 점의 일부만 가져와서 출력

'''javascript
for (let i = 0; i < inH; i++) {
                for (let k = 0; k < inH; k++) {
                    outImage[parseInt(i / scale)][parseInt(k / scale)] = inImage[i][k];
                }
            }
'''


# ㅇ 영역 처리
 - 화소점 처리는 원본 사진의 값은 변하지 않고 해당 값의 x,y 좌표가 변하는 방식이다.
- 하지만, 영역처리는 화소의 값과 그 주위의 화소값도 함께 고려하여 영상을 처리하는 방식이다.

![곱의합](https://user-images.githubusercontent.com/108249298/199427228-be6d27ae-3be3-4bff-9e8b-d8aa2ee211f6.png)

> 입력 영상(inImage)에 가중치를 곱한 합을 출력(outImage)

![영역처리 알고리즘 모식도](https://user-images.githubusercontent.com/108249298/199427313-1ae3bec7-2d3f-4a54-9446-a6061b1dc5e0.png)

영역처리 알고리즘의 모식도

- 입력영상에 각 영역처리 방법에 따른 마스크(mask)를 씌워서 각 좌표의 곱의 합으로 출력 영상을 구현한다.

- 마스크(mask)는 보통 3x3의 배열로 구성되며 알고리즘에 따라서 5x5 또는 그 이상의 배열이 사용될 수 있다.
![ppt_blur](https://user-images.githubusercontent.com/108249298/199427502-76550fb9-9446-479d-9487-7192d21e0196.png)


- 좌측은 3x3 배열, 우측은 5x5 배열의 mask를 활용한 블러링(blurring) 알고리즘 이다.
![blurring mask](https://user-images.githubusercontent.com/108249298/199427629-9545398a-41f5-4aa9-8a13-9bf6eae652ff.png)

블러링(blurring) 3x3 , 5x5 mask
![code of mask](https://user-images.githubusercontent.com/108249298/199427701-2814be69-349c-411b-9cb2-365d8f607a1b.png)

- 1번 : blurring 3x3 마스크

- 2번 : inH,inW는 입력받은 영상보다 2가 커야 한다.

- 원본 영상 (0,0) 좌표에 3x3 mask 처리를 할 때 아래의 그림과 같이 2x2 크기는 원본영상의 범위에서 벗어나게 된다. 
- 따라서 mask 처리를 위한 알고리즘에서는 원본영상은 기존보다 2 크게 설정 되어야 한다.
(5x5 mask의 경우 마찬가지의 원리로 4 크게 설정 필요)

![네모칸](https://user-images.githubusercontent.com/108249298/199427784-d744836b-8734-46d4-b7d5-8a296b3e581f.png)

- 곱의 합을 구현하는 코드는 아래와 같다.



![img](https://blogfiles.pstatic.net/MjAyMjA5MTZfMTAg/MDAxNjYzMzE4NzcwODAw.bqVlc2eB-R7w-dT_QNwvT1J4EVHouYf07AwZM9m-55Ug.puxJnO6sOWxvVnnlhcY6Um-fKNGmth9BSif9jcmaEqEg.PNG.hkpyh/image.png?type=w1)


![img](https://blogfiles.pstatic.net/MjAyMjA5MTZfNTYg/MDAxNjYzMzE3NTE3MTQw.K4xMsHhB31ksw06CT26rLRIXM6-cxSoF1XV6y6jtb6Ag.SpYp0yBWTTjNo8Sg7lNBtLWf8iUmQwfFzQ9bpQFlcSgg.PNG.hkpyh/image.png?type=w1)


(ppt 12/15) Example of Digital Image Processing - 영역 처리[2](edge 검출)

- 아래는 주요 알고리즘에 따른 mask 이다.

![img](https://blogfiles.pstatic.net/MjAyMjA5MTZfMTg4/MDAxNjYzMzE5MzkyMzMw.4-X8F-RR6xew84lM9TuHD2rgVJi7cmT6wJN7QLfmzTgg.5nJM2sZW_LaZCXn_5i4BUaq9TzqpB0EAZegIPA1y1bUg.PNG.hkpyh/image.png?type=w1)

# ㅇ Future Plan

![img](https://blogfiles.pstatic.net/MjAyMjA5MTZfNjUg/MDAxNjYzMzE5NDg0NTAy.HB2z1Wfm_72Y4Uuug_309mlXz86R2bffiOwP7GU_gQsg.l2h8oNamKoCrwu3hH6znaA5BYTWVj8Cp-IEGJI-zocUg.PNG.hkpyh/image.png?type=w1)

(ppt 14/15) Future Plan of Digital Image Processing

- 현재는 JavaScript 환경 구성 및 흑백 중에서도 raw 포멧의 영상에 대한 코딩만 완료 하였다.
- '22년 9월에는 칼라 영상의 구조에 대한 학습을 통해서 jpg, png 등의 다양한 포멧에 대하여 진행 할 것이다.
- 동영상은(음성 제외, 영상만) 칼라(또는 흑백) 사진을 1초당 수십장(또는 그 이상) 빠르게 보여지는 것이므로 칼라 영상 이후에 지속적인 학습을 통해서 구현 할 것이다.
- 최종 목표는 Web에 구현 및 상용화를 통하여 이익을 추구하는 것이다.


![img](https://blogfiles.pstatic.net/MjAyMjA5MTZfMjY3/MDAxNjYzMzE5ODg4MjE1.gKuwj_WEaKLdyuK98Lojg3L8mJ5UNuuzrP8C_hADqn8g.6ayInQ93ExrJx6ntc_SvJdCpSosW_wSYNlrkKNNi_wQg.PNG.hkpyh/image.png?type=w1)

(ppt 15/15) 최종적인 목표

# ㅇ (번외) web 시안
- 상단에 'JavaScript 활용한 영상처리 프로그램' 제목 입력
- 좌측에 제작자, 파일 선택, 영상처리 방법 선택 창 시현
- 가운데에 영상처리 전/후 비교 사진
- 사용자 설명서
>  1. 영상처리할 파일 선택(파일 선택 버튼 우측에 선택한 파일명 시현0
> 2. 좌측 아래에서 원하는 처리 방법 선택
> 3. 영상처리 전/후 비교를 통해서 원하는 영상처리 효과 확인


![img](https://blogfiles.pstatic.net/MjAyMjA5MTZfMiAg/MDAxNjYzMzIwMDg4NjQ2.bXr5AxGEeIrQjQKTJgAbR1ZrU1vNmbI2uGstP6V9_M0g.9qKC4hiy8yk9J8NVm5twLIGJyGpAu0rdrU_6GyqlBS0g.PNG.hkpyh/image.png?type=w1)


![img](https://blogfiles.pstatic.net/MjAyMjA5MTZfMTA5/MDAxNjYzMzIwMTExOTg2.-wY8ddrgz2oNOzihyWCDHjstIRZeNLqxI4Z9JDZ5kkAg.22aDBkl48yXJRS7abrXYb0a-73Xoz-XrDntlOZ5afMQg.PNG.hkpyh/image.png?type=w1)


# ㅇ 결 론
 - 본 포스팅의 처음에 언급한 것 처럼 일반사용자들은 영상처리를 위해서 기존에 S/W를 설치하던 방식에서 web에서 바로 작업 및 결과 확인 하는 것을 선호하는 방향으로 변하고 있다.
- 따라서 Web에서 HTML5 및 JavaScript를 활용하여 PC의 'PhotoShop(사진)' & 'Premiere Pro(영상)'과 같은 기능을 구현 및 서비스하는 것이 최종 목표이다.
