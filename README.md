# rehabilitation-exercise-program
![image](https://github.com/HyejiYu/rehabilitation-exercise-program/assets/65165556/0c6cb568-5a19-46bd-8697-7bc6b5b1c2f5)
![image](https://github.com/HyejiYu/rehabilitation-exercise-program/assets/65165556/3d28fc03-ab21-42b8-8aa6-6b2abc537f9f)
파이썬의 **mediapipe**를 활용하여 제작된 수부 부상에 대한 재활 프로그램입니다. 동작을 인식하여 올바르게 동작을 했다면 count가 올라가고, 그렇지 않다면 정확하게 동작을 해달라고 출력합니다.

# Requirement
- python 3.7.1 (3.9 이하)
- tensorflow 2.7.0 (2.x)
- colab 환경에서 웹캠 사용 및 창 띄우기 불가능

# keypoint_logging(56frame).ipynb
-각 동작의 왼손, 오른손을 라벨링하여 동작 
- 56frame으로 고정
- 0. Wrist 점을 X:0, Y:0로 정의 하여 상대 위치 기록
- 정규화
- csv 파일로 저장

# data_preprocessing.ipynb
- 56frame보다 길거나 짧은 데이터 처리
- 하나의 파일로 취합

# keypoint_classification.ipynb
- 분류 모델 학습
- lstm(선택), DNN, CNN
- tensorflow 모델로 변환
  
# keypoint_classifier_2d.py
- keypoint_logging 파일에서 모드를 변환하면 동작 인식모드로 사용가능
- keypoint_logging에서 넘겨주는 데이터를 keypoint_classification에서 학습시킨 모델에 넣어 해당 동작의 추정 정도를 그래프로 그림
- 그래프에 피크가 생기면 동작을 한 번 한 것으로 판단, 피크값을 기준으로 동작의 정확도 평가








