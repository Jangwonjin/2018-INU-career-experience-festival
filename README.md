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
1. 얼굴 인식<br>
   실시간으로 촬영중인 영상속에서 얼굴을 인식한다.
```bash
pi@raspberrypi:~ $ cd INUfestival
pi@raspberrypi:~ $ python3 face_detection
```
1. 사용자의 얼굴 데이터 수집<br>
   사용자의 얼굴을 촬영하여 데이터를 수집한다.
   1. 폴더 생성(User1,User2,User3 ...)
   ```bash
   pi@raspberrypi:~ $ cd dataset
   pi@raspberrypi:~ $ mkdir User*
   ```


