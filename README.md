# IN_OUT
> 깜빡깜빡 : Facial landmark와 CNN을 이용한 안구건조증 예방 서비스

아래 사진 클릭 시 서비스 발표 영상으로 이동합니다 😝

![발표영상](https://img.youtube.com/vi/Qiv-UJnBunE/0.jpg)

------

## 개발 필요성

스마트폰 사용이 점점 늘어남에 따라 수면장애, 목 통증, 안구건조증, 시력약화 등의 문제가 발생한다. 특히 안구건조증은 2015년 과학기술정보통신부에 따르면 20%의 문제를 차지할 만큼 심각하다. 건강심사평가원 자료에 따르면, 안구건조증으로 의료기관을 찾은 국내 환자는 2015년 215만여 명, 2016년 225만여 명, 2017년 231만여 명, 2018년 257만여 명, 2019년 268만 명 등으로 매년 크게 증가하고 있다. 안구건조 증세로 불편하지만 병의원을 찾지 않은 사람들까지 합하면 숫자는 훨씬 더 커질 것이다. 따라서 안구건조증 예방 및 해결방안의 필요성이 증가하였다.

------

## 개발 목표

카메라로 사용자의 얼굴을 인식하고 눈 깜빡임 및 분당 깜빡임 횟수를 측정하여 알려준다. 사용자의 눈깜빡임 횟수가 적어질 경우, 안구 건조증 예방을 위해 사용자에게 알림을 주는 시스템을 개발한다.

<img width="509" alt="image" src="https://user-images.githubusercontent.com/60170358/154834805-79ad3336-1dee-4e56-be5e-2f561c0e4df0.png">

<정상적인 깜빡임>

<img width="527" alt="image" src="https://user-images.githubusercontent.com/60170358/154834812-415ff1a2-434e-4d58-8f22-a8613fd8da96.png">

<깜빡임이 적은 상태>

------

## 구현 기술

### Facial Landmark를 통한 dataset 생성

<img width="599" alt="image" src="https://user-images.githubusercontent.com/60170358/155846628-c7612292-f6b1-40a5-8a0f-0dc80ee81829.png">

Facial landmark 오픈소스를 이용해 얼굴 영역을 인식한 다음 눈, 코, 입 등의 facial landmark를 도출한다. 그중 눈 부분을 추출하여 data normalization을 거친 다음 전처리와 augmentation 과정을 통해 데이터를 생성하고 dataset을 만든다.



### CNN

<img width="548" alt="image" src="https://user-images.githubusercontent.com/60170358/155846824-b6e1e60b-5c5e-46cb-8be5-13c6c596fd1d.png">

위와 같은 구조로 구성된 CNN 네트워크로 눈 깜빡임 인식을 학습시킨다. 

------

## 기대 효과

1. 소리나 진동과 같은 비시각적 요소를 통한 알림으로 알림 시스템을 보안시켜 사용자에게 명확한 알림을 줄 수 있다.
2. 앱으로 구현하여 스마트폰과 같은 기기에서도 사용이 가능하게 만들 수 있다.
3. 움직임이 심하거나 얼굴 각도가 틀어질 때, 또한 마스크를 쓰고 있을 때 측정이 불가하지만,다양한 얼굴각도의 dataset을 수집해 학습시켜 보완된 모델을 생성할 수 있다.

------



## 참고 문헌

Pothuraju Vishesh,"Eye blink detection using CNN to detect drowsiness level in drivers for road safety", Indonesian Journal of Electrical Engineering and Computer Science,Vol. 22, No. 1, April 2021, pp. 222~231



Young-Joo Han,"Efficient Eye-Blinking Detection on Smartphones: A Hybrid Approach Based on Deep Learning",Hindawi Mobile Information Systems,Volume 2018, Article ID 6929762, 8 pages

Cian Ryan,"Real-Time Face & Eye Tracking and Blink Detection using Event Cameras ",Neural Networks,Volume 141, September 2021, Pages 87-97
