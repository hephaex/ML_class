# 온수당 Machine Learing Note (week #6)
* Advice for applying machine learning
* progress: 6 주차
*
* date: 2016.05.31

* Note:
 - 1주와 2주는 supervised learing 에서 Linear Regression(선형 회귀)을 공부했습니다.
 - 3주는 classification(군집화)에 대하여 공부했습니다.
 - 4주는 기계학습에서 사용하는 신경망(neural network)을 공부했습니다.
 - 5주는 신경망이 어떻게 학습을 하는지에 대하여 공부합니다.
 - 5주차 이후 중간 복습하는 시간을 가졌습니다. 
 - 6주차에서는 기계학습에 도움될 여러가지 것을 공부합니다. 
 
## Week6 contents
ᆿ* Evaluating a Learning Algorithm
> Deciding What to Try Next
>
> Evaluating a Hypothesis
>
> Model Selection adn Train/ᆶᆼValidation/Test Sets

* Bias vs. Variance
> Diagnosing Bias vs. Variance
>
> Regulatization and Bias/Variacne
>
> Learning Curves
>
> Deciding Waht to do Next Revisited

* Building a Spam Classifier
> Prioritizing What to Work On
>
> Error Analysis

* Handling Skewed Data
> Error Metrics for Skwed Classes
>
> Trading Off Precision and Recall

* Using Large Data Sets
> Data For Machine Learning

## Evaluating a Learning Algorithm
지도 학습의 방법으로 Linear Regression (선형회기) 와 logistic Regression(구분), Neural netowrk 을 배웠다.

어떤 것을 배워서 아는 것과 그것을 응용하여 무엇인가 만들어 보는 행동은 큰 차이가 있다. 
지금까지 배운 기계학습 방법을 응용하여 무언가 만들 때 필요한 기술은 많은 종류가 있는데
이번주는 그것에 대하여 배워보자. 

