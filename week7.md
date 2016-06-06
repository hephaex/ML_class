# 온수당 Machine Learing Note (week #7)
* Advice for applying machine learning
* progress: 7 주차
*
* date: 2016.06.06

* Note:
 - 1주와 2주는 supervised learing 에서 Linear Regression(선형 회귀)을 공부했습니다.
 - 3주는 classification(군집화)에 대하여 공부했습니다.
 - 4주는 기계학습에서 사용하는 신경망(neural network)을 공부했습니다.
 - 5주는 신경망이 어떻게 학습을 하는지에 대하여 공부합니다.
 - 5주차 이후 중간 복습하는 시간을 가졌습니다. 
 - 6주차에서는 기계학습에 도움될 여러가지 것을 공부합니다. 
 - 6주차에서 Machine learning에 디자인에 대한 부분을 시간상 이번주에 하고,
 - 7주차에서 해야 할 Support Vector Machine에 대한 부분을 공부합니다.
 
## Week7 contents
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

* Large Margin Classification
> Optimization Objective
>
> Large Margin Intuition
>
> Mathematics Behind Large Margin Classification

* Kernels
> Kernels I
>
> Kernels II

* SVMs in Practice
> Using A SVM

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

## Large Margin Classification

### Optimization Objective
![01-01](https://github.com/hephaex/ML_class/blob/master/week7/week7_01_Optimization_01.png)
![01-02](https://github.com/hephaex/ML_class/blob/master/week7/week7_01_Optimization_02.png)
![01-03](https://github.com/hephaex/ML_class/blob/master/week7/week7_01_Optimization_03.png)
![01-04](https://github.com/hephaex/ML_class/blob/master/week7/week7_01_Optimization_04.png)
![01-05](https://github.com/hephaex/ML_class/blob/master/week7/week7_01_Optimization_05.png)
![01-06](https://github.com/hephaex/ML_class/blob/master/week7/week7_01_Optimization_06.png)
![01-07](https://github.com/hephaex/ML_class/blob/master/week7/week7_01_Optimization_07.png)
![01-08](https://github.com/hephaex/ML_class/blob/master/week7/week7_01_Optimization_08.png)
![01-09](https://github.com/hephaex/ML_class/blob/master/week7/week7_01_Optimization_09.png)

### Large Margin Intuition

![02-01](https://github.com/hephaex/ML_class/blob/master/week7/week7_02_LargeMargin_01.png)
![02-02](https://github.com/hephaex/ML_class/blob/master/week7/week7_02_LargeMargin_02.png)
![02-03](https://github.com/hephaex/ML_class/blob/master/week7/week7_02_LargeMargin_03.png)
![02-04](https://github.com/hephaex/ML_class/blob/master/week7/week7_02_LargeMargin_04.png)
![02-05](https://github.com/hephaex/ML_class/blob/master/week7/week7_02_LargeMargin_05.png)
![02-06](https://github.com/hephaex/ML_class/blob/master/week7/week7_02_LargeMargin_06.png)
![02-07](https://github.com/hephaex/ML_class/blob/master/week7/week7_02_LargeMargin_07.png)
![02-08](https://github.com/hephaex/ML_class/blob/master/week7/week7_02_LargeMargin_08.png)
![02-09](https://github.com/hephaex/ML_class/blob/master/week7/week7_02_LargeMargin_09.png)


### Mathematics Behind Large Margin Classification
![03-01](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_01.png)
![03-02](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_02.png)
![03-03](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_03.png)
![03-04](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_04.png)
![03-05](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_05.png)
![03-06](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_06.png)
![03-07](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_07.png)
![03-08](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_08.png)
![03-09](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_09.png)
![03-10](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_10.png)
![03-11](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_11.png)
![03-12](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_12.png)
![03-13](https://github.com/hephaex/ML_class/blob/master/week7/week7_03_BehindLargeMargin_13.png)

## Kernels

### Kernels I
![04-01](https://github.com/hephaex/ML_class/blob/master/week7/week7_04_Kernel1_01.png)
![04-02](https://github.com/hephaex/ML_class/blob/master/week7/week7_04_Kernel1_02.png)
![04-03](https://github.com/hephaex/ML_class/blob/master/week7/week7_04_Kernel1_03.png)
![04-04](https://github.com/hephaex/ML_class/blob/master/week7/week7_04_Kernel1_04.png)
![04-05](https://github.com/hephaex/ML_class/blob/master/week7/week7_04_Kernel1_05.png)
### Kernels II
![05-01](https://github.com/hephaex/ML_class/blob/master/week7/week7_05_Kernel2_01.png)
![05-02](https://github.com/hephaex/ML_class/blob/master/week7/week7_05_Kernel2_02.png)
![05-03](https://github.com/hephaex/ML_class/blob/master/week7/week7_05_Kernel2_03.png)
![05-04](https://github.com/hephaex/ML_class/blob/master/week7/week7_05_Kernel2_04.png)
![05-05](https://github.com/hephaex/ML_class/blob/master/week7/week7_05_Kernel2_05.png)
![05-06](https://github.com/hephaex/ML_class/blob/master/week7/week7_05_Kernel2_06.png)

## SVMs in Practice
### Using A SVM

![06-01](https://github.com/hephaex/ML_class/blob/master/week7/week7_06_SVM_01.png)
![06-02](https://github.com/hephaex/ML_class/blob/master/week7/week7_06_SVM_02.png)
![06-03](https://github.com/hephaex/ML_class/blob/master/week7/week7_06_SVM_03.png)
![06-04](https://github.com/hephaex/ML_class/blob/master/week7/week7_06_SVM_04.png)
![06-05](https://github.com/hephaex/ML_class/blob/master/week7/week7_06_SVM_05.png)
![06-06](https://github.com/hephaex/ML_class/blob/master/week7/week7_06_SVM_06.png)
![06-07](https://github.com/hephaex/ML_class/blob/master/week7/week7_06_SVM_07.png)
![06-08](https://github.com/hephaex/ML_class/blob/master/week7/week7_06_SVM_08.png)
![06-09](https://github.com/hephaex/ML_class/blob/master/week7/week7_06_SVM_09.png)


