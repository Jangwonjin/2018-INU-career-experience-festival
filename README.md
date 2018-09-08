# 2018 INU 진로체험 페스티벌
전공체험 등의 기회로 자기주도적인 진로진학 결정에 도움 제공
## 전자공학과 실습 내용
라즈베리파이와 파이카메라를 이용한 얼굴인식 실습
### 순서
1. 얼굴 인식
1. 사용자의 얼굴 데이터 수집
1. 사용자의 얼굴 학습
1. 사용자의 얼굴 인식 확인
### 실습
1. **얼굴 인식**<br>
   실시간으로 촬영중인 영상속에서 얼굴을 인식한다.
```bash
pi@raspberrypi:~ $ cd INUfestival
pi@raspberrypi:~ $ python3 face_detection.py
```
2. **사용자의 얼굴 데이터 수집**<br>
   사용자의 얼굴을 촬영하여 데이터를 수집한다.
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
   1. esc키를 누른후 :wq 입력 후 enter (저장 후 종료)
```bash
pi@raspberrypi:~ $ python3 face_dataset.py
```

