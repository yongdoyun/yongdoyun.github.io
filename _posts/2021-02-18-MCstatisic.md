---
title: Monte Carlo Statistics
toc: ture
toc_sticky: true

---

## Statistical Information in TOPAS

디폴트설정에서 scorers는 모든히스토리 과정중 총 합을 정량적으로 계산해서 보여준다.  
**다양한 설정이 기본적으로 존재**
```console
# default
sv:Sc/MyScorer/Report = 1 "Sum"
# Sum, Mean, Histories, Count_In_Bin, Second_Moment, Variance, Standard_Deviation, Min, Max
# example
sv:Sc/MyScorer/Reprot = 3 "Sum" "Variance" "Standard_Deviation"
```

일단기본적인 TOPAS의 기능으로는 옵션을 넣어주면 계산해줌.  .  
획득한 것을 어떻게 처리해야 error가 계산될지는 error propagation에 대한 공부 필요.    

추후에는 error propagation 과정을 TOPAS extension을 이용하여 직접추가하면 바로 통계처리가 가능 할 것.    


## Paper Review
**On the Assessment of Monte Carlo Error in Simulation-Based Statistical Analyses**  
When a simulation is run more than once, different results are obtained.  
However, virtually no emphasis has been placed on reporting the uncertainty, referred to here as **Monte Carlo error**.  
These deserve broader consideration.  
Here we present a series of simple and practical methods for estimating MC error as well as determining the number of replications required to achieve a desired level of accuracy  

## Error Propagation
에러가 있는 애들끼리 사칙연산을 하게될때 에러들끼리의 연산은 어떻게 해야하는지  
python package중에 error propagation을 알아서 계산해주는  **uncertainties** 라는 패키지가 있음. [홈페이지](https://uncertainties-python-package.readthedocs.io/en/latest/)  

설치방법  

```consol
# 아나콘다로 Python package 및 가상환경 관리
conda install -c conda-forge uncertainties

```

