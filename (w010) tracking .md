
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
