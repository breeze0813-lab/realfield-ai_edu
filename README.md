# realfield-ai

엄지희 — 학원장의 언어로, 학부모의 언어로.
한국 교육 현장에 실제로 쓰이는 AI 사용법을 1년간 직접 살아본 사람의 시각으로.

> 본 저장소는 본명 브랜드(AI 교육자) 자료의 정본입니다. 학원 운영 시스템(academy-feedback)과 *분리* 운영합니다.

---

## 페이지 구성 (4개)

| URL | 파일 | 내용 |
|---|---|---|
| `/` | `index.html` | 본 랜딩페이지 — 차별화·사례·강연 메뉴·연락처 |
| `/guide` | `guide.html` | AI 자동화 기본 세팅 가이드 — 인터랙티브 자가 진단 포함 |
| `/practice` | `practice.html` | 페르소나 첫 세팅 15분 실습 — 입력→시스템 프롬프트 자동 생성→복사 |
| `/slides` | `slides.html` | 6/11 학원장 세미나 슬라이드 (Reveal.js 34장) |

각 파일명이 클린 URL과 일치하므로 `cleanUrls: true`만으로 `.html` 없이 접근됩니다 (별도 rewrite 불필요). 구 경로(`ai-guide`·`practice-persona`)는 `vercel.json`의 redirect로 새 경로로 이동합니다.

---

## 디자인 시스템

| 토큰 | 값 |
|---|---|
| Primary | `#1F3864` (Deep Navy) |
| Accent | `#C57B57` (Terracotta) |
| Background | `#FAF7F2` (Ivory) |
| Text | `#2A2A2A` (Soft Black) |
| Font (Sans) | Noto Sans KR (Google Fonts) |
| Font (Serif) | Noto Serif KR (Google Fonts) |

4개 페이지 모두 동일 토큰. 변경 시 4개 파일 모두 수정 필요 (CSS 변수 `--navy`, `--accent` 등).

---

## 운영 정보

- **운영자**: 엄지희 (T-Point Edu 학원장, 거여초 학부모회장, 초4 학부모)
- **이메일**: breeze0813@gmail.com
- **호스팅**: Vercel (정적 사이트)
- **빌드 명령**: 없음 (정적 HTML)
- **빌드 출력**: 루트 디렉토리

---

## 배포

GitHub `main` 브랜치에 push하면 Vercel이 자동 배포.

```bash
git add .
git commit -m "update: ..."
git push origin main
```

배포 URL: `https://realfield-ai.vercel.app`

---

## 페이지별 수정 가이드

### index.html (랜딩페이지)
- 검증 사례 카드: `<section class="cases">` 안의 `.case-card`. 실물 이미지 추가 시 카드 상단에 `<img>` 삽입.
- 운영자 프로필 사진: `[프로필 사진]` placeholder를 실제 `<img>`로 교체. 240×240 권장.

### guide.html (가이드)
- 자가 진단 단계 추가: `<div class="checklist">` 블록을 복사·수정.
- 컬러 변경: `:root` 변수만 수정.

### practice.html (실습)
- 시스템 프롬프트 양식 수정: `<script>` 안 `buildPrompt()` 함수.
- 비교 질문 카드 추가: `<div class="q-cards">` 안에 `<div class="q-card" data-q="...">` 추가.

### slides.html (슬라이드)
- 슬라이드 추가: `<section>` 블록 추가. 발표자 노트는 `<aside class="notes">`.
- 이미지 placeholder 교체: `<div class="ph-img">` 블록을 실제 `<img>`로 교체.
- 인쇄/PDF: URL에 `?print-pdf` 붙이고 브라우저 인쇄 → PDF 저장.

---

## 라이선스

콘텐츠는 운영자 본인이 작성. 외부 라이선스 콘텐츠 없음.
Google Fonts (Noto Sans/Serif KR)와 Reveal.js (MIT)만 외부 의존.

---

## 학원 시스템과의 관계

본 저장소는 *별도 운영*입니다:
- 학원 운영 도구 → [academy-feedback](https://github.com/breeze0813-lab/academy-feedback) (private)
- 본명 브랜드 콘텐츠 → 본 저장소 (public)

두 저장소·도메인·콘텐츠는 *섞이지 않습니다*.
