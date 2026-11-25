# 영어지문 분석기

영어 지문과 공식 한글 해석을 넣으면 내신 대비용 분석을 정해진 양식으로 만들어 주는 웹 도구입니다.

- **1. 제목** · **2. 글 개요** · **3. 한줄해석 및 상세 설명**(직독직해, 문법, 어휘, 연결어, 내용 설명) · **4. 글 구조**
- 주제문 ★ 표시, 문장별 공식 해석 대조 검사
- "좌지문 우해석" 한줄해석 PDF를 그대로 읽어 단원·지문·문장을 한 번에 가져오기
- 단원 단위 일괄 분석, 결과 직접 수정
- PDF · Word(.docx) · Markdown 저장, 여러 지문을 골라 한 파일 또는 지문별 .zip으로 저장

## 사용 방법

1. 사이트를 열고 **API 설정**에 Anthropic API 키를 입력합니다. 키는 [Anthropic Console](https://console.anthropic.com/settings/keys)에서 만들 수 있습니다.
2. **단원 불러오기**로 PDF를 올리거나, **+ 지문 추가**로 원문과 해석을 붙여 넣습니다.
3. **단원 전체 분석** 또는 지문별 **분석하기**를 누릅니다.
4. **내보내기**에서 PDF, Word, Markdown으로 저장합니다.

## 개인정보와 비용

- API 키와 분석 결과는 **사용하는 브라우저 안에만** 저장됩니다. 이 사이트에는 서버가 없고, 키는 Anthropic API(`api.anthropic.com`) 외에는 어디에도 보내지 않습니다.
- 분석 요금은 Claude 구독(Pro 등)과 별도로, 입력한 API 키의 계정에 사용량만큼 청구됩니다.
- 공용 컴퓨터에서는 사용 후 **API 설정 → 키 지우기**를 눌러 주세요.

## 구성

- `index.html` — 앱 전체 (HTML · CSS · JavaScript 한 파일)
- `vendor/anthropic-sdk.min.js` — Anthropic TypeScript SDK 1.8.0 브라우저 번들 (MIT, `vendor/LICENSE-anthropic-sdk.txt`)
- PDF 읽기(pdf.js)와 Word·zip 생성(JSZip)은 cdnjs에서 필요할 때 불러옵니다.
