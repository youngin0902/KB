# 녹색금융연구소

AI 기반 저탄소 소비 실천 금융 서비스 **"그린에이전트"**  
개인의 소비 데이터를 분석하여 탄소 배출량을 산출하고, 맞춤형 감축 전략과 ESG 금융 서비스 연계를 제공하는 서비스입니다.

---

## 📌 프로젝트 개요
본 프로젝트는 금융 소비 데이터를 활용해 사용자의 탄소발자국을 정량적으로 측정하고, AI를 통해 친환경 소비 행동을 유도하는 서비스입니다.  
카드 거래 내역을 업종(MCC)으로 분류하고 탄소 배출량을 계산한 뒤, LLM 기반 피드백과 시각화를 통해 사용자의 행동 변화를 지원합니다.

---

## 🛠 주요 기능
1. **소비 데이터 수집**
   - 카드사 API, CSV 파일, 직접 입력 등 다양한 데이터 소스 지원
2. **업종 분류**
   - 카카오 지도 API → MCC(Merchant Category Code) 매핑
3. **탄소 배출량 계산**
   - Mastercard Carbon Calculator API 기반 CO₂e 산출
4. **시각화 대시보드**
   - 업종·기간별 탄소 배출 현황 및 평균 대비 분석
5. **AI 피드백**
   - LLM(Gemini 2.5 Pro) 기반 친환경 소비 행동 추천

---

## 📂 디렉토리 구조 
KB/
├── dataset/
│ ├── final_member.csv # 최종 데이터
│ ├── member.csv # 원본 회원·거래 데이터
│ ├── member_with_category.csv # 업종(category) 매핑 데이터
│ └── member_with_category_mcc.csv # MCC 코드 포함 업종 매핑 데이터
├── main.ipynb # 분석·시각화 메인 노트북
├── README.md
├── requirements.txt
└── .env # API Key 등 환경 변수

## 🚀 Quickstart

1. **가상환경 생성**
   conda create -n KB python=3.12
   conda activate KB

2. **패키지 설치**
   pip install -r requirements.txt

3. **환경 변수 설정**
   - 프로젝트 루트에 `.env` 파일 생성 후 아래 내용 입력:
   ```
   GEMINI_API_KEY=YOUR_GEMINI_API_KEY
   CARBON_API_URL=YOUR_CARBON_API_URL
   KAKAO_API_KEY=YOUR_KAKAO_API_KEY
   ```
4. **프로젝트 실행**