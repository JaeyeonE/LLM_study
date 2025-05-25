# GPT 기반 2023 수능 국어 문제 풀기

> GPT 모델의 프롬프트 엔지니어링 실험을 통해 수능 국어 문제 풀이 성능을 비교하고 분석한 프로젝트입니다.

## 📌 프로젝트 개요
KICE Slayer는 OpenAI의 GPT 모델을 활용하여 한국 수능 국어 문제를 풀고, 다양한 프롬프트 전략이 문제 해결 정확도에 미치는 영향을 실험적으로 분석하는 프로젝트입니다.

Velog에 작성된 블로그 [Prompt Engineering 실험 - GPT로 2023 수능 국어 풀기](https://velog.io/@ght010522/%ED%94%84%EB%A1%AC%ED%94%84%ED%8A%B8-%EC%97%94%EC%A7%80%EB%8B%88%EC%96%B4%EB%A7%81-%EC%8B%A4%ED%97%98-GPT%EB%A1%9C-2023-%EC%88%98%EB%8A%A5-%EA%B5%AD%EC%96%B4-%ED%92%80%EA%B8%B0)와 연계되어 있습니다.



## 🔍 실험 목적

💡 다양한 프롬프트 전략 (Zero-shot, 감정 유도, 전문가 역할 부여 등)이 GPT 모델의 성능에 어떤 영향을 주는가?
📈 실제 수능 데이터(2023년 11월 국어)를 기반으로 정답률, 점수, 소요 시간, 토큰 사용량 등을 비교

## 🛠️ 기능 요약
| 기능             | 설명                                      |
| -------------- | --------------------------------------- |
| ✅ 문제 데이터 로드    | GitHub에서 2023 수능 국어 JSON 파일 자동 다운로드     |
| ✅ 프롬프트 자동 생성   | 세 가지 스타일의 프롬프트로 문제별 prompt 생성           |
| ✅ 모델 예측 실행     | OpenAI GPT 모델 API를 통해 문제 풀이             |
<<<<<<< HEAD

=======
| -  결과 평가 및 저장   | 정확도, 점수, 토큰 수, 응답 내용 등 평가 후 CSV/JSON 저장 |
| -  시각화/샘플 응답 분석 | 정답/오답 예시와 응답 내용 요약 출력                   |
>>>>>>> d864bbf16805f76e0dc509b4c206237fab15356b

# 🧪 실험 프롬프트 유형

1. zero_shot
아무런 사전 정보 없이 문제를 직접 풀도록 지시하는 기본형 프롬프트

2. emotional_appeal
감정적 압박을 부여해 모델이 더 신중하고 열정적으로 문제를 풀도록 유도하는 방식
예: “이 문제는 당신의 할머니가 지켜보고 계십니다…”

3. expert_role
모델에게 국어 출제위원 역할을 부여하고, 문제를 전문가처럼 분석하도록 요청
예: “30년 경력의 수능 국어 출제위원으로서 이 문제를 분석하세요.”

## 📚 주요 기술
- Python 3.10+
- OpenAI GPT API (gpt-4o, gpt-4o-mini 등)
- pandas, requests, dotenv, tiktoken 등



## 📊 주요 실험 결과
최신 실험 결과는 gpt-4o 모델과 최적화된 zero-shot 프롬프트 조합이 가장 우수한 성능을 보였습니다. 반면, function_calling 프롬프트는 정확도 향상에 기여했으나, 처리 시간이 비교적 길었습니다.

| 모델 + 프롬프트                       | 점수     | 정답률       | 소요 시간     |
| ------------------------------- | ------ | --------- | --------- |
| gpt-4o + zero\_shot (최적화)       | **84** | **84.4%** | 79.8초     |
| gpt-4o + function\_calling      | 74     | 73.3%     | 403.8초    |
| gpt-4o + zero\_shot             | 67     | 68.9%     | 258.5초    |
| gpt-4o + emotional\_appeal      | 67     | 66.7%     | 262.8초    |
| gpt-4o + expert\_role           | 67     | 66.7%     | 362.7초    |
| gpt-4o-mini + zero\_shot (최적화)  | 68     | 68.9%     | **75.7초** |
| gpt-4o-mini + expert\_role      | 54     | 53.3%     | 666.2초    |
| gpt-4o-mini + function\_calling | 48     | 48.9%     | 892.9초    |
| gpt-4o-mini + zero\_shot        | 49     | 48.9%     | 455.4초    |
| gpt-4o-mini + emotional\_appeal | 46     | 46.7%     | 532.7초    |


✅ gpt-4o + zero_shot (최적화) 조합이 정답률 84.4%, 점수 84점, 79.8초라는 뛰어난 성능을 기록함.

⏱️ 최적화된 zero-shot 프롬프트는 정확도뿐 아니라 응답 속도도 가장 빠른 수준.

⚙️ function_calling 프롬프트는 성능은 좋지만 응답 속도가 매우 느림 → 실제 적용 시 효율성 고려 필요.

🧠 단순 zero-shot보다 감정 유도나 전문가 역할 부여 방식은 성능 향상에 제한적이었음.


---

## 실행 방법

``` git clone https://github.com/your_username/KICE_slayer_AI_Korean.git
cd KICE_slayer_AI_Korean

# Python 환경 설정
pip install -r requirements.txt

# OpenAI API 키 설정
touch .env
echo "OPENAI_API_KEY=your_api_key_here" >> .env

# 실행 예시
python main.py
```
