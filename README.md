# gen-ai
kt cloud tech up 교육 자료

> 

---
## 📌 교육 기간: 2026.06.15~2026.07.10 (4주간)
## 📌 교육 로드맵
| Part | 제목 | 끝나면 할 수 있는 것 |
| --- | --- | --- |
| 1 | LLM이 뭔데? | LLM의 강점·한계를 설명하고 도입을 판단한다 |
| 2 | LLM API & 프롬프트 | 프롬프트로 CS 답변·분류 초안을 생성한다 |
| 3 | 동작하는 서비스 | 요약·번역·챗봇을 FastAPI로 서빙한다 |
| 4 | RAG로 문서 QnA | 사내/고객 문서를 근거로 답하는 봇을 만든다 |
| 5 | 성능 평가 | 잘 되는지 수치로 증명하고 약점을 찾는다 |
| 6 | 분류 파인튜닝 | 분류기를 회사 기준에 맞춰 학습·서빙한다 |
| 7 | 통합 & 서빙 | 모든 기능을 하나로 묶어 데모한다 |

---

## 📁 파일 구조

```
gen-ai/                  ← 작업 루트(ROOT)
├── data/                ← 실습 데이터
├── requirements.txt     ← 라이브러리 목록
└── code/                ← (앞으로 만들어나갈 곳)
    ├── ch001_01_practice.ipynb
    ├── ch002_01_practice.ipynb
    └── ...

```

---

## 🗂️ 데이터셋
```
data/
├── cs_inquiries.csv     ← cs 문의 데이터
├── orders.csv           ← 주문정보 데이터 
├── product_reviews.csv
└── product_images/      ← 제품 홍보 이미지
```

---


## 🚀 기술스택
| 영역 | 도구 |
| --- | --- |
| LLM API | Google **Gemini** (`google-genai` SDK, `gemini-2.5-flash`) |
| 오픈소스/파인튜닝 | Hugging Face **Transformers** + **PEFT(LoRA)** |
| 임베딩/검색 | `BAAI/bge-m3`, 리랭커 `bge-reranker-v2-m3` |
| 벡터DB | **Chroma** (`PersistentClient`) |
| 평가 | `evaluate`/`sacrebleu` |
| 서빙/데모 | **FastAPI**, **Gradio** |

---

## ⚙️ 코랩 환경설정
```
# (1) 내 구글 드라이브를 코랩에 연결 (마운트)
from google.colab import drive
drive.mount('/content/drive')   # 실행 → 팝업에서 '허용' 클릭

# (2) 우리 작업 루트(ROOT)와 데이터 폴더(DATA) 경로를 정해 둔다
from pathlib import Path
ROOT = Path('/content/drive/MyDrive/kt cloud tech up/gen-ai')   # 내 드라이브 안의 gen-ai 폴더
DATA = ROOT / 'data'                            # 그 안의 data 폴더 (/ 로 경로를 이어붙임)

print('작업 루트 ROOT :', ROOT)
print('data 폴더 있음 :', DATA.exists())        # True 가 나와야 정상
```

---

## 📚 참고 문헌
- [파이썬은 아는데, LLM은 처음입니다.](https://gen-ai-buildup.vercel.app/index.html)
