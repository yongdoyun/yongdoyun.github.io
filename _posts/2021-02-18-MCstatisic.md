---
title: Monte Carlo Statistics
toc: ture
toc_sticky: true

---

## Reliability of the results
*Mar 10, 2021*

Monte Carlo simulation이 매우 복잡한 지오메트리에서도 정확한 선량 계산이 가능하지만 uncertainties는 분명히 존재함.  

The reliability of the results obtained using Monte Carlo simulation depends essentially on **the number of trials**, and most codes output **the standard error of the mean** as statistical uncertainties.  
The results of Monte Carlo simulations intrinsically include systematic uncertainties associated with **unclear physical quantities**, such as total cross section and material composition.  

**Therefore, estimation of not only the statistical but also the systematic uncertainties are required to confirm the reliability of results.**

## Statistical Information in TOPAS
*Feb 18, 2021*

디폴트설정에서 scorers는 모든히스토리 과정중 총 합을 정량적으로 계산해서 보여준다.  
**다양한 설정이 기본적으로 존재**
```console
# default
sv:Sc/MyScorer/Report = 1 "Sum"
# Sum, Mean, Histories, Count_In_Bin, Second_Moment, Variance, Standard_Deviation, Min, Max
# example
sv:Sc/MyScorer/Reprot = 3 "Sum" "Variance" "Standard_Deviation"
```

1. **"Count_In_Bin"** is the number of histories that contributed to this bin (that is, excludes any histories for which no particles hit this bin).
2. **"Sum"** simple accumulation.
3. If "Mean", "Second_Moment", "Variance", or "Standard_Deviation" is requested, accumulation uses a numerically stable algorithm from: Donald E. Knuth (1998). The Art of Computer Programming, volume 2: Seminumerical Algorithms, 3rd edn., p. 232. Boston: Addison-Wesley: ...
	- Speed Penalty: This occurs because any bin that has ever been hit will then have to recalculate its mean or second moment to account for the new history (even if the current history doesn’t hit this bin).  

TOPAS calculates the variance (and hence the standard deviation) associated with the distribution of the quantity of interest (dose, fluence, etc).  

- For the standard deviation of the mean value, divide the standard deviation from TOPAS by the square root of the total number of histories.  
- For the standard deviation of the sum, multiply the standard deviation from TOPAS by the square root of the total number of histories.  

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

```console
conda install -c conda-forge uncertainties
```

## References
1. Hashimoto, Shinataro, and Tatsuhiko Sato. "Estimation method of systematic uncertainties in Monte Carlo particle transport simulation based on analysis of variance." *Journal of Nuclear Science and Technology* (2019)
