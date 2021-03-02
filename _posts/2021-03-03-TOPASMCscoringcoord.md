---
title: TOPAS Scoring 좌표축 
toc: true
toc_stiky: true

---

빔의 방향과 무관.  
지오메트리 생성과 동시에 Bins에 따라  좌표축이 만들어짐.  
따라서 Scoring Geometry를 회전시키는 것을 지양해야함.  

Matrix form으로 얻어지지만 Matrix라고 생각하면 안됨.  
기존의 x,y 좌표와 마찬가지로 우상단으로 갈수록 x,y가 증가  
Scoring할때든 언제든 TOPAS default coordinat system 에 맞춰서 항상 생각할건지 고민해야할듯. 

사실 이 고민은 정말 나중에 실제 DICOM Plan을 직접가져와서 할때 해도 괜찮음.  

나중에 BField는 어차피 노즐뷰에서 상대적인 시스템이라 더 큰 상관은 없을듯.  
지금은 그냥 세팅해놓은 환경(Rotate Gantry 180)에서 BEV로 볼 수있도록 코딩만 해놓자.  
