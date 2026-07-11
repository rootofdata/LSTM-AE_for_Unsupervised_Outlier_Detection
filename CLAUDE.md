# 프로젝트
실내 공기질 센서 다변량 시계열의 비지도 이상치 탐지 프레임워크(LSTM-AE 재구성오차 + 잠재공간 OC-SVM + 앙상블)의 정리된 최종본. 논문: doi.or.kr/10.1186/s40537-023-00746-z

# 환경·실행
- 언어: Python 3, Jupyter Notebook (원래 Google Colab에서 작성됨 — `from google.colab import ...` 셀 존재)
- 주요 패키지: tensorflow / keras, tensorflow_addons, scikit-learn(SVM·DBSCAN·GaussianMixture), statsmodels, numpy, pandas, plotly, seaborn, matplotlib, tqdm
- 실행: Jupyter 또는 Colab에서 노트북을 순서대로 실행. 저장소 루트를 작업 디렉터리로 두어야 `data/` 상대경로가 맞음.
- 데이터 위치: `data/` (센서 원본 `device*.csv`, 시뮬레이션 `simul_*.csv`)

# 폴더 구조
- `LSTM-AE Outlier Detection.ipynb` — 메인. LSTM-AE 학습, 재구성오차 기반 탐지
- `Outlier_Algorithm.ipynb` — 잠재특징 DBSCAN·OC-SVM 등 서브 알고리즘·앙상블
- `Simulation Preprocessing.ipynb` — 시뮬레이션 데이터 전처리(정상성 검정·결측 보간·상관분석)
- `LAB TEST.ipynb` — 실험실 AB 테스트 검증
- `data/` — CSV 데이터
- `figure/` — 논문 그림·표 PNG (파일명에 공백·한글 포함)
- `Reference/` — 참고 논문 PDF (약 36MB)

# 컨벤션
- 데이터 참조는 저장소 루트 기준 상대경로(`data/xxx.csv`) 사용.
- 시계열은 시간 컬럼(`Time`, `TsYMD`)을 `index_col`로 지정해 로드.
- 변수 약어: TMP(온도), HMD(습도), TVOC, CO, CO2, CH2O, PM10/PM2.5.

# 주의
- 형제 저장소 `outlier-detection`이 본 프로젝트의 EDA·실험 원본임(코드·데이터가 부분적으로 상호 참조).
- 일부 노트북이 `data/`에 없는 파일명(예: `device08_0713_0720.csv`)을 하드코딩함 — 존재하는 `device11*`, `device16*`로 맞추거나 경로 확인 필요.
- `data/data`는 2바이트짜리 잔존 파일 — 무시하되 삭제하지 말 것.
- 대용량 자산(`data/*.csv`, `figure/*.png`, `Reference/*.pdf`, 모델 `*.pkl`)은 삭제·재생성하지 말 것.
- 노트북을 다른 폴더로 옮기면 `data/` 상대경로가 깨짐 — 이동 시 경로 함께 수정.
- 한글이 포함된 파일명은 NFC로 통일. 캐시(`.ipynb_checkpoints/`, `__pycache__/`)는 커밋 금지.
- Colab 전용 셀(`google.colab`, 드라이브 마운트)은 로컬 실행 시 건너뜀.
