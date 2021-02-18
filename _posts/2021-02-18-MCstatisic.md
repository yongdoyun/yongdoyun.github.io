---
title: Monte Carlo Statistics
toc: ture
toc_sticky: true
---

## Statistical Information in TOPAS
디폴트설정에서 scorers는 모든히스토리 과정중 총 합을 정량적으로 계산해서 보여준다.  
하지만 다양한 설정이 존재
```console
sv:Sc/MyScorer/Report = 1 "Sum"
# Sum, Mean, Histories, Count_In_Bin, Second_Moment, Variance, Standard_Deviation, Min, Max
```

일단 여기에서는 여러가지를 구해주기만 하는듯.  
획득한 것을 어떻게 처리해야 확률이 나올지 생각해보자.  

추후에 획득한 결과를 TOPAS extension 빌드과정에서 직접추가하여 바로 에러를 확인할 수 있도록 하자.  