### Deciding What to Try Next
집값을 기계학습으로 예측할 때 regularized linear regression 을 다음과 같은 수식으로 정의하였다.
![01-01](https://github.com/hephaex/ML_class/blob/master/week6/week6_01_decidingWhatToTryNext_01.png)

가설을 세우고 학습을 시키면서 예상하지 못했던 것과 거기서 발생하는 오류를 만나게 될 것이다. 
이것을 해결하려면 어떻게 해야 할까?

* Get more training examples
 - 학습할 데이터를 늘린다.
 - 데이터를 늘린다고 해서 항상 도움이 되지는 않는다.
 - 데이터 수를 늘릴지 아니면 다른 것으로 개선할지 결정하는 방법을 배워보자. 
 
* Try smaller sets of features
 - 영향을 주는 요소를 줄여가 보자. 
 - 결과에 영향을 요소가 영향을 주는지 아닌지 아는 것은 어렵다. 
 - 어떨때 결과에 영향을 주는 핵심 요소만 뽑을 수 있는지 배워보자.
* Try getting additional features
 - 영향을 주는 요소가 부족할 수도 있다. 
 - 어떨때 결과에 영향을 주는 요소를 늘려가야만 하는지 배워보자.
* Try adding polynominal features (ᆹᆻx1^2 , x2^2, x1*x2, ,,, etc)
 - 가설 함수에 고차항을 추가 하는 것이 도움이 될 수도 있다. 
 - 어떻 때 고차항을 추가하는 것이 도움이 될지 배워보자.
* Try decreasing LAMDA (λ)
 - regularization 항을 계산하여 바꿔보자. 
* Tyr increasing LAMDA (λ)
 - regularization 항을 계산하여 바꿔보자. 

### Evaluating a Hypothesis
집값에 대하여 영향을 주는 가설 함수를 세우기 위해서 여러가지를 요소를 가정할 수 있다. 
* x1: size of house
* x2: no. of bedrooms
* x3: no. of floors
* x4: age of house
* x5: average income in neighborhood 
* x6: kitchen size
* ...
* x100: xxx

이 것을 바탕으로 x1, x2, x3, x4 가 중요한 영향을 준다고 가설을 세우고 가설함수를 다음처럼 세웠다고 하자. 
![02-02](https://github.com/hephaex/ML_class/blob/master/week6/week6_02_EvaluatingAHypothesis_02.png)

그리고 가설에 대하여 그래프로 (x: size, y: price) 에 따라서 그려보자. 
![02-01](https://github.com/hephaex/ML_class/blob/master/week6/week6_02_EvaluatingAHypothesis_01.png)

여기서 이 가설 함수가 최적이라고 할 수 있을까? 
최적이라면 어떻게 그것을 알 수 있을까?

가설 함수를 학습 시키는 것처럼 가설 함수를 시험해 보는 것도 필요하다. 

우리가 수집한 데이터를 가지고 학습(training set) 과 시험(test set) 을 사용해야 할 것이다. 
* 70%는 학습에 사용 (ᇂTraining set: 70%)
* ᆸ30%는 시험에 사용 (Test set: 30%)
![02-03](https://github.com/hephaex/ML_class/blob/master/week6/week6_02_EvaluatingAHypothesis_03.png)

학습에 사용할 데이터와 시험에 사용할 데이터는 잘 썪어야만 학습과 시험에 대한 오류를 줄 있수 있다. 

잘 학습되었는지 비용함수로 알아보았듯이, 
시험이 잘 되었는지 시험에 대한 비용함수를 만들어서 알아 볼 수 있다. 


학습에 대한 비용함수와 똑같이 시험에 대한 비용 함수도 square error 를 측정으로 계산할 수있다. 
![02-04](https://github.com/hephaex/ML_class/blob/master/week6/week6_02_EvaluatingAHypothesis_04.png)


linear regression 에서 학습과 시험에 대한 비용함수를 계산하였듯이, 
logistic regression 에서도 똑같이 학습과 시험에 대한 비용함수를 계산 할 수 있다. 

![02-07](https://github.com/hephaex/ML_class/blob/master/week6/week6_02_EvaluatingAHypothesis_07.png)


logistic regression에서 오류는 가설h(θ)에 대한 결과 y의 오류 함수가 될 것이다. 
이것을 수식으로 정리하면 다음이 된다. 
![02-05](https://github.com/hephaex/ML_class/blob/master/week6/week6_02_EvaluatingAHypothesis_05.png)

> hθ(x) > 0.5 일 때 예상한 결과는 1이지만 결과가 0이 나왔다면 오류이다. 
> 
> hθ(x) < 0.5 일 때 예상한 결과는 0이지만 결과가 1이 나왔다면 오류이다. 

시험에 대한 오류도 학습에 대한 오류를 계산하는 것과 똑같이 수식을 세우고 계산할 수 있다.
![02-06](https://github.com/hephaex/ML_class/blob/master/week6/week6_02_EvaluatingAHypothesis_06.png)


### Model Selection adn Train/ᆶᆼValidation/Test Sets
![03-01](https://github.com/hephaex/ML_class/blob/master/week6/week6_03_ModelSelectionAndTrainingValidatingTest_01.png)
![03-02](https://github.com/hephaex/ML_class/blob/master/week6/week6_03_ModelSelectionAndTrainingValidatingTest_02.png)
![03-03](https://github.com/hephaex/ML_class/blob/master/week6/week6_03_ModelSelectionAndTrainingValidatingTest_03.png)
![03-04](https://github.com/hephaex/ML_class/blob/master/week6/week6_03_ModelSelectionAndTrainingValidatingTest_04.png)
![03-05](https://github.com/hephaex/ML_class/blob/master/week6/week6_03_ModelSelectionAndTrainingValidatingTest_05.png)
![03-06](https://github.com/hephaex/ML_class/blob/master/week6/week6_03_ModelSelectionAndTrainingValidatingTest_06.png)

## Bias vs. Variance

### Diagnosing Bias vs. Variance
![04-01](https://github.com/hephaex/ML_class/blob/master/week6/week6_04_DiagnosingBiasVSVariance_01.png)
![04-02](https://github.com/hephaex/ML_class/blob/master/week6/week6_04_DiagnosingBiasVSVariance_02.png)
![04-03](https://github.com/hephaex/ML_class/blob/master/week6/week6_04_DiagnosingBiasVSVariance_03.png)
![04-04](https://github.com/hephaex/ML_class/blob/master/week6/week6_04_DiagnosingBiasVSVariance_04.png)
![04-05](https://github.com/hephaex/ML_class/blob/master/week6/week6_04_DiagnosingBiasVSVariance_05.png)
![04-06](https://github.com/hephaex/ML_class/blob/master/week6/week6_04_DiagnosingBiasVSVariance_06.png)
![04-07](https://github.com/hephaex/ML_class/blob/master/week6/week6_04_DiagnosingBiasVSVariance_07.png)

### Regulatization and Bias/Variacne

![05-01](https://github.com/hephaex/ML_class/blob/master/week6/week6_05_RegularizationAndBiasVariance_01.png)
![05-02](https://github.com/hephaex/ML_class/blob/master/week6/week6_05_RegularizationAndBiasVariance_02.png)
![05-03](https://github.com/hephaex/ML_class/blob/master/week6/week6_05_RegularizationAndBiasVariance_03.png)
![05-04](https://github.com/hephaex/ML_class/blob/master/week6/week6_05_RegularizationAndBiasVariance_04.png)
![05-05](https://github.com/hephaex/ML_class/blob/master/week6/week6_05_RegularizationAndBiasVariance_05.png)

### Learning Curves

![06-01](https://github.com/hephaex/ML_class/blob/master/week6/week6_06_LearningCurves_01.png)
![06-02](https://github.com/hephaex/ML_class/blob/master/week6/week6_06_LearningCurves_02.png)
![06-03](https://github.com/hephaex/ML_class/blob/master/week6/week6_06_LearningCurves_03.png)
![06-04](https://github.com/hephaex/ML_class/blob/master/week6/week6_06_LearningCurves_04.png)
![06-05](https://github.com/hephaex/ML_class/blob/master/week6/week6_06_LearningCurves_05.png)
![06-06](https://github.com/hephaex/ML_class/blob/master/week6/week6_06_LearningCurves_06.png)
![06-07](https://github.com/hephaex/ML_class/blob/master/week6/week6_06_LearningCurves_07.png)

### Deciding Waht to do Next Revisited

![07-01](https://github.com/hephaex/ML_class/blob/master/week6/week6_07_DecidingWhatToTryNext_01.png)
![07-02](https://github.com/hephaex/ML_class/blob/master/week6/week6_07_DecidingWhatToTryNext_02.png)
![07-03](https://github.com/hephaex/ML_class/blob/master/week6/week6_07_DecidingWhatToTryNext_03.png)

## Building a Spam Classifier

### Prioritizing What to Work On

![08-01](https://github.com/hephaex/ML_class/blob/master/week6/week6_08_PrioritizingWhatToWorkOn_01.png)
![08-02](https://github.com/hephaex/ML_class/blob/master/week6/week6_08_PrioritizingWhatToWorkOn_02.png)
![08-03](https://github.com/hephaex/ML_class/blob/master/week6/week6_08_PrioritizingWhatToWorkOn_03.png)
![08-04](https://github.com/hephaex/ML_class/blob/master/week6/week6_08_PrioritizingWhatToWorkOn_04.png)
![08-05](https://github.com/hephaex/ML_class/blob/master/week6/week6_08_PrioritizingWhatToWorkOn_05.png)
![08-06](https://github.com/hephaex/ML_class/blob/master/week6/week6_08_PrioritizingWhatToWorkOn_06.png)

### Error Analysis



## Handling Skewed Data

### Error Metrics for Skwed Classes

![10-01](https://github.com/hephaex/ML_class/blob/master/week6/week6_10_ErroeMetrics4SkewedClass_01.png)
![10-02](https://github.com/hephaex/ML_class/blob/master/week6/week6_10_ErroeMetrics4SkewedClass_02.png)
![10-03](https://github.com/hephaex/ML_class/blob/master/week6/week6_10_ErroeMetrics4SkewedClass_03.png)

### Trading Off Precision and Recall

![11-01](https://github.com/hephaex/ML_class/blob/master/week6/week6_11_TradingOffPrecisionAndRecall_01.png)
![11-02](https://github.com/hephaex/ML_class/blob/master/week6/week6_11_TradingOffPrecisionAndRecall_02.png)
![11-03](https://github.com/hephaex/ML_class/blob/master/week6/week6_11_TradingOffPrecisionAndRecall_03.png)
![11-04](https://github.com/hephaex/ML_class/blob/master/week6/week6_11_TradingOffPrecisionAndRecall_04.png)
![11-05](https://github.com/hephaex/ML_class/blob/master/week6/week6_11_TradingOffPrecisionAndRecall_05.png)
![11-06](https://github.com/hephaex/ML_class/blob/master/week6/week6_11_TradingOffPrecisionAndRecall_06.png)
![11-07](https://github.com/hephaex/ML_class/blob/master/week6/week6_11_TradingOffPrecisionAndRecall_07.png)
![11-08](https://github.com/hephaex/ML_class/blob/master/week6/week6_11_TradingOffPrecisionAndRecall_08.png)
![11-09](https://github.com/hephaex/ML_class/blob/master/week6/week6_11_TradingOffPrecisionAndRecall_09.png)

## Using Large Data Sets

### Data For Machine Learning

![12-01](https://github.com/hephaex/ML_class/blob/master/week6/week6_12_DataForMachineLearning_01.png)
![12-02](https://github.com/hephaex/ML_class/blob/master/week6/week6_12_DataForMachineLearning_02.png)
![12-03](https://github.com/hephaex/ML_class/blob/master/week6/week6_12_DataForMachineLearning_03.png)
![12-04](https://github.com/hephaex/ML_class/blob/master/week6/week6_12_DataForMachineLearning_04.png)
