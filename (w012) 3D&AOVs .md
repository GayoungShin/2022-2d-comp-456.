# 3D 
- 3d 렌더링 할때는 알파채널이 없는 물체를 따로 렌더링하고 배경과 합침
- cryptomatte 알파 채널 각각 선택하게 해줌 
- grade, colorcorrect 같은 작업은 먼저 하고 premult 하자
- log2in 리니어 이미지를 로그로 바꾸거나 로그 이미지를 리니어로 바꿔줌
- 3d는 셔플로 각각의 구역 나눠서 따로 내가 편집하고 싶을때마다 할수 있음
- S log에 lut적용으로 색상 변환-> 중간톤의 컬러가 많아져 합성에 용이

- sharpness 적용 후 lut-> 원본의 손상이 적게 이미지를 만들 수 있음




# AOVs
## color AOVs
direct / indirect -maya에서 주로 사용. 정반사 난반사? 빛이 직접 쏘는거와 반사되는 것
albedo - 빛과 쉐이더가 아예없는 색상. 쉐이더와 알비도를 더한게 디퓨즈라고 보면 될듯.

## MAin Utility AOVs

