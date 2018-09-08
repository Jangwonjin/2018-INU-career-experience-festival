# 2018 INU 진로체험 페스티벌
전공체험 등의 기회로 자기주도적인 진로진학 결정에 도움 제공

## 강의
* 주제: 누구나 쉽게 쓰는 인공지능 기술
* [강의자료](INU_Festival_인공지능_v3.pdf)

## 전자공학과 실습 내용
라즈베리파이와 파이카메라를 이용한 얼굴인식 실습(python, Opencv 활용)
### 순서
1. 얼굴 인식(face detection)
1. 사용자의 얼굴 데이터 수집
1. 사용자의 얼굴 학습
1. 사용자의 얼굴 인식(face recognition)
### 실습
1. **사전 준비**<br>
* 카메라 준비<br>
   라즈베리카메라는 usb타입이 아니라서 opencv에서 자동으로 장치인식이 불가, 다음과 같이 장치를 인식 시켜준다.
```bash
pi@raspberrypi:~ $ sudo modprobe bcm2835-v4l2
```
2. **얼굴 인식**<br>
```bash
pi@raspberrypi:~ $ cd INUfestival
pi@raspberrypi:~/INUfestival $ python3 face_detection.py
```
3. **사용자의 얼굴 데이터 수집**<br>
   * 폴더 생성(User1,User2,User3 ...)
   ```bash
    pi@raspberrypi:~/INUfestival $ mkdir dataset (dataset 폴더생성)
    pi@raspberrypi:~/INUfestival $ cd dataset
    pi@raspberrypi:~/INUfestival/dataset $ mkdir User*
    ```
    * 폴더 삭제(사용자 제거)
    ```bash
    pi@raspberrypi:~ $ rm -rf 폴더명
    ```
    * (필요시)저장할 사진의 갯수 설정
    ```bash
    pi@raspberrypi:~/INUfestival $ vi face_dataset.py
    ```
    1. esc키를 누른 후 :34 입력 후 enter (34번째 줄로 이동)
    1. i키를 누른 후 우측으로 이동 count >= 10 에서 10을 원하는 장수로 변경
    1. esc키를 누른 후 :wq 입력 후 enter (저장 후 종료)<br>

* **파일 실행**<br>
    * 파일 실행 시 enter user id... 라는 문구가 출력된다. 1을 입력후 엔터
    (이 후 새로운 사용자 등록시 2,3,4 순으로 등록)<br>
    (해당 id에 일치하는 INUfestival/dataset/User\* 폴더 생성 후 파일 실행)
```bash
pi@raspberrypi:~ $ python3 face_dataset.py
```
data 확인(터미널에서 파일 확인)
```bash
pi@raspberrypi:~/INUfestival $ cd dataset
pi@raspberrypi:~/INUfestival/dataset $ cd User*
pi@raspberrypi:~/INUfestival/dataset/User* $ ls
```
이 후 파일 탐색기를 이용하여 해당 해당 경로로 이동하여 데이터를 확인한다.

4. **사용자의 얼굴 학습**
학습파일 저장을 위한 폴더 생성
```bash
pi@raspberrypi:~/INUfestival $ mkdir trainer
```
파일을 실행하여 학습 진행
```bash
pi@raspberrypi:~/INUfestival $ python3 face_train.py
```

5. **사용자의 얼굴 인식**
사용자의 이름 등록
```bash
pi@raspberrypi:~/INUfestival $ vi face_recognizer.py
```
    1. esc키를 누른 후 :16 입력 후 enter(16번째 줄로 이동)
    2. i키를 누른 후 우측으로 이동 ['None','zoonyoung']를 ['None','사용자1','사용자2',...]로 수정한다. 
파일실행
```bash
pi@raspberrypi:~/INUfestival $ python3 face_recognizer.py
```

