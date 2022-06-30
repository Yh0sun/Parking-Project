# Parking Project - 융복합 프로젝트 관리자 웹사이트
***
<br>

**배포주소** <br>
http://www.parking-check.com/<br>
<br>
**웹사이트 & 배포 수행 도구**<br>
Django, docker, nginx, aws rds, aws route 53, aws ec2<br>
<br>


## :car:융복합 프로젝트(AI, IOT, 클라우드, 빅데이터) 요약
<br>

 - 장애인 구역 불법 주차를 근절하고 신고자에 대한 보복성 행위 방지를 위해 장애인 주차구역 위반 방지 서비스를 기획
 - 주차장에 들어오는 장애인 차량의 사진을 찍어 장애인 차량 여부와 번호판을 인식하고
 - 장애인 주차 구역에 주차하는 차량의 번호판을 database와 대조하여 위반 차량을 잡아낸다.
 <br>

>![image](https://user-images.githubusercontent.com/89528276/176693566-6b9f45ad-bcf5-4d09-bb97-3ee461300516.png)
<br>

**_-아키텍쳐 구성_**

>![아키텍처](https://user-images.githubusercontent.com/89528276/176686485-07dd5e26-986f-48c2-a63f-1ea5f21287a0.png)
<br>

## :clipboard:사이트 주요 기능
- 관리자가 보는 페이지와 일반 이용자가 보는 페이지를 로그인으로 구분
  - 관리자 페이지 : 주차 현황, dashboard, 입차 차량 확인, 장애인 주차 확인(위반 차량 확인)
  - 일반 이용자 페이지 : 주차 현황
- 주차 현황에 현재 주차장의 주차 현황을 알 수 있음
- dashboard에 최근 입차차량과 주차 상황, 차단기 제어 버튼
- 입차 차량에 차량 번호, 장애인 스티커 유/무, 입차 시간, 차량 사진을 볼 수 있음
  - 이때, 입차 차량의 번호가 제대로 인식되지 않았다면 사진을 보고 관리자가 번호 수정 가능
- 장애인 차량임에도 불구하고 장애인 스티커 인식이 제대로 되지 않아 위반 차량으로 저장된 경우,
<br> 차량 정보가 수정되고 위반 차량 리스트에서 삭제 가능
- MQTT 브로커에서 받은 정보를 rds에 저장
- 차량 번호가 정상적으로 감지되지 않았을 때, 심플 노티스 라이브러리를 통해 팝업 알람으로 알림

***
### :mailbox_with_mail:느낌점
- 각기 다른 전공 팀원들이 모여서 함께한 융복합 프로젝트이다 보니 처음에는 서로의 전공에 대해 잘 몰라 주제를 정하는 것조차 정말 힘들었다.
하지만 프로젝트를 마친 지금 생각보니 많은 커뮤니케이션 능력을 기를 수 있었던 기회였고 일반적인 웹개발 프로젝트보다 더 실무에 가까운 클라우드 기술을 적용해볼 수 있었다.
클라우드 부분과 배포, 웹사이트 페이지 구성, 로그인 부분을 맡았는데 좀 더 웹사이트 기능을 추가하여 이를 구현하였으면 좋겠다는 아쉬움이 남습니다. 

