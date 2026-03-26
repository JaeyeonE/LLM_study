# KMU & TrustAI 산학멘토링 - LLM 실무 프로젝트 정리

이 저장소는 **KMU & TrustAI 산학멘토링** 프로그램의 일환으로 수행된 **LLM 기반 실무 프로젝트**를 정리했습니다. LangChain, OpenAI API, 벡터DB, HuggingFace 등을 활용해 실무형 NLP 과제를 직접 구현해보며 생성형 AI 기술에 대한 이해를 넓히는 것을 목표 진행했습니다.

## 프로젝트 목표

* LLM, LangChain, RAG 등의 실무형 기술 숙련
* 매 과제별 실습을 통해 자연어처리 파이프라인 학습
* 학습한 이론과 코드를 구조화하여 관리
* 실습 및 과제를 통해 얻은 지식 기록

## 개인 정리 링크

* **Velog**: https://velog.io/@ght010522/posts

## 실습 목록

| 단계 | 주제 | 목표 | 추가 정리 링크 | 
|------|------|------|----------------|
| Step 1 | MNLI 파인튜닝 | HuggingFace Trainer를 사용하여 MNLI 데이터셋 기반 문장 분류 모델 구축 | [Transformer 정리](https://velog.io/@ght010522/Transformer-%EC%A0%95%EB%A6%AC) |
| Step 2 | Retrieval-Augmented Generation | LangChain, ChromaDB, OpenAI API, Google vision API를 활용한 이미지 포함 RAG 파이프라인 설계 및 구현 | [WebBaseLoader vs UnstructuredLoader](https://velog.io/@ght010522/WebBaseLoader-vs-UnstructuredLoader) |
| Step 3 | 프롬프트 엔지니어링 | 다양한 프롬프트 전략을 적용하여 LLM 응답 품질 실험 및 비교 분석 | [프롬프트 엔지니어링 실험: GPT로 2023 수능 국어 풀기](https://velog.io/@ght010522/%ED%94%84%EB%A1%AC%ED%94%84%ED%8A%B8-%EC%97%94%EC%A7%80%EB%8B%88%EC%96%B4%EB%A7%81-%EC%8B%A4%ED%97%98-GPT%EB%A1%9C-2023-%EC%88%98%EB%8A%A5-%EA%B5%AD%EC%96%B4-%ED%92%80%EA%B8%B0) |


## 사용 기술 스택 | Tech Stack

| 범주 | 기술 |
|------|------|
| LLM 인터페이스 | OpenAI API (GPT-4), HuggingFace Transformers |
| 파이프라인 구성 | LangChain |
| 벡터 검색 | FAISS |
| 모델 파인튜닝 | PyTorch, HuggingFace Datasets, HuggingFace Trainer |
| 환경 구성 및 실행 | Python, Jupyter Notebook |
| 문서화 및 기록 | Markdown, GitHub, Velog |

## 앞으로의 계획

* 격주 실습을 통해 다양한 LLM 파이프라인 구현 예정
* LangChain의 고급 체인, 에이전트 기능, 프롬프트 튜닝 실험 예정
* 실제 서비스 또는 프로젝트에 적용 가능한 형태로 확장 도전

##

NLP 과제를 접하며 비전 단순 분류 모델과는 다르게 생각보다 정답이 애매하고 사람의 판단이 개입되는 작업이 많아 흥미로웠습니다. YOLO처럼 명확한 정답이 출력되는 태스크와는 다르게, 답변을 낸 후 알고리즘을 이용해 결과를 후처리해야한다는 점이 신기했습니다. 데이터 입력부터 모델 출력, 결과를 정제하는 과정이 모두 데이터의 품질과 신뢰도를 결정짓는 유기적인 파이프라인임을 체감할 수 있었습니다. 그러나 다양한 인풋에 유동적으로 답이 출력이 되는 것을 보며 정형화되지 않은 언어 데이터 속에 숨겨진 맥락을 파악하는 LLM을 응용해 추후 vision과 접목해 사람들에게 도움이 되는 기술을 개발하고 싶다는 생각을 하게 되었습니다.
