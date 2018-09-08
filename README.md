# 2018 INU 진로체험 페스티벌
전공체험 등의 기회로 자기주도적인 진로진학 결정에 도움 제공
## 전자공학과 실습 내용
라즈베리파이와 파이카메라를 이용한 얼굴인식 실습
### 순서
1. 얼굴 인식(face detection)
1. 사용자의 얼굴 데이터 수집
1. 사용자의 얼굴 학습
1. 사용자의 얼굴 인식(face recognition)
### 실습
1. **사전 준비**<br>
* 카메라 준비<br>
   라즈베리카메라는 usb타입이 아니라서 opencv에서 자동으로 장치인식이 불가, 다음과 같이 장치 인식
```bash
pi@raspberrypi:~ $ sudo modprobe bcm2835-v4l2
```
2. **얼굴 인식**<br>
```bash
pi@raspberrypi:~ $ cd INUfestival
pi@raspberrypi:~ $ python3 face_detection.py
```
3. **사용자의 얼굴 데이터 수집**<br>
   * 폴더 생성(User1,User2,User3 ...)
   ```bash
    pi@raspberrypi:~ $ cd dataset
    pi@raspberrypi:~ $ mkdir User*
    ```
    * (필요시)저장할 사진의 갯수 설정
    ```bash
    pi@raspberrypi:~ $ cd ..
    pi@raspberrypi:~ $ vi face_dataset.py
    ```
    1. esc키를 누른후 :34 입력 후 enter (34번째 줄로 이동)
    1. i키를 누른후 우측으로 이동 count >= 10 에서 10을 원하는 장수로 변경
    1. esc키를 누른후 :wq 입력 후 enter (저장 후 종료)<br>

* **파일 실행**
```bash
pi@raspberrypi:~ $ python3 face_dataset.py
```
data 확인(터미널에서 파일 확인)
```bash
pi@raspberrypi:~ $ cd dataset
pi@raspberrypi:~ $ cd User*
pi@raspberrypi:~ $ ls
```
이 후 파일 탐색기를 이용하여 해당 해당 경로로 이동하여 데이터를 확인한다.

4. 사용자의 얼굴 인식

