
# tracking

- tracker    
    Nuke의 카메라 트랙더 노드는 통합 카메라 추적 또는 일치 도구를 제공할 수 있도록 설계되었다.2D 영상에서 카메라 이동 추적 카메라 움직임을 2D 개체를 2D 영상을 2D 영상으로 추가할 수 있다.   
    첫 프레임에 트레커 달지 말자
  ##  one point tracking   
  ![image](https://user-images.githubusercontent.com/113075273/232699199-80f3a5fb-239e-4e05-99e7-db8d4757d121.png)

    
    포인트는 특정한 픽셀의 패턴. 대비가 강한 부분 중점으로 잡고. 안쪽에 있는 사각형은 이러한 패턴을 찾음. 바깥의 사각형은 지정한 모양이 이 영역 안까지 움직일 수 있다 지정.
    
    상단의 바에서 트랙 아이콘 삼각 토글 모양 누르면 트랙커 작동. 그럼 왼쪽 뷰어에 보임.
    
    R되어 있는건 영역 지정.
    
    신호등 아이콘 누르면 누크가 초록색 부분 붉은 색 부분 트랙킹 어색한 부분 나눠줌.
    
    상단 우측에 위치한 엑스자 아이콘은 트랙 날리는 것.
    
    트랙커의 트랜스폼에 입력된 수치(센터,트랜스값)를 불러와서 위에 뭔갈 덮어씌운다던지 할 수 있다.
    
    위치 회전 스케일 값 밑에 매치무브에 넣는다 입력 박스 하고 매치무브 연결.
    
 ##   two point tracking
    
    스타빌 라이즈 써서 안흔들린 상태에서 합성후 흔들림.
    
 ##   four point tracking
    
 corner pin 투디 노드.
    ![image](https://user-images.githubusercontent.com/113075273/232715672-6e00b17b-1c8e-449f-a295-f4f1bb04413e.png)

    
- match move   
![image](https://user-images.githubusercontent.com/113075273/232716475-7823b05c-3f90-43bc-bf1d-5fa5ac4e91a0.png)

    
    트랙 움직이는 거와 똑같이 트랜스폼을 생성. 움직일 플래이트를 노드에 연결하기만 하면 됨.
    
- frame hold
    
    레퍼런스의 한 프레임만 가져올 때
    
- stabilize
    
    카메라 흔들림을 반대 방향으로 흔들어서 잡아줌 
    
- camera tracker
    
    카메라 움직임이 없으면 쓸 필요 없다
    
    nukeX
    
    add user track
- noise   
   ![image](https://user-images.githubusercontent.com/113075273/232689017-271f6939-52df-4fb8-958c-4990b2d22ca0.png)   
   모든 촬영된 이미지는 노이즈를 갖는다. 초록색 크로마키도 블루 채널로 보면 노이즈가 있음.   
   - regrain   
   ![image](https://user-images.githubusercontent.com/113075273/232690114-0ba89c5a-27da-4590-9ca8-0b082b39f8a7.png)   
   ![image](https://user-images.githubusercontent.com/113075273/232690334-8dba36f8-15e4-4851-847b-7b1b2db96b4d.png)

- lensdistortion   
- 리디스톨션은 전체 플레이트에 하지 말고 풋티지에만 하자.
-![image](https://user-images.githubusercontent.com/113075273/232708645-f783e281-7234-45b9-97d7-5daa29fc3aec.png)

- planartracker   
먼저 로토 처럼 베지어 따고 인식 한 다음 트래킹 들어가서 위쪽 아이콘 눌러 트랙 포인트 재지정 후 플레이하면 따라감
![image](https://user-images.githubusercontent.com/113075273/232725515-81f2d95a-9b6a-434f-b0dd-01b083eb158e.png)
track 2d랑 storesign을 트랙킹하는건데
6개의 간판 중에 좌측에 강아지 같이 생긴거 포함 그 외에 3개의 컴프를 추가로 합성한다.
전부 다 코너핀으로 하면 안되고 플래너트래커를 하든 코너핀트래킹을 하든 2개씩하자.

storesign

lens distortion 펴주고 local 싸인을 다른 싸인으로 바꿔서 넣어주자.
tracking에서 reflection도 넣어줘야 한다.

grain이 뭐고 noise가 무엇이냐.

똑같은 개념인데 그레인은 필름 디지털
노이즈는 카메라 센서에서 발생하는 입자 생성.

디지털 촬영한 것은 그레인이 생기는데 새로 붙는 소스가 깨끗하면 이질감이든다.
그래서 추가되는 오브젝트를 grain을 플레이트에 입혀주려면 regrain 노드를 사용하면 되는데
grain을 원본 플레이트의 노이즈를 따고 src를 추가되는 플레이트에 입혀주면 된다.

만약에 jpg파일들을 불러와는데 이미지가 재생이 안된다면 global로 되어있느 것들을 input으로 바꿔줘야한다.

매치무브에는 베이크와 일반이 있는데 베이크는 처음 프레임 적용한거 그대로 독립적으로 따라가는거고
일반은 초록색 선으로 연결되어 우리가 값을 바꿔주면 실시간으로 적용이된다.

lens distortion을 잡아주는 노드는 TAB키에서 lens distortion키를 입력해주고
x키를 눌러서 TCL모드로 LensDistortion (대소문자확인) 입력하여 2개의 노드를 만들어준다.
그 다음 x키를 눌러 만든 lensdistortion node의 image analysis들어가서 범위를 지정해주고
 analysis sequence 눌러주면 자동으로 포인트들이 생기며 왜곡을 잡는다.

4개의 점을 트래커로 잡았다면 2d 코너핀을 만들고 대체할 푸티지를 들고와서 from창으로 넘어가서 set to input을 해주고
copy from을 해주면 to 점이 4개가 생긴다. 그다음 그 4개의 점을 옮겨서 위치를 수정해주면 된다.





