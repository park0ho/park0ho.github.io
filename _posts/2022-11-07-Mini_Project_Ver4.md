[요약지](https://github.com/park0ho/park0ho.github.io/blob/7bb81e83a95ba4f6a292f7e8d36d2c123fbc139b/docs/%5B%EC%9A%94%EC%95%BD%EC%A7%80%5D%20%EB%AF%B8%EB%8B%88%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8_Ver4_(%EB%B0%95%EC%98%81%ED%98%B8).pdf)

[보고서](https://github.com/park0ho/park0ho.github.io/blob/7bb81e83a95ba4f6a292f7e8d36d2c123fbc139b/docs/Mini%20Project%20Ver4.0.pdf)

## ㅇ 교육과정
- 기 간 : '22. 8. 17.(수) ~ 12.30.(금)
- 기 관 : 대한상공회의소 서울기술교육센터
- 교육명 : AI활용 Big Data 시스템 개발자

## ㅇ 교육내용 : JAVA

## ㅇ Project : Mini Project(Ver 4.0)
- 언 어 : JAVA
- 환 경 : Windows PC
- 내 용 : 사진가게(PhotoShop) & Game(Dream Blast) Helper Using JAVA
- 지도교수 : 장영완
- 개발기간 : '22. 10. 7일 ~ 20일 [14일간 / 약 50 hour]

## ㅇ Mini Project 4.0에 대한 포스팅을 시작 하며...
- 휴..... 한숨을 먼저 쉬어야 한다.
- 약 보름의 기간동안 평일에는 수업 전후로 두세시간 그리고 주말에는 거의 하루를 반납하며 코딩 하였다.
- "Hello JAVA"만 쓸 수 있던 나에게 미니 프로젝트는 정말 커다란 산처럼 보였다.
- 하지만 하나씩 문제를 해결해가면서 가끔은 코딩이 재밌다고 느낄때고 있었고, 약간의 희열을 느낄때도 있었다.
- 아래 부터는 의식의 흐름대로, 생각나는대로 포스팅을 하겠다.

## ㅇ 주제 선정 이유
[노마드코더](https://www.youtube.com/c/%EB%85%B8%EB%A7%88%EB%93%9C%EC%BD%94%EB%8D%94NomadCoders)
- 가끔 보는 유투브 이다. 코딩 전반적인 내용과 프로그래밍 언어 등에 대해서 나름 쉽게 설명하고 있다.
- 여기서 본 영상 중에 새로운 언어를 배울때 가장 좋은 방법을 소개한 것이 있다.
- 우리가 영어를 배울 때 처음부터 소설을 쓴 적이 있던가?
- '안녕하세요' 는 'Hi' 또는 'Hello~' 입니다. 이게 아마 영어를 배울때의 첫 모습일 것이다.
- 내가 지금까지 유일하게(대학교때 잠깐 맛보고 도망쳤던 C언어는 뒤로 하고..) 배우고 아주 조금이라도 할 수 있는 언어는 JavaScript 이다.
- JavaScript로 Mini Project 1~3을 진행하였다.(이전 포스팅 참고)
- 수준이 높지는 않지만 나름 열심히 코딩하고 교수님께서 알려주신 코드를 최대한 이해하려고 노력하였다.
- Java Mini Project라는 큰 산을 마주 하고 나서 어떤 주제로 해야 하나 많은 고민을 하였다가 최종적으로 선택한 것이 영상처리 이다.
- 노마드 코더에서 '니꼴라스'도 그랬고.... 나도 그말에 너무 공감했다.
- 새로운 알고리즘으로 코딩을 하면 내가 작성하고 있는 Java의 문법이 맞는지 틀린지 아님 알고리즘이 잘못되었는지를 알기 힘들다.
- 이러한 시행착오를 줄이고 싶어서 영상처리를 주제로 선정 하였다.
  (아래는 PPT 로 위의 말을 정리하였는데 제대로 표현되지 않은 것 같아서 속상하다)
![주제선정이유1](https://user-images.githubusercontent.com/108249298/200276477-206702c8-32e5-4899-b08a-527b6ea921!
[주제선정이유2](https://user-images.githubusercontent.com/108249298/200276523-ff01a8f3-c126-4f70-a1d6-da257b015064.png)
6e.png)

## ㅇ S/W UI 소개
![swUi](https://user-images.githubusercontent.com/108249298/200276610-8da8fab5-cbe4-4c65-8c60-1da91d54ada1.png)

- 위의 화면은 S/W의 UI를 간략하게 나타내었다.
    1. 좌측 상단의 File Load, Save 두 개의 메뉴로 구성되어 있다.
    2. Load로 영상처리할 파일을 읽어오면 File 메뉴 바로 아래의 JLabel에 '선택한 파일은 : 경로 + 파일명 입니다'
    표시되어서 어떤 파일에 대한 영상처리를 하고 있는지 확인 할 수 있다.
    3. 입력 영상, 출력 영상은 400x300 의 크기로 설정하여서 영상처리 전후의 사진을 볼 수 있다.
    4. 마우스로 임의의 좌표를 클릭하면 좌표와 해당 좌표의 색상이 RGB로 표시 된다.
    (Robot Class를 활용하였는데 흥미로운 기능들이 많이 있었다.)
    5. 그 아래에는 실시간으로 Log가 표시되도록 하였다.
        우측의 'Save Logs' 버튼을 누르면 Text파일로 저장이 가능하다.
    6. 우측에는 영상처리 등을 위한 사용자 입력 버튼, 보정값 입력을 위한 JTextField, JSlider가 있다.

## ㅇ S/W 기능 소개
![기능소개1](https://user-images.githubusercontent.com/108249298/200276714-1c95f5a6-841f-4585-8e3b-44507e990706.png)
![기능소개2](https://user-images.githubusercontent.com/108249298/200276754-5afbf762-bcce-45c9-9dd1-6d265a31eba6.png)

- S/W의 영상처리 기능 중에서 일부 기능을 나타내었다.
- 각 기능에 대한 자세한 설명은 Mini Project 1~3의 포스팅을 참고하면 된다.


## ㅇ S/W 기능 - 게임(Dream Blast) Helper
![game](https://user-images.githubusercontent.com/108249298/200276833-88268095-5f5f-4363-8bdc-1898e768c80b.png)

- 이번 미니 프로젝트를 진행하면서 가장 고민했던 부분이다.
- 영상처리 S/W는 기존의 미니프로젝트 Ver 3.0에서 이미 JSP(라고 쓰고 Java라고 읽는다)로 모두 변환하였다.
- 물론 JLabel, JTextField, JSlider 등을 사용하면서 처음 코딩해서 그런지 가장 기본적인 부분에서도 수많은 에러 및 버그가 발생하였다.
- 장영완 교수님의 수업시간 중 코드도 참고 하였지만, 가장 많은 도움을 받은 것은 전지전능하신 'Google'님이다. 
- 구글님께서는 수많은 자료를 가지고 계시지만 내가 정확한 키워드를 검색하고 아주 기초적인 수준의 영어는 해석할 수 있어야 도움을 주신다. 때로는 잘못된 정보도 있지만 잘 걸러내야 한다.
- Dream Blast 게임은 가장 많은 색을 가진 블록을 선택(터치)해야 게임에서 승리할 확률이 높아진다.
- 다른 여러가지 방법도 있지만 '판단'을 요하는 문제들은 현재 내 코딩 실력으로는 불가능해서 색상 판단만 코딩으로 구현하였다.

    1. S/W에서 File - Load 해서 게임(Dream Blast)의 실행화면을 입력한다.
    (실제로는 스마트폰의 화면을 Capture 한 후에 JPG 파일로 저장해서 입력 하였다.)
    2. S/W에서 게임시작 버튼을 클릭
    3. S/W가 입력 영상에서 가장 많은 색의 블록이 무엇인지를 판단해서
    4. 해당 버튼으로 마우스를 이동시킨 다음에 자동으로 클릭한다.
    5. '게임에서 OO색 버튼 추출하였습니다'의 로그를 출력하고
    6. S/W 화면의 출력영상으로도 확인이 가능하다.

- 색상 판단 알고리즘은 아래와 같다.
    1. 사진 각 픽셀의 R,G,B 정보를 ImageIO로 입력받는다.
```java
public static BufferedImage roadFromFile (int width, int height, BufferedImage image, String filename) {
	
	try {
		File sampleFile = new File(filedirectory_open);
		image = new BufferedImage(width, height, BufferedImage.TYPE_INT_ARGB);
		image = ImageIO.read(sampleFile);
		
		System.out.println("Reading Complete" + image);
		
		// my code
		inW = image.getHeight();
		inH = image.getWidth();
		
		System.out.println("W" + inW + "H" + inH);
		
		inImage = new int[3][inH][inW];
		
		// 읽어오기
		for(int i=0; i<inH; i++) {
			for (int k=0; k<inW; k++) {
				int rgb = image.getRGB(i,k);  // ex)F377D6  --> 0000F3  

				int r = (rgb >> 16) & 0xFF;    // F377D6  ---> 0000F3 & 0000FF ==> F3 
				int g = (rgb >> 8) & 0xFF;    // F377D6  ---> 00F377 & 0000FF ==> 77
				int b = (rgb >> 0) & 0xFF;    // F377D6  ---> F377D6 & 0000FF ==> D6
				
				inImage[0][i][k] = r;
				inImage[1][i][k] = g;
				inImage[2][i][k] = b;
				}
		}  // for
		
	} catch (IOException e) {
		System.out.println("Error" + e);
	}
		return image;		
		
	} // BufferedImage roadFromFile(int width,
```
    2. RGB 값을 HSV로 변환한다.
    (Mini Project Ver 3.0에서 고생했던 RGBtoHSV, HSVtoRGB 함수 활용)
```java
public static float[] rgb2hsv(float r, float g, float b) {
	float max1 = Math.max(r,g);
	float max2 = Math.max(g,b);
	float max = Math.max(max1,max2);
	
	float min1 = Math.min(r,g);
	float min2 = Math.min(g,b);
	float min = Math.min(min1, min2);
	
	float d = max - min; //Delta RGB value
	float h=0, s;
	float v = max / 255;
	
	if (max==0)  s = 0;
	else s = d/max;	   
	
	if(max==min){ h = 0; }

	else if(max==r){ h = (g - b) + d * (g < b ? 6: 0); h /= 6 * d; 	}
	else if(max==g){ h = (b - r) + d * 2; h /= 6 * d;	}
	else{ h = (r - g) + d * 4; h /= 6 * d;	}	
								 
	hsv[0] = (float)(h);
	hsv[1] = (float)(s);
	hsv[2] = (float)(v);
	
	return hsv;
} // rgb2hsv

public static float[] hsv2rgb(float h, float s, float v)
{
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

     if(i%6==0){ r = v; g = t; b = p; }     
     else if(i%6==1){ r = q; g = v; b = p; }
     else if(i%6==2){ r = p; g = v; b = t; }
     else if(i%6==3){ r = p; g = q; b = v; }
     else if(i%6==4){ r = t; g = p; b = v; }
     else if(i%6==5){ r = v; g = p; b = q; }
    
  	rgb[0] = (float) r*255;
  	rgb[1] = (float) g*255;
  	rgb[2] = (float) b*255;
  
    return rgb;
} // hsv2rgb
```
    3. 각 점의 H 값 중에서 원하는 값을 누적시킨다. 각 블록 색상에 따른 H값을 범위는 여러번의 시행착오(노가다)를 통해서 확인 하였다.
```java
	      if(0<=(H*360) && (H*360) <= 50) {
					sum_color_orange ++;
				}
							
				if(72<=(H*360) && (H*360) <= 132) {
					sum_color_green ++;
				}
				
				if(150<=(H*360) && (H*360) <= 210) {
					sum_color_sky ++;
				}
				
				if(260<=(H*360) && (H*360) <= 290) {
					sum_color_purple ++;
				}
				
				if(302<=(H*360) && (H*360) <= 362) {
					sum_color_pink ++;
				}
```
    4. 누적된 값들 중에서 가장 큰 값을 찾는다.
```java
 int[] find_max_color = new int[]{sum_color_sky, sum_color_pink, sum_color_green, 
					 							sum_color_purple, sum_color_orange};
			 int max_color = 0;
			 
			 for (int i=0; i<find_max_color.length ; i++) {
				 if(max_color < find_max_color[i]) {
					 max_color = find_max_color[i];
				 }
			 }
			 textarea_record.append("max_color = " + max_color + '\n');
```
    5. 가장 큰 값(max_color)에 해당하는 버튼으로 마우스 이동 한 후에 클릭 시킨다.
    단순히 화면상의 좌표로 마우스를 이동 시키는 것이기 때문에 S/W를 실행한 다음 S/W의 위치를 변경시키면 제대로 동작하지 않는다. S/W의 위치를 변경시켰을 때 해당 좌표를 확인하는 방법도 추후에 고민해야 한다.
```java
 try {
				Robot robot_mouse_move = new Robot();
				
				if (max_color == sum_color_sky) {
					robot_mouse_move.mouseMove(1460,860);
					robot_mouse_move.mousePress(InputEvent.BUTTON1_DOWN_MASK);
					robot_mouse_move.mouseRelease(InputEvent.BUTTON1_DOWN_MASK);
				 }
				
				if (max_color == sum_color_orange) {
					robot_mouse_move.mouseMove(1500,860);
					robot_mouse_move.mousePress(InputEvent.BUTTON1_DOWN_MASK);
					robot_mouse_move.mouseRelease(InputEvent.BUTTON1_DOWN_MASK);
				 }
				
				if (max_color == sum_color_green) {
					robot_mouse_move.mouseMove(1380,860);
					robot_mouse_move.mousePress(InputEvent.BUTTON1_DOWN_MASK);
					robot_mouse_move.mouseRelease(InputEvent.BUTTON1_DOWN_MASK);
				 }
				
				if (max_color == sum_color_purple) {
					robot_mouse_move.mouseMove(1420,860);
					robot_mouse_move.mousePress(InputEvent.BUTTON1_DOWN_MASK);
					robot_mouse_move.mouseRelease(InputEvent.BUTTON1_DOWN_MASK);
				 }
				
				if (max_color == sum_color_pink) {
					robot_mouse_move.mouseMove(1340,860);
					robot_mouse_move.mousePress(InputEvent.BUTTON1_DOWN_MASK);
					robot_mouse_move.mouseRelease(InputEvent.BUTTON1_DOWN_MASK);
				 }
```
    6. 최종적으로 결과를 확인한다.(박수~!!)


## ㅇ 로봇 테스트
- Robot Class에서는 마우스 이동, 클릭, 키보드 입력 등을 할 수 있다.
- 로봇 테스트 버튼을 활용해서 간단하게 글씨를 쓰는 연습을 하였다.
- 스마트폰 게임을 할 때 '자동클릭커' 등을 사용한 적이 몇 번 있었는데 그 때 흥미로움을 느꼈고 지금 와서 보니 그렇게 어려운 기능은 아니었다.
- 윈도우 버튼 --> notepad --> 글자크기 100 --> happy 입력
- 단순하게 키보드를 눌러서 실행할 수 있는 프로그램과 단축키 활용하는 기능 등은 쉽게 구현 할 수 있다.
- '판단'이 필요한 다른 기능들은 할 수 없다. 아주 단순한 일만 처리하는 '심부름꾼'이라고 생각하면 된다.

## ㅇ 사용자 편의기능(로그 기록 및 저장)
- 미니 프로젝트를 하면서 처음에는 '시간을 다스리는 자' 가 되고 싶었다.
- 현재 시간, 화면을 클릭했을 때와 그 다음 클릭 할 때까지의 소요시간 등 게임이나 다른 S/W 에서 활용할 수 있는 많은 것들은 '시간'을 확인 하고 계산할 수 있어야 한다.
- 하지만 교육센터의 수업시간에는 배우지 않아서 구글님께 많은 자료를 받았고 몇 가지 연습도 해보았다.
- 그 중에서 이번 프로젝트에서는 로그 기록에 활용 하기로 하였다.
- 로그는 '언제' '무엇을' 했는지 기록하여야 하므로 아래의 코드를 활용 하였다.
- JAVA는 코드 몇 줄 만으로도 쉽게 현재 시간을 확인 및 출력 할 수 있어서 매우 편리하였다.
```java
String formatDate = LocalDateTime.now().format(DateTimeFormatter.ofPattern("yyyyMMdd"));
			textarea_record.append(formatDate + " ");
			
			String formatTime = LocalDateTime.now().format(DateTimeFormatter.ofPattern("HH:mm:ss.SSS"));
			textarea_record.append(formatTime + " -- ");
```![사용자 편의기능(로그)](https://user-images.githubusercontent.com/108249298/200278177-1876f61b-ca2d-4f3b-9fb5-ed50a8ac184c.png)

- textarea에 로그를 기록하는 것은 아래와 같다.
> textarea_record.append(" 로그로그로그") ;
- 이 때 꽤 많은 시간을 필요로 했던 것이 JScrollPane 이다. 로그가 일정 수준 이상으로 기록되면 textarea에 누적이 되어서 한 눈에 볼 수 없게 되고 이 때 scrollbar를 추가하여야 한다.
    또한 로그가 저장 되면 새로운 로그가 저장된 위치로 scrollbar가 자동으로 이동하여야 한다.
- 구글께서 알려주신 코드를 적용하였다.
- JScrollPane이 추가 될 textarea를 선언하고, panel에는 textarea를 add 하는 것이 아니라 JScrollPane만 add 하여야 한다. 아마도 textarea는 JScrollPane에 종속되는 것으로 생각하여야 할 것이다.
```java
JScrollPane scroll_text_area = new JScrollPane(textarea_record, JScrollPane.VERTICAL_SCROLLBAR_AS_NEEDED, JScrollPane.HORIZONTAL_SCROLLBAR_AS_NEEDED);
		scroll_text_area.setBounds(10,10,815,200);
		scroll_text_area.setLocation(20,500);
		
		scroll_text_area.getVerticalScrollBar().setValue(scroll_text_area.getVerticalScrollBar().getMaximum());
		
		panel_Main.add(scroll_text_area);
```

- 새로운 로그가 저장된 위치로 scrollbar 자동 이동하는 코드 이다.
    JTextArea에 저장된 텍스트의 총 길이에 scrollbar의 caret의 포지션을 설정하고 textarea를 새로고침하면 된다. 
- 이것을 textfield_record_scroll 이라는 함수로 선언한 다음 textarea에 새로운 내용이 기록될 때 마다 추가해주었다.
- (시도해 볼 내용) textarea에 change event listener를 추가해서 event가 발생할때마다 해당 함수를 실행하도록 하면 되지 않을까...
```java
public void textfield_record_scroll() {
		//int 형 변수에 jTextArea 객체의 텍스트의 총 길이를 저장
		int pos = textarea_record.getText().length();
		
		//caret 포지션을 가장 마지막으로 맞춤
		textarea_record.setCaretPosition(pos);
		//갱신
		textarea_record.requestFocus();
	}
```

## ㅇ 사용자 편의기능(키보드 단축키)
![shutCutKey](https://user-images.githubusercontent.com/108249298/200278574-26707615-231d-4eae-bb4a-59106c6a5fcb.png)
- 키보드 단축키는 의외로 단순하였다. 달랑 한 줄
```java
file.setMnemonic(KeyEvent.VK_F);
```

## ㅇ 사용자 편의기능(파일 로드, 저장)
![편의기능(파일로드 저장)](https://user-images.githubusercontent.com/108249298/200278965-ae0d162e-3678-4b52-bd03-a5bf30948e4b.png)

- 이번 S/W 에서 파일 입력 관련 제한사항이다.
    1. 입력 파일 유형 : 'jpg' (그 외의 파일이 입력되면 S/W는 수많은 오류를 발생, 동작 불가)
    2. 파일은 단 하나만 입력 되어야 한다.
- 처음에는 FileDialog를 활용하여 파일의 입력 및 저장을 하였다. 당연히 기능은 제대로 동작하지만 파일의 확장자를 제한하는 기능은 없었다.(아니, 찾지 못하였다.)
- 구글께서 알려주신 방법은 JFileChooser 였다.
```java
else if(e.getSource() == fopen) {
			file_open.setVisible(true);
			file_open.setFileSelectionMode(JFileChooser.FILES_ONLY);
			file_open.setDialogTitle("영상처리할 파일을 로드 하세요");
			file_open.addChoosableFileFilter(new FileNameExtensionFilter("Images(JPG), JPG만 선택 가능 합니다", "jpg"));
			file_open.setAcceptAllFileFilterUsed(true);
			file_open.setMultiSelectionEnabled(false); // 다중 선택 불가 설정

			file_open.setSelectedFile(new File(".jpg"));
			File open_default_directory = new File("C:\\images");
			file_open.setCurrentDirectory(open_default_directory);
			
			int file_open_result = file_open.showOpenDialog(this);
			
			if(file_open_result == JFileChooser.APPROVE_OPTION) {
			filedirectory_open = file_open.getSelectedFile().getAbsolutePath();
			filename_open = file_open.getSelectedFile().getName();
			}
			
			if(filedirectory_open==null) { return;	}
						
			File file_name_Open = file_open.getSelectedFile();
			String open_file = file_name_Open.getName();
			
			String formatDate = LocalDateTime.now().format(DateTimeFormatter.ofPattern("yyyyMMdd"));
			textarea_record.append(formatDate + " ");
			
			String formatTime = LocalDateTime.now().format(DateTimeFormatter.ofPattern("HH:mm:ss.SSS"));
			textarea_record.append(formatTime + " -- ");
			
			textarea_record.append(filedirectory_open + " 의 파일을 로드 하였습니다. " + '\n');
			
			label_filename.setFont(new Font("맑은고딕", Font.BOLD, 20));
			label_filename.setText("선택한 파일은 : " + filedirectory_open + " 입니다.");
			
			image = roadFromFile(width, height, image, filename_open);
				
			equalImage(image);
			Graphics2D g_in = (Graphics2D) panel_Image_In.getGraphics();		
			g_in.drawImage(image, 0, 0, null);
			textfield_record_scroll();
			
		}
```
    1. file_open.setFileSelectionMode : FILES_ONLY // 파일만 입력 가능하도록 제한
    2. file_open.setDialogTitle : JFileChooser 상단의 제목 설정
    3. file_open.addChoosableFileFilter : 파일 유형 제한하는 메뉴 생성
    4. file_open.setAcceptAllFileFilterUsed : FileFilter 사용 여부(true : 사용)
    5. file_open.setMultiSelectionEnabled : 파일 다중 선택 여부(false : 불가)
    6. file_open.setSelectedFile : ".jpg"로 설정시 그 외 다른 파일은 JFileChooser에서 안보임
    7. file_open.setCurrentDirectory : JFileChooser 실행시 default로 보이는 directory 설정
- JFileChooser에서 선택한 file의 directory, filename을 입력받기 위해서는 반드시 아래의 과정을 해야 한다.
- 정확한 이유는 찾지 못하였으나, JFileChooser가 실행된 것을 확인해야만 .getSelectedFile()이 동작되도록 제한되어있는 것으로 짐작된다.

# ㅇ 추가 개발 및 개선 필요사항(1)
![개선1](https://user-images.githubusercontent.com/108249298/200279190-da7be80b-b542-40ca-9181-33b550dc40bc.png)

- 치명적인 단점이 하나 있다. 영상 시현 패널의 크기가 (400 x 300)으로 고정되어 있다는 것이다.
  (본 프로젝트 코딩에서 가장 해보고 싶었지만 못했던 것이다.)
- 사진은 크기가 제각각이고 요즘은 400 x 300 보다는 훨씬 큰 사진이 많다. 하지만 본 S/W 에서는 해결하지 못하였다.
    1. 패널이 스크롤바(JScrollPane)를 추가해서 상하좌우로 움직이면서 사진을 확인
    2. 패널의 크기가 사진의 크기에 따라서 변화하는 방법
    3. 3개의 프레임(입력영상, 출력영상, 사용자 UI) 으로 나누어서 구현하는 방법
- 상기 3가지 방법 모두를 몇 번씩 시도해보았으나, 최종적으로는 모두 실패하였다.

추후에 다시 해보려고 PPT와 블로그에 기록해 놓았다.
- 1개 Class에 여러 함수 사용은...ㅠ_ㅠ
- Java의 가장 큰 장점이자 본질은 '객체지향' 이라는 것이다.
   이것은 그 누구도 부정할 수 없다.
- 하지만 본 S/W의 class는 1개 이다. 물론 함수는 여러개이지만..
- 처음에는 원하는 기능을 되게 하는 것이 목표였고 조금 후에 생각해보니 객체지향언어의 장점을 하나도 못 살리고 있었다.
- 객체, 생성자, 상속... ... ...
- 추후에 실무에서는 객체지향 S/W를 반드시 구현할 것이다.
- 아래는 내가 요즘 따로 시간내서 공부하고 있는 유투브 이다.
[Youtube](https://www.youtube.com/playlist?list=PLW2UjW795-f6xWA2_MUhEVgPauhGl3xIp)

## ㅇ 추가 개발 및 개선 필요사항(2)
![개선21](https://user-images.githubusercontent.com/108249298/200279250-1e511ee1-36ed-4a57-a806-ba2884586124.png)

- S/W 속도가 생각보다 느리다.
- 처음 개발하는 S/W라서 이미지 로드하고 영상처리하는 속도가 이게 맞는지 잘 모른다.
- 하지만 Look Up Table, Thread 등 내가 아직 제대로 안 배우고 시도해보지 못한 Look Up Table, Thread 등 고수준의 Coding 기술을 배운 다음에 이번 코딩을 다시 해보면 조금 다른 결과가 나오지 않을까.
- (종이로) 프린트 기능이 없다. 구글과 몇시간 상담(!)을 해보고 가능할 것 같은 코드를 찾아보긴 했다. 하지만 최종적으로는 구현하지 못하였다.
- 화면에 출력되는 image는 BufferedImage의 형식으로 되어 있다.
    프린트를 위해서는 BufferedImage를 Printer의 OutputStream으로 전송 하여야 하는데 그 부분이 어려웠다.
- BufferedImage --> Printer OutputStream --> Printer Spool --> 프린터 --> 종이

## ㅇ 포스팅을 마치며
- 휴... .이제 끝이다.
- 요약지 1쪽만 작성하면 Mini Project Ver 4.0이 끝난다.
- 나름 열심히 하려고 했고 많은 시간과 노력을 투자하려고 했는데 만족한 부분도 모자란 부분도 많이 있다.
- 다음의 Java S/W 개발은 더 행복한 마음으로 시작할 수 있을 것 같다.
- 지금은 처음해보는 것들이 많아서 시간도 많이 걸리고 시간 투자도 많이 하였지만, 한 번 가본 길은 다시 가기 쉬우니까.. 그럼 이만~!!!!




* 이 포스팅 끝까지 보신 분들은 댓글 하나만 남겨주시면 감사하겠습니다 ^_^
