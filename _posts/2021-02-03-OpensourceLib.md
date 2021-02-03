---
title: C++ Library

---

## C++ 라이브러리 설치에 대한 공부.
Python을 사용할때는 conda, pip 등으로 편하게 설치가능하였으나 IDE를 사용하지 않는 
현재 C++ 개발 환경에서는 소스코드를 다운받고 직접 빌드하여서 설치해야함.  
지금까지 Python에서 사용해오던 많은 라이브러리들이 c++로 짜여있고 swig로 다른데에서도 사용가능하게 되어온듯.  

C++ 라이브러리를 설치한다는 것은 컴파일러한테 헤더(.hpp)와 compiled obj(.lib, .dll) 의 위치를 알려주는 것.
- dll: 동적 라이브러리, Runtime 중에 필요
- lib: 정적 라이브러리, Compule 중에 필요

빌드방법은 다음과 같다.
1. cmake를 사용하여 CMakeList.txt를 읽어서 Makefile을 만듦
	- ccmake .
	- configuration
2. make -j 4


## ITK
Insight Toolkit (ITK)는 의료영상처리를 위한 오픈소스 라이브러리.

## OpenCV 
일단 잘 아는 openCV 같은걸 c++ 에서 사용해보자.

## VTK


## GDCM
DICOM 데이터를 다루기 위해, C++ 언어를 사용하는 환경에서 일반적으로 GDCM 라이브러라를 사용. dcmtk(Dicom Toolkit)도 사용가능함.  
VTK/ITK는 빌드할 때 GDCM을 포함할 수 있다.
