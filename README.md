# 한밭대학교 컴퓨터공학과

<img src="https://capsule-render.vercel.app/api?type=Wave&color=auto&height=250&section=header&text=챗봇%캡스톤&fontSize=90" />

**팀 구성**
- 20171612 박상현
- 20197132 주준하
- 20171768 남승완

## <u>Teamate</u> Project Background
- ### 필요성
  - 비대면 교육으로 형태가 변화하며 온라인 동영상 강의의 비중이 높아지고 있다.
  - 기계독해기반 질의응답 모델을 이용해 챗봇을 통해 온라인 강의 환경을 개선하고 이를 제공한다.

- ### 기존 해결책의 문제점
  - 현재 산업에서 많이 활용되는 챗봇은 정해진 규칙에 따라서 미리 준비한 답변을 제공하는 방법을 많이 채택한다. 
  - 이러한 규칙 기반 챗봇은 구현이 간단하고 정해진 답변을 하기 때문에 안정적이지만 정의된 규칙에 따라 답변하기 때문에 비슷한 질문을 이해하지 못하거나 예상치 못한 질문은 답변하지 못하는 경우가 빈번하다.
  - 또한 다양한 온라인 교육 서비스 이용은 편리함을 주기도 하지만 실시간 소통의 문제를 가지고 있다.
  
## System Design
  - ### Skill
    - <img src="https://img.shields.io/badge/React-61DAFB?style=flat&logo=React&logoColor=white"/> <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=CSS3&logoColor=white"/> <img src="https://img.shields.io/badge/Node.js-339933?style=flat&logo=Node.js&logoColor=white"/> <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=MongoDB&logoColor=white"/>
    - <img src="https://img.shields.io/badge/Flask-000000?style=flat&logo=Flask&logoColor=white"/>
    - <img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=Python&logoColor=white"/> <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=TensorFlow&logoColor=white"/>
    
  - ### Web System 
  
     - #### 프로젝트 개요
      - 강의자는 강의와 교안을 업로드 하고 수강자는 기계독해 챗봇을 통해 강의에 대한 질의 응답을 수행 할수 있다.
      ![프로잭트 개요](https://user-images.githubusercontent.com/77065758/206148602-29d0df01-7aa9-4894-a814-44d9af85d374.PNG)
      
    - #### 웹 시스템 디자인
      - React를 이용해 Client를 구성하고 강의, 수강 관리 server는 Node, MongoDB로 구성. 챗봇 서버는 Flask를 이용해 구현
      ![프로젝트 시스템](https://user-images.githubusercontent.com/77065758/206148910-ba645b77-3f55-4ba4-a0da-d1cd76490b9b.PNG)
      
      - #### 강의 업로드
        ![강의 업로드](https://user-images.githubusercontent.com/77065758/206151041-f62e4902-a3e8-43cd-bee3-da30c25da43b.PNG)
        
      - #### 강의 목록
        ![강의 목록](https://user-images.githubusercontent.com/77065758/206151511-da4b908f-5326-4646-b717-5ff05a8f4f67.PNG)
   
  - ### System Requirements
    
    - #### 전체 시스템 구성도
      ![기능](https://user-images.githubusercontent.com/77065758/205566507-facab19c-1ba0-4d74-9467-c562643e8040.png)
   
    - #### 기능별 상세 요구사항
      ![시스템기능도](https://user-images.githubusercontent.com/77065758/205566586-425eb0c8-41e6-4d9a-9320-36fdd8efa629.png)
      
    - #### 위키피디아 기계독해
      ![PDFMRC](https://user-images.githubusercontent.com/77065758/205566623-6231fd56-d1ae-4ee8-9841-08c156c76e76.png)
      
    - #### PDF 기계독해
      ![WIKIMRC](https://user-images.githubusercontent.com/77065758/205566643-d9a7c793-628c-4fa5-a733-6648e718d59a.png)
  
## Case Study
  - ### Description
    - 한국어 기계독해를 위한 표준 데이터셋으로는 KorQuAD 1.0을 이용.
      - #### 데이터셋 구성
        ![KorQaud 데이터셋](https://user-images.githubusercontent.com/77065758/206151557-e4482d1d-61b7-4a44-b60e-388f7fca20f4.PNG)
    - 문장형 답변을 포함하는 298쌍의 추가 데이터 셋을 구축하여 추가로 fine-tuning을 진행.
    - 구글에서 개발한 자연어 처리 언어모델 BERT를 이용해 데이터를 양방향으로 학습.
      - #### BERT
        ![bert](https://user-images.githubusercontent.com/77065758/206151609-4e98a2ec-b90e-4db4-a091-b86574961be9.PNG)
  
## Conclusion
  - ### 실험 환경
    - 298쌍의 질의응답을 228/70쌍으로 분할하고 학습과 테스트에 교차 적용하여 실험을 진행.
    - 문장형 답변 179개, 단답형 답변 49개로 구성되어 있고, 70쌍의 질의응답은 문장형 답변 51개, 단답형 19개로 구성.
  - ### 성능 및 테스트
    - ![성능](https://user-images.githubusercontent.com/77065758/205581470-40550c63-80d5-470b-b394-5b45c4b2a5f2.png)
  - ### 결과
    - #### 응답 형식
      ![응답 형식](https://user-images.githubusercontent.com/77065758/205581462-a3e3ea08-9816-4b84-b8c6-4ac556cf015e.png)
      - 문장형 답변을 학습한 모델은 상대적으로 답변을 문장형으로 예측하는 결과
    - #### 챗봇 페이지
      ![결과](https://user-images.githubusercontent.com/77065758/205577447-2367f07f-9fcb-4158-bbe3-8bca9c03e98e.png)
  - ### 기대효과
    - 위키피디아와 강의 자료를 통한 기계독해 수강자들은 그전에는 어려웠던 즉각적인 소통을 기대할 수 있다.
    - 적은 양의 문장형 데이터셋을 이용하여도 성능향상을 기대할 수 있다.
    - 온라인 교육환경에서 다양한 과목에 대하여 챗봇 시스템을 이용할 수 있다.

## Project Outcome
- ### 2022년 제34회 한글 및 한국어 정보처리 학술대회 포스터발표
  - 교육환경에서의 기계독해 기반 질의응답 시스템. 주준하, 박상현, 남승완, 임경태 (한밭대학교) [논문다운로드](https://drive.google.com/file/d/1NOINmf4DOXgueN9zqvTRbq4rVj-EjzIa/view?usp=share_link)
- ### 2022년 한밭대학교 컴퓨터공학과 캡스톤디자인 작품전시회
  ![패널](https://user-images.githubusercontent.com/77065758/206153465-1be6ec72-7b3a-4a69-a70f-af63cd59de7c.PNG)
