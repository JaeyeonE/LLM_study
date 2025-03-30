# LLM_study

Colab link : https://colab.research.google.com/drive/1DcJJFBorxjWvuEelN819TP8ZJzUTvFlk?usp=sharing



## MNLI 분류 모델 프로젝트
###프로젝트 개요
본 프로젝트는 자연어 처리(NLP) 작업 중 하나인 MNLI(Multi-Genre Natural Language Inference) 분류 문제를 해결하기 위한 모델을 HuggingFace 라이브러리를 활용하여 구현한 것입니다.
MNLI 작업 설명

* 입력: premise(전제)와 hypothesis(가설) 두 문장
* 출력: 두 문장 간의 논리적 관계를 다음 세 클래스로 분류

* Entailment: 두 문장에 논리적 모순이 없음
* Neutral: 두 문장은 논리적으로 관련이 없음
* Contradiction: 두 문장 사이에 논리적 모순이 존재함



###데이터셋

* 데이터셋: nyu-mll/glue, mnli 태스크
* 학습 데이터: train 스플릿만 활용하여 90%는 학습용, 10%는 검증용으로 분할
* 평가 데이터: validation_matched 스플릿을 사용하여 최종 성능 측정

###모델 아키텍처

*사전 학습된 트랜스포머 기반 모델 활용
*파인튜닝을 통한 MNLI 분류 작업 수행

###학습 설정

*학습률(learning rate): 3e-5
*배치 크기: 16 (GPU 당)
*에폭 수: 1
*최적화 전략: 매 에폭마다 평가 및 모델 저장
*평가 지표: accuracy, F1 score

###학습 결과

*성능 분석

*정확도(Accuracy): 약 80.9%로, 요구사항인 50%를 크게 상회
*F1 점수: 약 80.9%로, 모델이 모든 클래스에 대해 균형 있게 좋은 성능을 보임
검증 손실이 학습 손실보다 낮아 과적합 없이 일반화가 잘 이루어짐

*환경 설정
이 프로젝트는 Google Colab T4 런타임 환경에서 실행되었습니다.

###실행 방법
1. 노트북 파일을 Google Colab에서 열기
2. 모든 셀을 순차적으로 실행
3. 학습 결과 및 성능 지표 확인
