---
layout: post
title:  "팀 프로젝트 기여방안"
date:   2020-05-24
excerpt: ""
tag:
- team_project
- word_cloud
- contribution
comments: false
---

## 프로젝트 개선 방향성

#### 1.한글로 구현하는 기능 추가
word cloud 프로젝트는 영어를 기반으로, 영어 문장(글)을 입력 받아 단어 등장 횟수에 따라 단어의 크기를 설정하여 하나의 이미지(구름)안에 단어들을 배치하는 작업이다. 
tokenization 등의 자연어처리가 진행되어 정제된 단어를 얻는 방식이며, font 설정에 따라 다른 언어도 작업이 가능하다.<br>
그러나 영어에 최적화된 자연어처리 과정에 의해 다른 언어들의 특성을 반영하지 못하고 시각적으로 핵심 단어를 파악하는 
word cloud의 기본 취지를 반영하지 못하는 상황이 발생하며, 이 문제는 [Different_Languages_issue][issue1]에서 제기되고 있다.<br>
font를 GmarketSansTTFLight.ttf로 적용하여 한글 예시를 작업해본 결과, 한글에서의 문제점을 파악할 수 있었다.<br>
![word_cloud_example_korean][word_cloud_example_korean]<br>
한글의 특성상 단어 뒤에는 항상 '조사'가 붙게 되는데, 이는 위의 예시에서 '소프트웨어를'과 '소프트웨어가'의 상황처럼 
'소프트웨어'로서 같은 단어로 처리되어야 할 단어가 조사에 따라 다른 단어로 체크되게 하여 단어의 등장 횟수를 계산하는 
word cloud의 기본 작업에 지장이 가게 하는 원인이다.<br>
따라서 우리 팀은 한글 자연어처리를 도와주는 외부 패키지 konlpy를 사용하여 이와 같은 문제를 해결하고자 한다.<br>
<br>

#### 2.정적페이지에 문서화
영어로만 설명되어있는 word cloud문서를 한글 문서화하여 한국 사람들에게 좀 더 쉽게 다가갈 수 있고 적용될 수 있는 프로젝트가 되도록 기여할 것이다.<br>
![issue1_doc_link][issue1_doc_link]<br>
또한 [Different_Languages_issue][issue1]에서 언급된 바와 같이 추후에 본 프로젝트에 한글로 구현가능한 기능을 버전으로 가진 페이지로서 링크를 추가할 수 있다면, 
여기서 한글로 정리된 정적페이지가 큰 도움이 될 것이다.<br>
<br>

#### 3.새로운 ISSUE 탐색, 새로운 기능 추가
한글로 word cloud를 구현하는 방식 외에도, word cloud의 다양한 issue들을 해결하기 위해 추가적으로 탐색하고, 해결방안을 같이 의논하여 기여할 것이다.<br>
7.1k의 스타를 받은 대형 프로젝트임에도 불구하고 현재까지도 많은 issue와 수정사항들이 word cloud에 존재한다.<br>
현재까지 탐색한 흥미로운 issue 중 [plural_issue][issue2]는 영어에서 복수형태의 단어를 모두 단수형태로 일반화하는 기능에 문제가 있다는 것인데, 
's'로 끝나는 'virus'같은 단어가 복수형태와 구분이 되지 않아서 'viru'로 처리되는 등 의도와 다르게 's'가 삭제되는 버그가 발생하고 있다고 한다.<br>
원 코드 작성자가 미리 preprocessing을 하는 등의 방식으로 해결책을 제시했지만, 긴 글의 경우 적용하기 쉽지 않은 해결책이다.<br>
우리 팀은 현재 해당 issue가 해결할 수 있는 문제인지, 우리 수준에서 해결 가능한지, 해결했을 때에 추가되는 소요시간이 너무 커지지는 않는지 등을 고려하여 
진행 여부를 의논 중에 있다.<br>
<br>
<br>

## 나의 기여방안
**정적페이지에 문서화**<br>
팀 정적페이지에 word cloud 프로젝트를 한글로 문서화할 것이다. 단순히 번역만 하는 것이 아닌, 다양한 한글 예제를 추가하고 
프로그램 설치부터 사용법, 명령어들에 대한 설명 등 프로그램을 사용하기 위한 전반적인 설명을 구체적으로 문서화한다.<br>
추후에 한글로 구현가능한 기능을 버전으로 가진 페이지로서 본 프로젝트에 링크를 추가할 경우에 한글을 이용해 word cloud를 이용하려는 사용자들이 
쉽고 이해하기 빠르도록 잘 정리된 정적페이지를 만드는 것이 목표이다.<br>
<br>

**새로운 ISSUE 탐색, 새로운 기능 추가**<br>
글자 방향을 새로운 각도로 시도하거나 테마와 어울리는 단어로 이미지 영역을 채우거나 프로그램 실행을 간편하게 만들어 주는 등의 새로운 기능을 추가 가능할지 고려 중에 있다. 
실제로 실현 가능할지에 관한 논의를 팀원들과 진행 중에 있으며, 해당 내용이 word cloud 프로젝트에 issue로 제기되어 있는지 확인 중이다.<br>
또한 word cloud 프로젝트의 issue 중에서도 우리가 해결가능하고 괜찮아보이는 issue들을 탐색 중이며, 현재는 [plural_issue][issue2]에 관해 팀원들과 
논의 중에 있다. 해당 issue를 진행하게 될 경우, English dictionary package 등의 패키지를 활용하거나 pattern 라이브러리를 사용하는 등의 
다양한 해결 방안을 고려 중이다.<br>


[issue1]: https://github.com/amueller/word_cloud/issues/238
[word_cloud_example_korean]: /assets/img/word_cloud_example_korean.png
[issue1_doc_link]: /assets/img/issue1.PNG
[issue2]: https://github.com/amueller/word_cloud/issues/542
