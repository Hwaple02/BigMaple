MapleStory Big Data Analysis System
1. 프로젝트 개요

본 프로젝트는 Nexon Open API를 활용하여 메이플스토리의 랭킹, 캐릭터 스탯, 장비, 유니온, 무릉도장 등의 데이터를 수집하고, Hadoop 기반의 빅데이터 처리 기술을 이용하여 분석 및 시각화를 수행하는 빅데이터 분석 시스템이다.

데이터 수집부터 저장, 전처리, 분석, 시각화까지 전체 파이프라인을 구축하는 것을 목표로 하며, Apache Spark와 Hive를 활용한 분산 데이터 처리 환경을 구현한다.

2. 문제 정의

메이플스토리는 다양한 직업, 서버, 장비 세팅, 강화 요소 등을 가진 대규모 온라인 게임이다. 그러나 게임 내 데이터는 개별적으로만 제공되기 때문에 다음과 같은 질문에 대한 체계적인 분석이 어렵다.

상위 랭커에서 가장 많이 사용되는 직업은 무엇인가?
서버별 직업 분포에는 어떤 차이가 있는가?
캐릭터 능력치와 무릉도장 기록 사이에는 어떤 관계가 있는가?
상위권 유저들은 어떤 장비 세팅을 사용하는가?
업데이트 이후 직업별 랭킹 변화가 발생하는가?

본 프로젝트는 Nexon Open API를 통해 대규모 데이터를 지속적으로 수집하고, Hadoop 기반 분산 처리 시스템을 활용하여 이러한 문제를 분석하고자 한다.

사용 데이터
메이플스토리 종합 랭킹 데이터
캐릭터 기본 정보
캐릭터 능력치 정보
장착 장비 정보
유니온 정보
무릉도장 기록 정보
업데이트 및 이벤트 공지 데이터
데이터 규모
일별 랭킹 데이터 수집
수천 명 이상의 캐릭터 정보 수집
JSON 기반 원본 데이터 저장

최종적으로 100MB 이상의 데이터를 확보할 예정이다.

3. 기술 스택
빅데이터 처리 기술
Apache Hadoop (HDFS)
Apache Spark
Apache Hive
개발 언어 및 처리 도구
Python
PySpark
HiveQL
시각화 도구
Matplotlib
Plotly
데이터 포맷
JSON
CSV
Parquet
4. 시스템 파이프라인
Nexon Open API
        ↓
Python 데이터 수집 스크립트
        ↓
Raw JSON 데이터 저장
        ↓
HDFS 적재
        ↓
Spark DataFrame 전처리
        ↓
Hive 테이블 생성
        ↓
Spark SQL / HiveQL 분석
        ↓
시각화 및 결과 분석
5. 분석 계획

본 프로젝트에서는 다음과 같은 분석을 수행할 계획이다.

상위 랭커에서 직업별 비율 분석
서버별 인기 직업 비교
캐릭터 능력치와 무릉 기록의 상관관계 분석
상위권 유저 장비 세팅 분석
업데이트 이후 직업 점유율 변화 분석
6. GitHub Repository 구조
maplestory-bigdata-analysis/
├── README.md
├── data/
│   └── README.md
├── src/
│   ├── ingest/
│   ├── pipeline/
│   └── analyze/
├── results/
└── report/
7. 실행 환경

본 프로젝트는 강의 실습 환경인 HDP Sandbox 환경에서 실행 가능하도록 구현할 예정이다.

8. 참고 자료
Nexon Open API
Apache Hadoop Documentation
Apache Spark Documentation
Apache Hive Documentation
9. AI 도구 사용 내역
ChatGPT: README 문서 교정 및 미비점 검사
