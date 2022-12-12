# 2D
```
2D는 길이와 너비의 두 차원을 가진 모양으로 정의할 수 있다.
위치를 말하는 데 필요한 좌표의 수, 보통의 경우 공간에서 독립적으로 움직일 수 있는 방향의 개수를 의미. 
직선은 1차원, 평면은 2차원, 보통의 공간은 3차원이지만, n차원이나 무한 차원의 공간도 생각할 수 있다.   
```
[https://www.vocabulary.com/dictionary/two-dimensional](https://www.vocabulary.com/dictionary/two-dimensional)
## DIGITAL
 **pixel (픽셀)**
- 이미지를 이루는 가장 작은 단위
- 이미지를 이루는 점이라고 생각하면 된다
- 640x480의 경우는 가로 640개, 세로 480개의 픽셀로 이루어진 이미지를 의미한다.

![이미지 이름](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FVC0go%2FbtqCFyfnEwf%2FK6HtwvelNW0KXQjg6Ebks1%2Fimg.png)
 

**이진 영상(binary image)**
- 디지털 이미지 중 가장 간단한 형태
- 각 픽셀이 1bit로 이루어져 있으며, 각 픽셀은 오직 밝음(1)과 어두움(0) 두 가지 만을 표현한다.

![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FkyJpC%2FbtqCF7ok30Q%2Fp5byGFydow6Bvi6zLmHEu1%2Fimg.png)


 

**흑백 영상(gray-scale image)**
- 각 픽셀의 밝기 값을 0~255 사이 값으로 표현한 이미지이다.
- 8bit = 1Byte의 메모리를 사용한 것이다.
- 픽셀 값들의 범위가 0~255 사이 값이기 때문에, 2^8 = 256개의 8bit로 표현한 것이 흑백 영상이다.

![이미](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FA2r8x%2FbtqCB8aSYsN%2Fl76TsIhJNX3UBqUSSTDUGk%2Fimg.png)
 

**컬러 영상(color image)**
- 컬러 영상은 3개의 채널로 표현된다. 빛의 3원색인 빨강(Red), 녹색(Green), 파랑(Blue)이다.
- 각 채널은 0~255 사이의 값으로 각각 빨강의 정도, 녹색의 정도, 파랑의 정도를 나타낸다.
- 컬러 영상에서는 세 가지 기본 컬러를 조합항 다양한 색을 만든다.
- 각 채널의 8bit 기본 컬러 3개가 조합되어, 256^3 = 16,777,216가지의 색을 만들어 낼 수 있다.
- 8bit(R, G, B) 3개를 조합해 총 24bit(3Byte)를 이용하여 컬러를 표현했고, 이를 True color라 부른다.
- 여러 이미지나 그래픽 관련 프로그램들은 RGB 채널에 투명도(Transparent)를 나타내는 Alpha 채널을 더해 RGBA인 32bit 컬러 모델도 사용한다.

![이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fb6KBkk%2FbtqCHw2fZ1s%2Fxjxnf6OUEBR0eVH8kZKoh0%2Fimg.png)
 


[[출처](https://twlab.tistory.com/23)](https://twlab.tistory.com/23)

## Compositing
```
두 가지 이상의 소스 이미지를 디지털 방식을 사용하여 연속하는 이미지나 하나의 이미지로 만드는 일
```
[[출처](https://www.studiobinder.com/blog/what-is-compositing-definition/)](https://www.studiobinder.com/blog/what-is-compositing-definition/)
# COLOR
인간의 눈이 빨강, 녹색, 청색의 빛에 민감하기에 빨초파 세 가지 기본 색상을 사용함.
![[출처](https://www.scratchapixel.com/images/upload/color/addsubcolor.png?)](https://www.scratchapixel.com/images/upload/color/addsubcolor.png?)
## RGB    (가산혼합)
- 디지털 작업에 용이    
- RGB는 빛으로 나타내는 색상을 의미. 
- R(Red), G(Green), B(Blue)의 빛을 혼합하여 영상장치의 색상을 표현. 
- 영상장치의 전원이 꺼진 상태가 RGB에서는 검정색임. 그렇기 때문에 명암은 빛의 세기로 조절. 빛의 세기가 약할수록 어두워 지며 빛의 세기가 강할수록 RGB원색을 표현. 빛의 세기가 가장 강한 상태에서 RGB가 모두 켜지면 하얀색으로 표현됨. 
- 단위는 pixel이며 해상도는 ppi(pixel per inch). ppi는 1인치당 분포된 픽셀의 갯수이다.
 
## CMYK    (감산혼합)
- 인쇄 작업에 용이
- CMYK는 일반 잉크의 색상이다. 
- C(Cyan), M(Magenta), Y(Yellow), K(Black 또는 Key)의 잉크를 혼합하여 각 종 재질에 인쇄함. 
- CMYK는 RGB와는 반대로 하얀색 잉크가 없음.(특수인쇄 제외)
- K가 필요한 이유는 C,M,Y를 모두 섞는다 해도 K를 표현하지 못함. 명암은 C,M,Y의 농도와 K의 농도로 조절가능. 
- 인쇄에서는 dpi(dot per inch)의 단위를 사용.   
     
     [[출처](https://vitalprinting.co.kr/pna/colorExpression.html)](https://vitalprinting.co.kr/pna/colorExpression.html)
## ALPHA
```
투명도 정보가 존재하는 채널
```
1) 알파채널은 선택영역을 만들어 이미지의 선택영역을 정밀하게 수정할 수 있는 기능을 가지고 있다.
2) 알파채널은 흰색과 검은색으로 이루어지는데, 흰색으로 된 부분을 수정할수 있고 검은색으로 이루어진 부분은 수정할 수 없다.
3) 흰색 -> 검은색의 단계로 표현되는 그레이 컬러는 모두 256가지이며, 알파채널은 흰색과 검은색 즉 그레이컬러의 256단계로 선택영역을 설정할 수 있기 때문에 정밀한 선택이 가능하다. 이렇게 만들어진 여러개의 알파채널을 만든 후 흰색의 농도를 조절하여 선택영역을 더하거나 빼면서 영역을 만들어 최종적으로는 RGB 색상채널에 효과를 적용합니다.
4) 예를 들어 레이어에서 선택영역을 만들고 색을 채워주면 색이 영역안에 단순하게 채워지지만, 채널에서는 선택영역자체에 그라디에이션을 줄 수 있고 선택영역의 색이 그라디에이션으로 채워집니다.
5) 알파채널의 흰색부분은 마스크와 같은 개념인데, 알파채널에서는 마스크의 농도를 표현할 수 있다고 생각하시면 됩니다.
6) 알파채널에서는 선택영역을 저장하고 불러올 수 있는 기능을 가지고 있는데, 저장된 선택영역을 불러들여서 이미지에 적용이 가능합니다. 또한 툴박스에 있는 퀵마스크 모드를 누르면 나타나는 채널로 선택영역을 편집할 수 있다.   
       [[출처](http://egloos.zum.com/knyatom/v/1458411)](http://egloos.zum.com/knyatom/v/1458411)
# Colorspace
- 색 영역은 특정 장치가 생성하거나 기록할 수 있는 색상 범위. 
- 일반적으로 색도 다이어그램에서 장치의 기본 색상의 밀폐 된 영역으로 표시된다. 
- 우리는 또한 다른 색상 장치에서 영역 내 색상 일치를 용이하게하기 위해 색 영역인 sRGB를 표준화한다.  
- 일반적으로 디스플레이 기기의 색 재현도를 판단할 때 표현할 수 있는 색상의 범위만 판단하는 경향이 있다.
- HDR 영상의 등장으로 인해 최근 HDR 디스플레이 기기가 등장하고 있음. 이에 따라 광색역 디스플레이 기기라고 할지라도 표현할 수 있는 휘도 영역에 따라서 HDR 지원 기기와 SDR 기기로 구분할 수 있다.

![이미지](https://image.benq.com/is/image/benqco/color-gamut-5?$ResponsivePreset$&wid=1468)
![이미지](https://image.benq.com/is/image/benqco/color-gamut-7?$ResponsivePreset$&wid=1468)

   [[출처](https://www.benq.com/en-me/knowledge-center/knowledge/color-gamut-monitor.html)](https://www.benq.com/en-me/knowledge-center/knowledge/color-gamut-monitor.html)

