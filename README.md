# 한국어 서사 복원 프로젝트(Korean narrative mining project)
한국어 서사 복원 프로젝트에 대한 자세한 사항은 [클리오사회발전연구소](https://sites.google.com/clioisds.org/clioisds/research/narrative-mining) 홈페이지에서 확인하실 수 있습니다. 
<br>본 페이지는 클리오사회발전연구소의 한국어 서사 복원 프로젝트(Korean narrative mining project)의 일환으로 구축된 CLIO SRL 데이터셋과 정보를 제공합니다.
* 한국어 서사 복원 프로젝트에서는 사회과학 특성을 반영한 의미역결정(Sementic Role Labeling, SRL) 예측 모델 개발을 위한 학습 데이터셋으로 CLIO SRL 데이터셋을 구축했습니다.
* CLIO SRL 데이터셋은 휴먼코더(Human Coders)들이 각 문장에 대해 의미역결정(SRL: Sementic Role Labeling) 작업을 진행한 뒤 언어모델이 학습 가능한 형태로 전처리하여 제공됩니다.
<br>

# 데이터셋 구성
CLIO SRL 데이터셋은 현재 구축 중에 있으며, 향후 데이터에 대한 업데이트가 이루어질 예정입니다(현재: ver1).
* CLIO SRL 데이터셋을 구성하기 위해 한국학술인용색인(KCI: Korea citation index)의 사회과학 분야 논문 초록과 사회분야 뉴스기사 자료를 수집했습니다.
* 논문 초록은 KCI에서 2019년 1월부터 2023년 6월까지 등재된 ‘사회학’ 및 ‘사회과학일반’ 중분류 분야 논문 초록 총 8,383편을 크롤링 방식으로 수집하였으며, 뉴스기사의 경우 동일 기간인 2019년 1월부터 2023년 6월까지 사회분야 뉴스기사 총 417,631편의 각 기사 본문 중 첫 문단을 한국언론재단이 운영하는 빅카인즈(Bigkinds)에서 제공받아 사용합니다. 
* 수집된 자료는 문장 단위로 분류하여 자료 중 무작위 KCI 논문초록 500문장, 뉴스기사 500문장 총 1,000문장에 대해 SRL 작업을 진행했으며, 1,653개의 인스탄스를 추출했습니다.
* 휴먼코더(Human Coders)는 의미역 중 ARG0, ARG1, Predicate를 분류하는 SRL 작업을 수행했습니다.
* SRL의 판단 기준은 국립국어원의 의미역 분석 말뭉치가 제공하는 기준을 따릅니다.
  <br>국립국어원. (2021). 국립국어원 의미역 분석 말뭉치(버전1.0) URL: https://kli.korean.go.kr/corpus
<br>

|Column|설명|
|:---|:---|
|id|문장이 포함되어있는 전체 기사 또는 논문 초록의 고유값|
|id_sequence|문장의 고유값|
|srl_sequence|문장에서 술어를 중심으로 중첩문장을 분리 후 추출한 triplet의 고유값|
|type|문장의 출처, 기사는 0, 논문 초록은 1의 값|
|line|문장|
|arg0|서술어의 동작주, 행위자(agent), 경험주(experiencer)|
|arg1|서술어의 피동작주(patient), 대상(theme) 등|
|predicate|서술어|
|lemma|서술어의 원형(Lemmatization)|
|negative|추출한 predicate가 부정적 의미일 경우 1, 긍정적 의미일 경우 0의 값|
|arg0_index|ARG0의 문장 내 index번호|
|arg1_index|ARG1의 문장 내 index번호|
pred_index|Predicate의 문장 내 index번호|
|word_id|공백을 기준으로 문장을 분리, 분리된 문장의 부분들은 하나의 요소로 보고 리스트의 형태로 변환|
<br>

# 문의
admin@clioisds.org


  
