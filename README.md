# <img style="width: 100px; height: 60px" src="https://user-images.githubusercontent.com/78795820/192134549-a2a587e1-738a-4d93-a6a8-97e2a62ec8f7.png"/> Meet The Past(MTP)


# 주제 소개
### **Meet The Past** 

찢겨지고 구겨진 추억의 이미지가 있으신가요?
누군가의 기억과 가까운 모습으로
추억을 되살려드리겠습니다.

사진을 원형에 가까운 모습으로 복구해드리는 서비스를 이용해보세요


# 소프트웨어 아키텍처
![아키텍처](https://user-images.githubusercontent.com/78795820/192134673-b2f32442-146a-4fb9-ad14-8c69c875b332.png)



# 기술스택 
## **:zap: Tech Stack**
```
- Frontend: React, typescript, redux
- Backend : Django, Django-Rest-FrameWork
- Web Server: Nginx
- WSGI: Gunicorn
- Database: postgreSql
- AI : pytorch, dlib, OpenCV
- DB : postgresql
- Deployment: Docker, AWS EC2, AWS S3
- API Test : Postman
- API Documentation : Swagger
- monitoring : prometheus, grafana
```
|Frontend|Backend|AI|DevOps|Other|
|:------:|:------:|:---:|:----:|:---:
|![TypeScript](https://img.shields.io/badge/typescript-3178C6?style=for-the-badge&logo=typescript&logoColor=black)<br>![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)<br>![Redux](https://img.shields.io/badge/Redux-764ABC?style=for-the-badge&logo=Redux&logoColor=black)|![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=Django&logoColor=white)<br>![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=Redis&logoColor=black)<br>![Rabbitmq](https://img.shields.io/badge/RabbitMQ-FF6600?style=for-the-badge&logo=RabbitMQ&logoColor=black)<br>![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white)<br>![Celery](https://img.shields.io/badge/Celery-37814A?style=for-the-badge&logo=Celery&logoColor=black)<br>![postgreSql](https://img.shields.io/badge/PostgreSQL-white?logo=PostgreSQL)<br>|![dlib](https://img.shields.io/badge/dlib-darkgreen.svg?style=for-the-badge&logo=dlib&logoColor=white)</br>![pytorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=PyTorch&logoColor=black)<br>![OpenCV](https://img.shields.io/badge/opencv-%23white.svg?style=for-the-badge&logo=opencv&logoColor=white)|![Colab](https://img.shields.io/badge/colab-%F9AB00.svg?style=for-the-badge&logo=googlecolab&logoColor=white)</br>![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white)<br>![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)<br>![S3](https://img.shields.io/badge/AmazonS3-569A31?style=for-the-badge&logo=amazon%20s3&logoColor=black)<br>![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)|![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=Postman&logoColor=white)<br>![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)<br>![prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=Prometheus&logoColor=black)<br>![grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=Grafana&logoColor=black)<br>![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge&logo=Swagger&logoColor=black)

## 4. 실행 방법

**Yarn 패키지 설치**  
```
git clone --recursive https://github.com/Meet-the-past/docker.git

cd docker/frontend
yarn
```

**AI module 설치** [(AI)](https://github.com/microsoft/Bringing-Old-Photos-Back-to-Life)
```
cd ../backend
mkdir ai
cd ai

cd Face_Enhancement/models/networks/
git clone https://github.com/vacancy/Synchronized-BatchNorm-PyTorch
cp -rf Synchronized-BatchNorm-PyTorch/sync_batchnorm .
cd ../../../
cd Global/detection_models
git clone https://github.com/vacancy/Synchronized-BatchNorm-PyTorch
cp -rf Synchronized-BatchNorm-PyTorch/sync_batchnorm .
cd ../../
Download the landmark detection pretrained model

cd Face_Detection/
wget http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2
bzip2 -d shape_predictor_68_face_landmarks.dat.bz2
cd ../
Download the pretrained model, put the file Face_Enhancement/checkpoints.zip under ./Face_Enhancement, and put the file Global/checkpoints.zip under ./Global. Then unzip them respectively.

cd Face_Enhancement/
wget https://github.com/microsoft/Bringing-Old-Photos-Back-to-Life/releases/download/v1.0/face_checkpoints.zip
unzip face_checkpoints.zip
cd ../
cd Global/
wget https://github.com/microsoft/Bringing-Old-Photos-Back-to-Life/releases/download/v1.0/global_checkpoints.zip
unzip global_checkpoints.zip
cd ../../../../
```

**Docker Start**  
```
docker-compose -f docker-compose.prod.yml up -d --build
```


## 5. 페이지 및 기능 소개

### [회원가입 & 로그인]
![로그인-회원가입](https://user-images.githubusercontent.com/78795820/192958170-cada15cf-b22a-41d3-afb9-664bab0d3398.gif)


### [메인 페이지]
![메인페이지-_online-video-cutter com_](https://user-images.githubusercontent.com/78795820/192958332-4624a12b-c750-4146-9c23-42712ed0c6eb.gif)

### [이미지 업로드]
![업로드1번-_online-video-cutter com_](https://user-images.githubusercontent.com/78795820/192958435-d840b15e-6d79-48d6-91d8-19e727dcdc2e.gif)

### [결과 페이지]
![결과페이지-_online-video-cutter com_](https://user-images.githubusercontent.com/78795820/192958453-d8d07ce0-3d08-4679-82a2-bac7b731471c.gif)

### [히스토리 페이지]
![히스토리페이지-_online-video-cutter com_](https://user-images.githubusercontent.com/78795820/192958460-708154e2-529f-406c-bc5b-7a3fcf6a2e05.gif)

### [반응형 CSS 적용]
![예시](https://user-images.githubusercontent.com/78795820/189389486-3532cb0c-14fe-478c-b21e-c895eabde211.gif)

## 6. 팀원
| Name    | 정태원 | 김건혁 | 이채현 | 박성빈 | 박수연 | 장아령 |
| ------- | ---- | ---- | ---- | ---- | ---- | ---- |
| Profile | <img width="200px" src="https://avatars.githubusercontent.com/u/78795820?v=4" />                               | <img width="200px" src="https://avatars.githubusercontent.com/u/87744606?v=4" />                               | <img width="200px" src="https://avatars.githubusercontent.com/u/68368104?v=4" />                               | <img width="200px" src="https://avatars.githubusercontent.com/u/103374034?v=4" />                               | <img width="200px" src="https://avatars.githubusercontent.com/u/93627156?v=4" />                               | <img width="200px" src="https://avatars.githubusercontent.com/u/65939213?v=4" />                               |
|Role| Team Leader, Frontend, Backend, Devops| Backend,Devops | Frontend | Backend,Devops | Backend,Devops | Backend, Devops |
| gitHub  | [teawon](https://github.com/teawon)                                     | [Hyeok](https://github.com/hyeokinen)                                   | [@chloe](https://github.com/chloe1129)                                       | [@SeongbinPark](https://github.com/SeongbinPark)                                 | [@PARK-Su-yeon](https://github.com/PARK-Su-yeon)                                 | [@aristo0922](https://github.com/aristo0922)                                 |


## 7. Reference
https://github.com/microsoft/Bringing-Old-Photos-Back-to-Life

https://medium.com/@dkfud2121/meet-the-past-mtp-9f3df63c4217

![Footer](https://capsule-render.vercel.app/api?type=waving&color=auto&height=200&section=footer)



