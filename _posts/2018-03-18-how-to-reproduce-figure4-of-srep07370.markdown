---
layout: post
title:  ""
date:   2018-03-18 22:11:00
author: Daniel Kim
categories: Figure
tags:	publication figure
cover:  "/assets/instacode.png"
---

Daniel Kim *et al.* *Sci. Rep.* **4**:7370 (2014).

위의 논문의 Figure 4를 그리는 순서
1. 그림 파일을 읽습니다. 
2. 그림을 Grayscale로 변환합니다. 
3. 그림에서 각 픽셀의 Grayscale 값을 각 픽셀의 높이로 둡니다.
4. 각 막대를 Grayscale 변환하기 전 색으로 칠합니다.

각각을 조금 더 구체적으로 살펴보겠습니다.


#### 1. 그림 파일을 읽습니다.
Python을 이용해서 그림 파일을 읽어보겠습니다. 

Python은 프로그래밍 언어입니다. 

아직 Python을 설치하지 않았다면, 다음과 같이 설치합니다.

- Python 설치(Miniconda3)
  - 아래 주소로 이동합니다. 
    - https://conda.io/miniconda.html
  - 사용하는 컴퓨터 RAM 용량이 4GB 이상이면 Python 3.6 64-bit를 미만이면 32-bit를 내려받습니다.
  - 내려받은 설치 파일을 실행합니다.


- Python Library 설치
  - Windows 7/8/10 에서 윈도우 키를 누르고 Anaconda 라고 입력하면 Anaconda Prompt 가 검색됩니다. 이것을 실행합니다.
  - 아래와 같이 한 줄씩 입력합니다.

```shell
(base) C:\> pip install numpy matplotlib jupyter opencv-contrib-python
(base) C:\> mkdir practice
(base) C:\> cd practice
(base) C:\practice> jupyter notebook
```

여기까지 입력하면 기본 브라우저에 다음과 같은 화면이 보일 것입니다.
