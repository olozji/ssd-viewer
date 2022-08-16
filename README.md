#  SSD-Medical-Image-Web-Viewer

## Features
- 임베디드 Dicom을 연동하여 환자들의 내시경 이미지와 영상들을 클라우드 서버를 통해 화면에 출력하여 볼 수 있게 하는 이미지 뷰어 개발
- 이미지를 불러오고 드래그 하여 드래그로 영역을 잡아 굵기를 조절할 수 있습니다.
- 기능을 클릭하면 이전 기능과 다시 실행 기능을 실행할 수 있습니다.

## How to start project
Local 환경에서 실행하는 것을 가정했을 때 필요한 것들   
  ```
  1 Nginx로 웹서버 구축
  설치되어 있는 우분투 터미널에서 sudo apt-get install nginx -y 로 설치

  2 smb로 자원 공유 및 디렉토리 설치
  sudo apt-get install -y samba 설치
  mkdir / smbdir 디렉토리 설치
  
  3. nginx 웹서버에 ssl 인증과 CSR(Certificate Signing Request)생성
  OpenSSL 라이브러리 http://www.openssl.org/ 설치
  sudo nano /etc/nginx/sites-available/myapp.conf 에서 Reverse proxy 설정 
  포트번호 회사 도메인과 연결

  #3 nginx 서버와 vsftpd 연결 
  sudo apt-get install vsftpd
  파일질라 연결
  
  #4 vscode에서 ASP.NET 프로젝트 생성
  
  ```

## 해당 프로젝트를 만든 이유

환자들이 내시경 촬영 시 촬영의 이미지들을 임베디드 시스템을 기반한 dicom 이미지를 클라우드 서버로 처리하여 이미지 뷰어로 연결하여 
병원 관계자들에게 내시경 진료 시 편리한 업무 시스템을 제공하기 위함

## Project Demo

1. ubuntu 리눅스 익숙해지기
리눅스는 처음 접해보는 것이어서 익숙해지는데에 한달이 조금 안되는 시간을 가지며 기간동안 nginx 웹서버 설치와 서버 구축시 필요한 자원들 셋팅

2. nginx 웹서버를 reverse proxy 포워딩
ssl 443포트가 적용된 서버를 회사 서버 도메인과 프록시 포워딩을 진행하여 연결하여 static hosting 구축

3. vsftpd를 통해 테스트용 가상 서버에서 이미지를 받아와 출력
파일질라를 이용하여 테스트용 서버에서 이미지를 받아와 mysql로 연동하여 서버에서 받아오는 지 테스트

4. javascript(es6) prototype 기반으로 뷰어 기능 구현
객체 속성에 원활한 접근을 위해 prototype을 사용하여 기능들을 구현

## 프로젝트 완성 후 소감
백엔드 개발 지식이 없어 관련 엔드포인트 미구현과 자료구조에 대한 이해도 부족으로 이미지 리스트 구현에 어려움을 겪어 많은 시행착오를 경험하였습니다. 오로지 내 지식으로 백프로
구현은 힘들었지만 그래도 여러 과정들을 탐색해보아 좋은 기회였다고 생각합니다. 
리눅스에 대한 지식이 전무해 진행과정에 많은 어려움이 있었지만 백엔드에 대한 데이터가 다뤄지는 방법들과 대용량 Data 관리 및 다양한 서비스 API 개발도 알 수 있었으며
리눅스에 관한 공부를 더 할 수 있게 되는 계기가 되었습니다.
또한 빠르게 변화하는 프론트엔드 생태계에서 react.js 와 node.js , next.js 와 같은 원하는 기술들을 도입해보지 못한 것과 
병원 서비스의 보완 문제로 프로젝트를 전반적으로 공개하지 못하는 점이 에 대한 아쉬움이 남습니다.
prototype보다 class형 컴포넌트를 썼다면 코드가 좀 더 명료해지지 않았을까 하는 보완점들을 생각하게 되었습니다.
짧은 근무 기간이었지만 백엔드 프론트엔드를 동시에 경험할 수 있게 되어 복잡한 만큼 많은 고민들이 필요했고, 이를 하나하나 구현시도와 
만들어냄으로써 리눅스와 자바스크립트에 점점 더 익숙해질 수 있었습니다.
프로젝트를 통해 경험으로 녹여 낸 덕에 한층 자신감을 얻기도 했고, 백엔드와 프론트엔드 개발의 재미가 느껴졌던 기회였습니다.