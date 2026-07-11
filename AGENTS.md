# AGENTS.md

AI 코딩 에이전트(범용 도구 포함)를 위한 규칙 문서. Claude 사용 시 CLAUDE.md와 동일 내용.

## 명령
- 실행: Jupyter/Colab에서 노트북을 순서대로 실행. 작업 디렉터리는 저장소 루트(그래야 `data/` 상대경로가 맞음).
- 의존성 설치: `pip install tensorflow tensorflow_addons scikit-learn statsmodels numpy pandas plotly seaborn matplotlib tqdm`

## 프로젝트
실내 공기질 센서 다변량 시계열의 비지도 이상치 탐지 프레임워크(LSTM-AE 재구성오차 + 잠재공간 OC-SVM + 앙상블)의 최종본. 논문: doi.or.kr/10.1186/s40537-023-00746-z

## 환경
- Python 3, Jupyter Notebook (원래 Google Colab 작성 — `google.colab` 셀 존재)
- tensorflow/keras, tensorflow_addons, scikit-learn, statsmodels, numpy, pandas, plotly, seaborn, matplotlib, tqdm
- 데이터: `data/` (센서 `device*.csv`, 시뮬레이션 `simul_*.csv`)

## 폴더 구조
- `LSTM-AE Outlier Detection.ipynb` — 메인(LSTM-AE 학습·재구성오차 탐지)
- `Outlier_Algorithm.ipynb` — DBSCAN·OC-SVM 서브 알고리즘·앙상블
- `Simulation Preprocessing.ipynb` — 시뮬레이션 전처리
- `LAB TEST.ipynb` — 실험실 검증
- `data/` CSV, `figure/` 그림 PNG, `Reference/` 논문 PDF(약 36MB)

## 컨벤션
- 데이터는 루트 기준 상대경로(`data/xxx.csv`). 시계열은 시간 컬럼(`Time`/`TsYMD`)을 인덱스로 로드.
- 변수 약어: TMP, HMD, TVOC, CO, CO2, CH2O, PM10/PM2.5.

## 주의
- 형제 저장소 `outlier-detection`이 본 프로젝트의 EDA·실험 원본.
- 일부 노트북이 `data/`에 없는 파일명(`device08_...`)을 하드코딩 — 존재 파일로 확인·수정.
- `data/data`는 2바이트 잔존 파일 — 무시하되 삭제 금지.
- 대용량 자산(csv/png/pdf/pkl) 삭제·재생성 금지. 캐시(`.ipynb_checkpoints/`, `__pycache__/`) 커밋 금지.
- 한글 파일명 NFC 통일. 노트북 이동 시 `data/` 상대경로 깨짐 주의.
- Colab 전용 셀은 로컬에서 건너뜀.
