---
layout: post
title:  "srep07370 의 Figure 4A 그려보기 - 3"
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
3. <U>그림에서 각 픽셀의 Grayscale 값을 각 픽셀의 높이로 둡니다.</U>
4. 각 막대를 Grayscale 변환하기 전 색으로 칠합니다.

이 글에서는 3번 단계를 구체적으로 다룹니다. 1번과 2번은 이미 다루었고 4번은 다음 글에서 다루겠습니다.


## 3. 그림에서 각 픽셀의 Grayscale 값을 각 픽셀의 높이로 둡니다.
2번 단계에서 이어지는 내용입니다.

링크에 있는 코드를 참조하면서 설명하겠습니다.

- [링크](https://github.com/danielykim-dev/reproduce-my-figures/blob/master/DKim2014-srep07370/3%20-%20%EA%B7%B8%EB%A6%BC%EC%97%90%EC%84%9C%20%EA%B0%81%20%ED%94%BD%EC%85%80%EC%9D%98%20Grayscale%20%EA%B0%92%EC%9D%84%20%EA%B0%81%20%ED%94%BD%EC%85%80%EC%9D%98%20%EB%86%92%EC%9D%B4%EB%A1%9C%20%EB%91%90%EA%B8%B0.ipynb)를 클릭하여 제가 미리 작성해둔 코드를 확인할 수 있습니다. 

위의 링크 내용을 다음과 같이 요약할 수 있습니다.
- 그림을 읽습니다.
- 그림을 BGR에서 RGB로 바꿉니다. (그림1)
- 그림을 RGB에서 Grayscale로 바꿉니다. (그림2)
- Gnuplot으로 3차원 표면을 그리기 위해 그림2의 모든 위치의 Grayscale 값과 그림1의 모든 위치의 RGB값을 파일로 씁니다.


