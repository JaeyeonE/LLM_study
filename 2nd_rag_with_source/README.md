# 웹 기반 RAG 시스템 (Retrieval-Augmented Generation)

### 프로젝트 개요

이 프로젝트는 웹 크롤링과 이미지 OCR을 결합한 고급 RAG(Retrieval-Augmented Generation) 시스템을 구현합니다. 특정 웹페이지의 텍스트와 이미지 내 텍스트를 추출하고, 이를 벡터 저장소에 저장하여 질의응답 시스템을 구축합니다.

## 주요 기능

- **웹 크롤링**: BeautifulSoup을 사용한 웹 컨텐츠 및 이미지 URL 추출
- **이미지 OCR**: Google Cloud Vision API를 사용한 이미지 내 텍스트 인식
- **문서 처리**: 문서 로딩, 분할 및 벡터화
- **벡터 검색**: FAISS를 사용한 효율적인 유사도 검색
- **자연어 응답 생성**: OpenAI의 GPT 모델을 활용한 질의응답

## 사용 방법

1. API 키 설정:
   - `.env` 파일을 생성하고 OpenAI API 키 설정 `OPENAI_API_KEY=your_openai_api_key`
   - Google Cloud Vision API 키 파일 준비

2. Google Cloud Vision API 인증 파일 경로 설정
```python
os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "path/to/your/vision-api-key.json"
```

3. 크롤링할 웹 URL 설정
```python
url = "https://your-target-website.com"
```

4. 코드 실행:
   - 웹 크롤링 및 이미지 추출
   - OCR을 통한 이미지 텍스트 추출
   - 문서 분할 및 벡터화
   - 질의응답 시스템 실행

## 시스템 구조

1. **데이터 수집 단계**
   - 웹 크롤링을 통한 텍스트 및 이미지 URL 추출
   - Vision API를 통한 이미지 내 텍스트 인식

2. **데이터 처리 단계**
   - 문서 로딩 및 정규화
   - 텍스트 분할(chunking)
   - 임베딩 생성

3. **검색 및 생성 단계**
   - 사용자 질문에 관련된 문서 검색
   - 검색된 컨텍스트와 질문을 바탕으로 응답 생성

## Workflow Diagram
![Workflow Diagram](./workflow%20diagram.png)

## 주의사항

- Google Cloud Vision API와 OpenAI API는 사용량에 따라 비용이 발생할 수 있습니다.
- 웹 크롤링 시 대상 웹사이트의 이용약관을 준수해야 합니다.
- 이미지 크기와 수에 따라 처리 시간이 길어질 수 있습니다.