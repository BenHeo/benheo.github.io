---
title: "[강의리뷰] Causal Data Science with Directed Acyclic Graphs"
tags: lecture, causality
<!-- article_header:
  type: cover
  image:
    src: /screenshot.jpg -->
---

> 유데미의 Causal Data Science with Directed Acyclic Graphs 강의를 듣고 정리한 내용입니다.  
> 개인적으로 DAG에 기반한 인과추론을 배우고 싶었는데 첫걸음을 떼기에 굉장히 적합한 강의였다고 생각합니다.  
>
> 강의 전부를 들으려면 확률계산에 대한 이해가 약간 필요해서 아쉽지만, 배경지식이 있다면 한 번 들어보시는 걸 추천합니다. 몇몇 강의는 강의를 찍고 슬라이드에 오타 있는 걸 발견하고 수정했는지 강의와 슬라이드에 차이가 있어서 ppt슬라이드를 비교하면서 들어야 합니다.  
> 전반적으로 DAG(Directed Acyclic Graphs, 대충 방향성 있는 그래프 모형인데 돌고도는 관계는 아니라는 뜻)에 기반한 인과추론을 다루고, 섹션별로 인과효과를 추론하기 어렵게하는 문제상황을 주고 해결책을 알려주는 방식으로 강의합니다. 중간중간 r실습도 있어 직접해보기도 좋습니다.


---
# 섹션별 주요내용 정리

## 섹션1 : Introduction

구글에서 남직원과 여직원 사이의 임금 차이를 분석했는데, 성별 평균으로만 보면 여직원의 임금이 더 적었는데 직급(매니저/매니저X)별로 나눠보니 남직원 임금이 더 적어서 남직원 임금을 더 올려줬다.  
-> 여기까지가 흔히 Simpons's paradox라 해서 더 나눠서 분석하면 결과가 바뀌기도 한다는 내용인데, 해당 강의에서는 성별이 직급에 영향을 주는 요인이기 때문에 성별/직급에 따라 나누는 건 잘못된 추론이라 말하면서 `그래프 모델을 통한 인과분석`의 필요성을 강조

## 섹션2 : Structural Causal Models, Interventions, and Graphs

DAG 구조와 앞으로 사용할 핵심 표기법, 용어에 대해 알려줌  
특히 상관없는 걸 상관있어 보이게 하는 다른 요인의 영향을 제거하는 게 인과분석의 핵심인데 D-separation이라는 개념을 알려줌  
또, RCT(Randomized Controlled Trial, 무작위로 배정해 진행한 실험)가 원래 인과분석에서 기본인데 현실에서는 이런 실험이 어려운 경우가 많아 관측치만으로 실험 효과를 얻는 수식 테크닉을 이제 알려줄게 이런 구성

## 섹션3 : Causal Discovery

DAG 구조는 방향성 있는 그래프를 만들어야 하는데 도메인지식에 기반해 이를 만들어줄 수도 있지만, 잘 모르는 경우도 많고 잘 안다고 생각했는데 잘 모르고 있는 경우도 많으니 자동으로 DAG 구조를 만들어주는 PC 알고리즘에 대해 설명

## 섹션4 : Confounding Bias and Surrogate Experiments

인과추론을 할 때 교란변수*의 영향력을 제거해야 하는데 이에 대한 방법론들을 알려줍니다. 전체 섹션 중 핵심 내용

- backdoor criterion
- frontdoor criterion
- do-calculus
- z-identification
개념을 다룸

*아이스크림 판매량(X)가 늘어나면 상어습격으로 인한 피해량(Y)가 늘어난다는 잘못된 결론을 내게 하는 계절(Z) 같은 걸 교란변수로 볼 수 있음

## 섹션5 : Recovering from Selection Bias

편향된 데이터를 수집했을 때 올바르게 인과관계를 추론하는 방법에 대해 다루는데 예시는 궁금하게 만드는 걸 들고와놓고 사실 이 케이스는 당장 못 풀고 다른 케이스 해결법 알려줄게 하는 방식이어서 이상했던 파트  

데이터가 편향됐다는 건 02- 로 시작하는 전화로 여론조사를 하고 국민의 여론이 이렇다라고 얘기하는 상황에서 씁니다

## 섹션6 : Transportability of Causal Knowledge Across Domains

지금까지는 관측치만으로 실험 결과에 준하는 효과를 얻는 방법에 초점을 맞췄다면, 섹션6에서는 실험한 결과가 있긴한데 도메인/사회적배경이 다른 집단에서는 관측치만 있다면 실험 결과를 활용해 도메인이 다른 걸 고려하면서 합리적으로 인과효과를 측정하는 법을 다룹니다.  

---

개인공부 목적으로 노션에 정리한 [링크](https://www.notion.so/hyun22/Causal-Data-Science-with-Directed-Acyclic-Graphs-3be6e088f57541b89306b436ac7f0c6c){:target="_blank"} 공유드립니다. 공부에 도움되면 좋겠습니다.
감사합니다.
