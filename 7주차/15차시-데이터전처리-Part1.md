# 데이터 전처리 Part1

## 1) 넘파이로 데이터 준비하기
```
1. 𝑘-NN 알고리즘을 사용할 때는 특성들 사이의 스케일 (Scale)을 맞춰야 합니다.
2. 넘파이의 column_stack() 함수를 이용하여 fish_length와 fish_weight를 합칩니다.
3. np.ones()와 np.zeros() 함수를 이용하여 타겟 데이터를 만듭니다.
```

## 2) 사이킷런으로 학습 데이터셋과 시험 데이터셋 나누기
```
1. train_test_split()함수 : 학습 데이터셋과 시험 데이터셋으로 나누어 주고 나누기 전에 알아서 섞어 준다.
2. from sklearn.model_selection import train_test_split 으로 불러오기
3. train_input, test_input, train_target, test_target = train_test_split(fish_data, fish_target, random_state=42)
4. fish_data -> trian_input, test_input, fish_target -> train_target, test_target (기본적으로 25%를 시험 데이터셋으로 떼어낸다.)
5. 무작위로 데이터를 나누었을 때 샘플이 골고루 섞이지 않으면 샘플링 편향이 발생 할 수 있다.
6. 해결방법: stratify 매개변수에 타깃 데이터를 전달하면 클래스 비율에 맞게 데이터를 나누게 된다.
7. train_input, test_input, train_target, test_target = train_test_split(fish_data, fish_target, random_state=42, stratify=fish_target)
```
