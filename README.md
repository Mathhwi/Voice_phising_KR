# Voice_Phishing_KR

**Korean voice phishing dataset (600 phishing + 600 normal)**  
This repository provides a structured Korean-language dataset for voice phishing detection research. The dataset includes Whisper-transcribed and GPT-4.1-cleaned call texts, with scam type annotations based on the Financial Supervisory Service's official classification.

<sub>
📚 **References**  
1. [금융감독원 보이스피싱 피해사례](https://www.fss.or.kr/fss/bbs/B0000203/list.do?menuNo=200686)  
2. [AI Hub 금융상담 콜 데이터셋](https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=98)  
3. [Korean Voice Phishing Detection (Baseline)](https://github.com/selfcontrol7/Korean_Voice_Phishing_Detection)
</sub>

---

## 📦 Dataset Overview

| File Name                | Description |
|--------------------------|-------------|
| `train.csv`              | 1,000 training samples (phishing + normal) with full labels and `label_name` |
| `test.csv`               | 200 evaluation samples with diverse scam types |
| `test+train.csv`         | Combined 1,200-call dataset |
| `train_nolabelname.csv`  | Training set without `label_name` column (for baseline models) |
| `test_nolabelname.csv`   | Test set without `label_name` column |
| `test+train_nolabel.csv` | Fully unlabeled version for unsupervised or pseudo-labeling use |

> - `label`: numerical class index  
> - `label_name`: textual phishing type (e.g., “공공기관 사칭 계좌이체 유도”)  
> - `content`: Whisper-transcribed and GPT-4.1-refined Korean call content  

---

## 📊 Label Distribution (Train vs Test)

The phishing dataset includes 14 types of fraud, annotated according to the Financial Supervisory Service guideline. The test set was constructed with the following strategy:

- **Fraud types with high volume** were proportionally sampled (e.g., “공공기관 사칭 계좌이체 유도”, “인터넷뱅킹·카드론·예금 편취”)
- **Financial consultation-related types** (4 types: “사고및보상문의”, “상품가입및해지”, “이체출금대출서비스”, “잔고및거래내역”) were **evenly sampled, 25 each**
- **Rare scam types** were partially included based on availability

| Scam Type (`label_name`)               | Train Count | Test Count |
|----------------------------------------|-------------|-------------|
| 공공기관 사칭 계좌이체 유도             | 280         | 48          |
| 인터넷뱅킹·카드론·예금 편취             | 199         | 33          |
| 사고및보상문의                         | 150         | 25          |
| 상품가입및해지                         | 150         | 25          |
| 이체출금대출서비스                     | 150         | 25          |
| 잔고및거래내역                         | 150         | 25          |
| 자동화기기로 유인하여 자금 편취        | 31          | 5           |
| 상황극 연출로 피해자 기망              | 28          | 5           |
| 신용카드 정보+ARS 카드론 유도          | 20          | 3           |
| 전화로 텔레뱅킹 정보 취득 후 이체       | 13          | 2           |
| 금감원 사칭 긴급공지 문자+피싱사이트 유도 | 12          | 2           |
| 자녀납치 및 사고 빙자 편취             | 8           | 1           |
| 오류 송금 빙자 편취                    | 8           | 1           |
| 메신저상 지인 사칭 송금 요구           | 1           | 0           |
![원본데이터_분포](https://github.com/user-attachments/assets/e79751f9-dc53-4000-977f-5c31c6d9685d)
![test_train_분할분포](https://github.com/user-attachments/assets/6aaf783f-dedc-4454-b376-92803b893bb0)

---

## 🧪 Use Cases

- Voice phishing detection using LLMs (GPT, Gemini, Solar, etc.)
- Semi-supervised learning with pseudo-labeling
- Retrieval-augmented generation (RAG) experiments with label metadata

---

## 📥 Dataset Access

- 📦 Download full dataset: [`Voice_Phishing_KR`](https://github.com/Mathhwi/Voice_phising_KR)

---

## 📄 Citation

```bibtex
@misc{voicephishing2024,
  title={Voice_Phishing_KR: Korean Voice Phishing Detection Dataset},
  author={Mathwi},
  year={2024},
  url={https://github.com/Mathwi/Voice_Phishing_KR}
}

## 📬 Contact
For questions or collaborations, please contact [rlarjsgnl@sogang.ac.kr]
