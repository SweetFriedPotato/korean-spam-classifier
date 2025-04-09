```markdown
# 📬 Korean Spam Mail Classifier (한국어 이메일 스팸 분류기)

딥러닝과 LoRA 기반 파인튜닝을 활용하여 **한국어 이메일**을 스팸과 일반 메일로 분류하는 프로젝트입니다.  
영어 기반 필터에 비해 정확도가 떨어졌던 기존 시스템의 한계를 극복하기 위해 기획되었습니다.

---

## 📌 프로젝트 개요

- **모델**: beomi/KcBERT-base
- **학습 방식**: LoRA (Low-Rank Adaptation)
- **프레임워크**: Hugging Face Transformers + PEFT
- **데이터셋**: 직접 생성한 5,000개 한국어 메일 문장 (스팸/햄 균형 데이터)
- **평가 결과**: Accuracy 100%, F1-score 1.0

---

## 📁 디렉토리 구조

```
korean-spam-detection/
├── spam_dataset_KO.csv               # 학습 데이터셋
├── train_ko_spam_classifier.ipynb    # 학습 코드
├── predict_ko_spam.py                # 추론 코드
└── KO_results/                       # 학습된 모델 저장 디렉토리
    ├── config.json
    ├── pytorch_model.bin
    ├── tokenizer_config.json
    └── vocab.txt
```

---

## 🧠 학습 성능

| 지표           | 값     |
|----------------|--------|
| Accuracy       | 1.0000 |
| F1 Score       | 1.0000 |
| Precision      | 1.0000 |
| Recall         | 1.0000 |
| Eval Loss      | 0.0016 |

---

## 📝 예측 예시

| 이메일 내용                              | 예측  | 신뢰도 |
|------------------------------------------|-------|--------|
| "지금 클릭하고 쿠폰을 받아보세요!"        | SPAM  | 0.999  |
| "프로젝트 회의는 오늘 3시입니다."         | HAM   | 0.999  |
| "비밀번호를 변경해주세요."                | SPAM  | 0.998  |

---

## 🚀 사용 방법

### 1. 학습 실행
```bash
jupyter notebook train_ko_spam_classifier.ipynb
```

### 2. 추론 실행
```bash
python predict_ko_spam.py
```

---

## ✅ 향후 개선 방향

- 메일 전체 본문 구조를 고려한 **문맥 기반 분류**
- **멀티 클래스 분류** (예: 광고 / 보안 / 업무 / 일반 대화 등)
- 서버 배포 및 라이트 버전 모델 구축

---

## 🧑‍💻 개발자

- **이름**: 최지희
- **이메일**: jiheechoi0102@ewhain.net
- **블로그**: [[velog.io/@jihiandcats](https://velog.io/@jihiandcats)]
- 
---

> 한국어 메일에 특화된 AI 필터를 LoRA 기반으로 학습하여, 완성도 높은 실전형 스팸 분류기를 구축
```
