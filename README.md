# SAI-2nd_Competition

<br>
<hr>

## 1. Competition
 - Jigsaw Unintended Bias in Toxicity Classification
 - https://www.kaggle.com/c/jigsaw-unintended-bias-in-toxicity-classification

<br>

## 2. Team Briefing
 - Simple CuDNNGRU [Python + Keras]
 - Newbie Tutorial - Jigsaw Unintended Bias Basic EDA

<br>


## 3. Experiment Result
### (1) 서기원

| Experiment | Score | Date |
|---|:---:|---:|
| Original Kernel : Simple CuDNNGRU [Python + Keras] | 0.92271 | 2019.05.30 |
| MaxPool + AvgPool => MaxPool | 0.92386 | 2019.05.30 |
| MaxPool, Dropout 0.2 => Dropout 0.1 | 0.92063 | 2019.05.30 |
| MaxPool, relu | 0.92267 | 2019.05.31 |
| MaxPool, relu, relu | 0.92167 | 2019.06.01 |

#### 1. 튜닝 값 : 하이퍼파라미터 튜닝이 아닌, 모델 자체의 층 구성을 바꿔보려고 노력했다.
 - AvgPool : 윈도우에서 평균값을 선택. Average pooling은 DNN에서 성능이 좋지 못하다. 활성화 함수 relu를 쓸 때 0이 많이 나오면 강한 자극의 영향이 줄어드는 효과가 발생하기 때문이다.
 - MaxPool : 윈도우에서 최고값을 선택. Max pooling은 average pooling과 같은 문제는 없지만 overfitting이 될 수 있다.
 - Dropout : Dropout은 네트웍의 일부를 생략하고 학습을 진행한다. 생략한 네트웍은 학습에 영향을 끼치지 않게 된다. 무작위 뉴런 생략을 통한 overfitting 방지!
 - Relu : ReLU가 음수들을 모두 0으로 처리하기 때문에 한번 음수가 나오면 더이상 그 노드는 학습되지 않는다는 단점이 한가지 생긴다.
 
#### 2. 참고
 - http://machinelearningkorea.com/2019/05/18/%EA%B0%84%EB%8B%A8%ED%95%9C-gru%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%9C-%ED%9B%88%EB%A0%A8-%EC%98%88-%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EC%B9%98%ED%8A%B8%EC%BD%94%EB%93%9C/
 - http://blog.naver.com/laonple/220830178487
 - http://blog.naver.com/laonple/220818841217
 - https://m.blog.naver.com/zzing0907/220693996517

  
#### 3. 분석
 - MaxPool + AvgPool로 구성된 것을 MaxPool로 구성했더니 성능이 조금 올라갔다. DNN에서는 AvgPool이 성능이 좋지 않을 수 있다는 연구가 있었다.
 - Dropout을 0.2에서 0.1로 줄여 봤더니 성능이 떨어졌다. Overfitting?
 - 모델에 다양한 층을 쌓으며 실험중
 - 은닉층의 활성화 함수로 relu를 쌓을 수록 성능이 떨어졌다. 넓은 신경망 / 깊은 신경망 등 층 쌓는 법 공부 필요!

<br>
<br>


<br>

## 4. Team Score

| Rank/Total | Team | Date |
|---|:---:|---:|
| 1844/2403 | SJU-SAI | 2019.06.01 |
