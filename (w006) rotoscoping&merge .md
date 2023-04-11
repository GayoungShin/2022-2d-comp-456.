
*누크 노드는 항상 위에서 아래인 것을 명심하자   
    모든 영상은 metadata가 존재하는데 다른 걸 합성하면서 original plate의 metadata를 유지하기 위해서이다.   
    motionblur 노드는 전체적으로 누크가 느려지기때문에 로토 자체에 있는 모션 블러를 쓰자   
    layer channel   
       ![image](https://user-images.githubusercontent.com/113075273/231084860-0fbd8bf6-7785-4ac0-9af1-adcd688e568c.png)
  
# premult-mutiplies the rgb values by the alpha
# you cant work colorcorrect in pre-mutied image
   ![image](https://user-images.githubusercontent.com/113075273/231094950-ce0ddcb9-bca5-4c57-92e2-f1965ce0d988.png)
   ![image](https://user-images.githubusercontent.com/113075273/231095000-3cda2380-7a44-428f-841c-55e35aecaa5f.png)



# rotoscoping
로토스코핑의 역사: 폴란드 계 미국인 Max Fleischer가 개발한 로토스코핑은 이미 촬영된 동영상을 따라그리거나 위에 효과를 그려 만드는 애니메이션 기법이다.   
![image](https://user-images.githubusercontent.com/113075273/206973946-dd98c333-a677-48f1-93fc-e5bda7768712.png)


## Rotoscoping in nuke
원하는 부분에 있는 오브젝트를 따내기 위한 알파를 만든다고 생각. 

1.대상이 어떻게 움직이는지 먼저 파악

2.사라지는 픽셀들 최대한 균일하게 맞추기

3.쉐잎이 겹치는 부분 자세하게 관리

4.트랜스폼이랑 모션블러 키 프레임 줘서 관리

## rotopainting Prep

identify motion path

separate by objects

stabilize plate

- 움직임의 역치값을 넣으면 안정된 상태로 보인다.

primary and secondary forms

use rotational points

- 해부학적 움직임을 추적

# merge
*a는 A채널의 알파, b는 B채널의 알파
![image](https://user-images.githubusercontent.com/113075273/206976172-b3753f07-4c97-4bc7-a824-f9785d04ae07.png)   
   
    
 ### 주로 사용하는 것
- over A+B(1-a)
- mask Ba
- matte Aa+B(1-a)
- multiply AB, A if A<0 and B<0

# rotopainting
로토 페인트: 로토스코핑, 장비 제거, 가비지 매트 및 먼지 파열과 같은 작업에 도움이되는 백터 기반 노드이다.


### 프로젝트 경로 설정 방벙 [프로젝트 세팅-프로젝트 딜리토리- 스크립트]

1. 절대 경로: 처음부터 기본 경로를 정해준다.
- 스크립트 디렉토리 아이콘을 누른 후 경로 설정한다.
 ![image](https://user-images.githubusercontent.com/113075273/206977769-a36adc6c-2552-4ba2-adc0-f7866fe100cf.png)

2. 상대 경로: 스크립트가 저장된 경로를 기본으로 세팅한다.
![image](https://user-images.githubusercontent.com/113075273/206977794-03d427da-eb0a-45de-88a1-159a68e94d1b.png)
[[출처](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=loveandpic&logNo=221037444169)]
- 같은 위치에 있다
    
    ./
    
- 같은 위치 내 폴더 안에 있다
    
    images/greenscreen boy.tif 
    
- 상위 폴더에 있다
    
    ../
    
- 상위 상위 폴더
    
    ../../
    
