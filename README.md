# SMART RC CAR
## 정의
openCV, Arduino, RasberryPi를 활용해 얼굴 인식과 기타 부가 기능을 구현한 스마트 RC카

<br />

## 기능
- 기본 RC CAR 조작 기능
- openCV를 이용한 얼굴 인식 기능
- 주변 장애물 감지 
- 버튼과 LCD를 이용한 타운전자에게 의사 전달 기능
- 미세먼지 농도에 따른 창문 조절 기능 

<br />

## 프로젝트 설명
* RCCar.ino
  * RC카 기본 조작 기능
  
  <br />
  
* mise_window.ino
  * 미세먼지가 일정 농도 이상일 때 창문을 닫는다. 
  * 압력센서로 일정 압력 이상일 때 창문을 연다.
  * 서브모터를 이용해 창문을 움직인다.

<br />

* ultra_lcd.py
  * 초음파 센서, 스위치 이용
  * 장애물과 거리가 기준보다 가까워 졌을 때, 피에조 부저로 경고음을 울린다.
  * 버튼을 눌렀을 때, 일정 시간동안 기존 문구 'Good Day'에서 'Thank You'로 변경하여 LCD 디스플레이에 보여준다. 

<br />

* 01_face_dataset.py
  * 카메라 이용
  * 사용자의 얼굴을 이미지화한다.
  * RGB -> gray 스케일로 저장한다.

  <br />
  
* 02_face_training.py
  * training.py 의 결과물을 바탕으로 이미지를 학습한다.
  * 파일은 .yml로 저장한다.

  <br />
  
* 03_face_recigniition.py
  * 실시간 얼굴 인식을 통해 학습된 사용자를 판별
  
  <br />
  
  > **학습된 사용자**  
  >* id 값과 일치하는 사용자 이름을 디스플레이  
  >* 5개의 LED가 빛남  
  >* 파에조 부저로 welcome 사운드 출력

  <br />

  > **학습되지 않은 사용자**   
  >* 이름을 판별할수 없을 때는 unknown 디스플레이  
  >* RED LED만 출력  
  >* 파에조 부저로 unwelcome 사운드 출력  

  <br />
  
* faceSmileEyeDetection.py
  * 얼굴,눈, 미소를 인식한다.
