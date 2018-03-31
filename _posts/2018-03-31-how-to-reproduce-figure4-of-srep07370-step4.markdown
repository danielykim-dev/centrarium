---
layout: post
title:  "srep07370 의 Figure 4A 그려보기 - 4"
author: Daniel Kim
categories: Publication
tags:	publication figure
cover:  "/assets/images/DKim2014/Fig4.jpg"
---

[Daniel Kim *et al.* *Sci. Rep.* **4**:7370 (2014).](https://www.nature.com/articles/srep07370)

위의 논문은 제 대표 논문입니다. 출판되자마자 [*Nature.com*](https://www.nature.com/) 메인에 소개되었고 2014년 12월 셋째주부터 2015년 1월 둘째주까지 [*Nature.com*](https://www.nature.com/) 에서 사람들이 가장 많이 본 논문이었습니다. [*Nature Research Highlight*](http://www.natureasia.com/en/research/highlight/9640)와 [*PNAS*](http://www.pnas.org/content/112/25/7619.full) 소개글을 포함한 해외 언론 5건, 국내 TV 5건, 국내 인터넷 뉴스 16건 등에서도 소개된 연구입니다. [여기](http://danielykim.me/papers/DKim2014/)에서 보도되었던 모든 자료를 확인할 수 있습니다.

최근에 위 논문의 Figure 4A를 어떻게 그리는지 질문을 받았습니다. 그리는 방법을 할 수 있는 한 쉽게 설명해보겠습니다.

위 논문의 Figure 4A는 다음과 같은 순서로 그렸습니다.

1. [그림 파일을 읽습니다.]({{ site.baseurl }}/publication/2018/03/18/how-to-reproduce-figure4-of-srep07370-step1.html)
2. [그림을 Grayscale로 변환합니다.]({{ site.baseurl }}/publication/2018/03/20/how-to-reproduce-figure4-of-srep07370-step2.html)
3. [그림에서 각 픽셀의 Grayscale 값을 각 픽셀의 높이로 둡니다.]({{ site.baseurl }}/publication/2018/03/21/how-to-reproduce-figure4-of-srep07370-step3.html)
4. <U>각 막대를 Grayscale 변환하기 전 색으로 칠합니다.</U>

이 글에서는 4번째 단계를 구체적으로 다룹니다.

3단계까지 진행하여 txt 파일을 하나 만들었습니다. 

이제 이 txt 파일을 가지고 그림을 그려보겠습니다. 

그림을 그릴 때는 Gnuplot이라는 프로그램을 사용합니다.


## Gnuplot을 내려받습니다.
[링크](https://sourceforge.net/projects/gnuplot/)에 방문합니다. 

아래와 같은 화면이 보일 것입니다. 여기에서 녹색 Download 버튼을 클릭합니다.

![Gnuplot download page]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-download-01.png)

클릭하고 기다리면 아래와 같이 파일을 자동으로 내려받을 수 있습니다. 팝업 차단이 되어있으면 진행이 안 될 수도 있습니다.

![Downloading Gnuplot setup file]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-download-02.png)


## Gnuplot을 설치합니다.
내려받은 설치 파일을 실행하면 다음과 같이 언어 선택하는 창이 나타납니다. English 를 선택하고 OK 를 클릭합니다.

![Gnuplot setup - select language]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-install-01.png)

I accept the agreement 체크 후에 Next > 를 클릭합니다.

![Gnuplot setup - agreement]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-install-02.png)

아래와 같은 내용이 보이면 Next > 를 클릭합니다.

![Gnuplot setup - information]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-install-03.png)

기본 설정 경로로 설치하겠습니다. 경로를 그대로 두고 Next > 를 클릭합니다.

![Gnuplot setup - destination location]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-install-04.png)

Full Installation 옵션을 선택합니다. 그리고 Next > 를 클릭합니다.
  
![Gnuplot setup - select components]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-install-05.png)

아래와 같은 내용이 보이면 Next > 를 클릭합니다.

![Gnuplot setup - start menu folder]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-install-06.png)

그대로 두고 Next > 를 클릭합니다.

![Gnuplot setup - additional tasks]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-install-07.png)

이제 설치를 시작할 준비가 됐습니다. Install 을 클릭합니다.

![Gnuplot setup - ready to install]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-install-08.png)

설치가 진행 중인 것을 확인할 수 있습니다.

![Gnuplot setup - installing]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-install-09.png)

설치가 끝나면 아래와 같은 내용이 나옵니다. Next > 를 클릭합니다.

![Gnuplot setup - information]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-install-10.png)

설치가 끝났습니다. Finish 를 클릭합니다.

![Gnuplot setup - information]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-install-11.png)



## [Gnuplot](https://sourceforge.net/projects/gnuplot/)으로 파일을 읽어서 그림을 그립니다.
이제 Gnuplot으로 3번 단계에서 만들었던 `txt` 파일을 읽어서 그림을 그려보겠습니다.

미리 만들어둔 Gnuplot 스크립트를 이용해서 그리겠습니다.

스크립트는 아래와 같이 내려받을 수 있습니다.

### Gnuplot 스크립트 내려받기

[링크](https://github.com/danielykim-dev/reproduce-my-figures/tree/master/DKim2014-srep07370)를 클릭하면 아래와 같은 페이지로 이동합니다. 아래와 같이 `crocus-3226433_640-show_image.plt` 라는 파일을 클릭합니다.

![Download plt file - 01]({{ site.baseurl }}/assets/images/2018-03-31/download-plt-file-01.png)

아래와 같은 내용이 보이면 Raw 를 클릭하여 이동합니다.

![Download plt file - 02]({{ site.baseurl }}/assets/images/2018-03-31/download-plt-file-02.png)

아래와 같은 내용이 보이면 마우스 오른쪽 버튼을 클릭하여 **다른 이름으로 저장**합니다. 이 스크립트를 `txt` 파일이 있는 폴더에 저장합니다.

![Download plt file - 03]({{ site.baseurl }}/assets/images/2018-03-31/download-plt-file-03.png)


### 스크립트 실행하여 그림 확인하기
[Gnuplot](https://sourceforge.net/projects/gnuplot/)를 정상적으로 설치했고, Gnuplot 스크립트를 3번 단계에서 만든 `txt` 파일이 있는 폴더에 저장했다면, 내려받은 `crocus-3226433_640-show_image.plt` 파일을 더블클릭하여 실행합니다.

그러면 아래와 같이 그림을 확인할 수 있습니다. 
![Gnuplot setup - information]({{ site.baseurl }}/assets/images/2018-03-31/gnuplot-show-image-01.png)
  
그림이 보이기까지 수십초 걸립니다. 작은 그림으로 작업했으면 Gnuplot 창에서 마우스를 드래그해서 보는 각도를 변경할 수도 있습니다.

