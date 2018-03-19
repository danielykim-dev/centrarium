---
layout: post
title:  "srep07370 의 Figure 4 를 그려봅시다."
author: Daniel Kim
categories: Publication
tags:	publication figure
cover:  "/assets/images/DKim2014/Fig4.jpg"
---

[Daniel Kim *et al.* *Sci. Rep.* **4**:7370 (2014).](https://www.nature.com/articles/srep07370)

위의 논문의 Figure 4를 그리는 순서

1. 그림 파일을 읽습니다. 
2. 그림을 Grayscale로 변환합니다. 
3. 그림에서 각 픽셀의 Grayscale 값을 각 픽셀의 높이로 둡니다.
4. 각 막대를 Grayscale 변환하기 전 색으로 칠합니다.

이 글에서는 1번 항목을 다룹니다.


## 1. 그림 파일을 읽습니다.
Python을 이용해서 그림 파일을 읽어보겠습니다. 

Python은 프로그래밍 언어입니다. 

아직 Python을 설치하지 않았다면, 다음과 같이 설치합니다.

### Python 설치(Miniconda3)
아래 주소를 클릭하면 아래 그림과 같이 Miniconda 다운로드 페이지로 이동합니다.
- [https://conda.io/miniconda.html](https://conda.io/miniconda.html)

![Miniconda download page]({{ site.baseurl }}/assets/images/2018-03-18/miniconda-download-page.png)

- 사용하는 컴퓨터 RAM 용량이 4GB 이상이면 Python 3.6 64-bit를 
- 4GB 미만이면 32-bit를 내려받습니다.

내려받은 설치 파일을 실행합니다. "Next"를 클릭하여 넘어갑니다.

![Miniconda3 install 01]({{ site.baseurl }}/assets/images/2018-03-18/miniconda3-install-01.png)

"I Agree"를 클릭하여 넘어갑니다.

![Miniconda3 install 02]({{ site.baseurl }}/assets/images/2018-03-18/miniconda3-install-02.png)

"Just Me"가 선택된 상태에서 "Next >"를 클릭하여 넘어갑니다.

![Miniconda3 install 03]({{ site.baseurl }}/assets/images/2018-03-18/miniconda3-install-03.png)

저는 설치 폴더를 아래와 같이 바꿨으나 굳이 바꾸지 않으셔도 됩니다. "Next >"를 클릭하여 넘어갑니다.

![Miniconda3 install 04]({{ site.baseurl }}/assets/images/2018-03-18/miniconda3-install-04.png)

화면과 같이 그대로 두고 "Install"을 클릭하여 넘어갑니다.

![Miniconda3 install 05]({{ site.baseurl }}/assets/images/2018-03-18/miniconda3-install-05.png)

설치가 진행됩니다.

![Miniconda3 install 06]({{ site.baseurl }}/assets/images/2018-03-18/miniconda3-install-06.png)

Miniconda 설치가 끝나면 윈도우 키를 누르고 Anaconda 라고 입력합니다. 저는 Windows 10 에서 진행했습니다.
그러면 아래와 같이 Anaconda Prompt 가 검색됩니다. 이것을 실행합니다.

![Run Anaconda Prompt]({{ site.baseurl }}/assets/images/2018-03-18/Anaconda-Prompt.png)


### Python Library 설치
Anaconda Prompt 창을 실행하면 아래와 같은 화면이 뜹니다.

![]({{ site.baseurl }}/assets/images/2018-03-18/pip-install-libraries-01.png)

여기에서 아래와 같이 입력하고 엔터키를 누릅니다.

```shell
pip install numpy matplotlib jupyter opencv-contrib-python
```

그러면 아래와 같이 Python Library 설치가 진행됩니다. 설치는 몇 분 안에 끝납니다.

![]({{ site.baseurl }}/assets/images/2018-03-18/pip-install-libraries-02.png)

아래와 같은 화면이 보이면 끝난 것입니다.

![]({{ site.baseurl }}/assets/images/2018-03-18/pip-install-libraries-03.png)

아래와 같이 입력하여 연습용 폴더를 하나 만들고 만든 폴더로 이동합니다. 
그리고 위에서 한 것처럼 한 줄씩 입력하고 엔터키를 누릅니다.

```shell
(base) C:\> cd \
(base) C:\> mkdir practice
(base) C:\> cd practice
(base) C:\practice> jupyter notebook
```

여기까지 입력하면 기본 브라우저에 다음과 같은 화면이 보일 것입니다.
그림을 클릭하면 크게 볼 수 있습니다.

<a href="{{ site.baseurl }}/assets/images/2018-03-18/jupyter-notebook-home-01.png" data-lightbox="falcon9-large">
  <img src="{{ site.baseurl }}/assets/images/2018-03-18/jupyter-notebook-home-01.png">
</a>

화면 오른쪽 위에 있는 "Upload" 버튼과 "New" 버튼 중에서 "New"를 클릭하면 드롭다운 메뉴에 "Python 3"가 나타납니다. 자신의 드롭다운 메뉴에 "Python 2" 나 "MRO 3.3.2"가 보이지 않더라도 이상한 것이 아니니 무시하시면 됩니다.

"Python 3"를 클릭합니다. 그러면 아래와 같은 화면이 나옵니다.

<a href="{{ site.baseurl }}/assets/images/2018-03-18/jupyter-notebook-Untitled-01.png" data-lightbox="falcon9-large">
  <img src="{{ site.baseurl }}/assets/images/2018-03-18/jupyter-notebook-Untitled-01.png">
</a>

