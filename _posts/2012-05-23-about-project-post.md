---
layout: post
title:  "팀 프로젝트 소개"
date:   2020-05-23
excerpt: ""
tag:
- team_project
- word_cloud
comments: false
---

# About the Project!

- Project Name : word cloud

>A little word cloud generator in Python. Read more about it on the [blog post][blog_post] or the [website][website].

>The code is tested against Python 2.7, 3.4, 3.5, 3.6 and 3.7. [_(word_cloud README.md)_][README.md]

<hr>



### 1. 팀프로젝트 소개
![example][example]

* 텍스트 내의 단어들을 중요도(문서 내 등장횟수)를 기준으로 구분하여 특정한 이미지 영역(mask) 내부에 시각화하는 프로젝트

* [GitHub repository][word_cloud]



### 2. 프로젝트로 선정한 이유

* 팀원들이 공통적으로 할 수 있는 언어가 python이고 실생활에 활용도가 높아보이는 프로젝트라서 선정함

* 영어 위주의 프로젝트라 한글을 더 잘 활용할 수 있는 기능을 만들고자 선정함



### 3. 프로젝트 선정 동기

- 팀원들이 공통적으로 할 수 있는 언어가 python이고 실생활에 활용도가 높아보이는 프로젝트라서 선정함

- 영어 위주의 프로젝트라 한글을 더 잘 활용할 수 있는 기능을 만들고자 선정함


 
### 4. 프로젝트 개선방향성

**한글 버전 wordcloud 코드의 필요성**

Word Cloud 프로젝트는 긴 글(문장)을 tokenize 수행하여, 단어 등장 횟수에 따라 글자 크기를 조정하여 word cloud를 생성하도록 하는 프로젝트이기에,
각 언어의 특성에 따라 word cloud가 제대로 수행되지 않을 확률이 높다.

해당 [issue][issue1]에 의하면 영어 기반의 프로젝트이기에,
다양한 언어의 특성을 적절하게 반영하지 못하고 있으며 이에 따라 상당 부분 word cloud의 기본 수행능력이 발휘되지 않은 경우 간혹 발생한다.

한글의 경우, 글자 font를 GmarketSansTTFLight.ttf로 수행하여 진행하면 본 프로젝트의 문제가 드러난다.

한글의 문장 특성 중에 '조사'라는 품사는 항상 명사, 형용사, 부사뒤에 붙여서 사용된다는 특성이 있다.
그래서 한글 자연어처리 과정에서, 조사는 필히 앞에 붙여진 단어와 분리하여 처리되어야 한다.
하지만 본 프로젝트 코드대로 단어 등장 빈도를 측정할 때, 조사를 포함한 하나의 어절로 구분하여 빈도를 측정하게 된다.
그렇게 되면, '(명사)는', '(명사)가'라는 두 어절은 사실상 같은 '(명사)' 단어를 표현한 것인데
따로 구분하여 wordcloud에 표시된다.


이는 확실히, 본 코드에 한글NLP 기능이 없기 때문에 나타난 현상이라 볼 수 있다.
영어 NLP의 경우, 띄어쓰기를 기준으로, 단어가 구분되기 때문에 단어 구분에 있어서 어렵지 않게 처리할 수 있다.
하지만 한글의 단어구분은 띄어쓰기가 아니기 때문에, 한글 NLP 기능 구현 추가가 불가피하다.

**한글 NLP 패키지 활용**

본 팀원은 한글 NLP를 전문적으로 배우지 않았기 때문에, 외부 패키지를 활용하는 것이 불가피하다.
한글 NLP 패키지 중 konlpy라는 패키지가 있다.
해당 패키지도 역시나 오픈소스프로젝트로 활발히 진행 중인 패키지나, 상당 부분 한글 NLP 기능을 구현할 만큼 유용한 패키지라고 판단하여,
해당 패키지를 활용하여 wordcloud 코드를 구현하기로 결정하였다.



**추가 issue 검색 및 해결방안 모색**

wordcloud 프로젝트가 대형 오픈소스프로젝트임에도 불구하고, 여전히 많은 issue들과 수정사항이 현재까지도 진행되고 있다.

대다수는 원 코드 작성자가 직접 해결하였지만, [plural issue][issue2]처럼 완벽하게 해결하지 못한 문제 또한 존재한다.

이러한 issue들을 추가 검색하여 우리가 직접 해결방안을 모색하는 방법으로 개선해나갈 수도 있다.



### 5. 팀 프로젝트 활동 계획

**한글로 구현하는 기능 추가**

한글을 이용해 word-cloud를 구현할 것이다. 특히 조사 등을 제거하여 실질적인 단어로 구성해볼 것이다.



**정적페이지에 문서화 (활용 예제, 한글 예제 추가)**

팀 정적페이지에 word-cloud 프로젝트를 한글로 문서화하고 다양한 예제를 추가할 것이다.



**새로운 ISSUE 검색, 새로운 기능 추가 생각 (글자 방향, 테마와 어울리는 단어)**

유용하다고 생각하는 새로운 기능을 추가하고, 원 프로젝트에서 제기된 issue를 활발히 찾아서 문제를 해결해볼 것이다.



### 7. Links
* The original page - [amueller/word_cloud][original_page] 
* SKKU team repository - [20-1-SKKU-OSS/2020-1-OSS-5][Groupreposit]
* My personal repository - [davidshyn1/2020-1-OSS-5][personalreposit]

[blog_post]: http://peekaboo-vision.blogspot.de/2012/11/a-wordcloud-in-python.html
[website]: http://amueller.github.io/word_cloud/
[README.md]: https://github.com/amueller/word_cloud/blob/master/README.md
[example]: https://github.com/amueller/word_cloud/raw/master/examples/constitution.png
[word_cloud]: https://github.com/amueller/word_cloud
[Groupreposit]: https://github.com/20-1-SKKU-OSS/2020-1-OSS-5
[original_page]: https://github.com/amueller/word_cloud
[personalreposit]: https://github.com/davidshyn1/2020-1-OSS-5
[issue1]: https://github.com/amueller/word_cloud/issues/238
[issue2]: https://github.com/amueller/word_cloud/issues/542
