# Robotarm Automation

## 프로젝트 개요

한동대학교 Industrial AI and Automation (IAIA) 수업에서 진행한 팀 프로젝트로,
INDY 10 산업용 로봇팔과 YOLOv5 객체 인식을 결합하여 신발을 자동으로 분류 및 보관하는 시스템입니다.

- **Subject** : Automated shoes organizing system implementation
- **Date** : Spring semester, 2023
- **Instructor** : Prof. Young-Keun Kim
- **Robot** : INDY 10
- **OS** : Ubuntu 20.04

## Demo

https://github.com/user-attachments/assets/fd15c0b4-6c97-4642-a6bc-30854a885138

---

## 시스템 구조

```
카메라 입력
    │
    ▼
YOLOv5 Detection Node (yolov5_ros.py)
    │  ROS Topic: shoeFlag / modeSelect / taskfinish
    ▼
Robot Control Node (projectRobotactual.py)
    │  Serial
    ▼
Arduino (Display)      INDY 10 Robot Arm
```

카메라로 신발을 인식하고, ROS 토픽을 통해 로봇 제어 노드와 통신하여 자동으로 보관/반출 작업을 수행합니다.

---

## 담당 역할

- **YOLOv5 모델 개발** : 신발 객체 인식 커스텀 모델 학습 및 ROS 노드 구현 (`yolov5_ros.py`)
- **로봇-카메라 통신 연동** : YOLOv5 검출 결과를 ROS 토픽으로 로봇 제어 노드에 전달하는 인터페이스 설계 (`projectRobotactual.py`)

---

## 기술 스택

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![YOLOv5](https://img.shields.io/badge/YOLOv5-00CCCC?style=for-the-badge)
![ROS](https://img.shields.io/badge/ROS-22314E?style=for-the-badge&logo=ros&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)

---

## 프로젝트 구성

- `source/` : 소스 코드
  - `yolov5_ros.py` : YOLOv5 ROS 검출 노드
  - `projectRobotactual.py` : 로봇 제어 및 카메라 통신 노드
  - `projectFunctions.py` : 공통 유틸리티 함수
  - `projectjointDef.py` : 로봇 관절 경로 정의
  - `arduino code/arduinoDisplay.ino` : 아두이노 디스플레이 코드
- `md files/` : 프로젝트 설명 문서 (설치 매뉴얼, 딥러닝 설정 가이드)
- `hardware file/` : CAD 파일
- `presentation file/` : 발표 자료
- `demo video/` : 시연 영상

---

## 참고

- 원본 팀 레포지토리 : [HanMinung/Robotarm_Automation](https://github.com/HanMinung/Robotarm_Automation)
