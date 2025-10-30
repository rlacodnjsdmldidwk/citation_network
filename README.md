# 연구 역량 강화를 위한 논문 인용 네트워크 분석 - 물리학 분야를 중점으로(Analysis of the Papers Citation Network to Strengthen Research Capacity – Focusing on Physics)

> OOO 학술대회 2025에 제출한 논문 "연구 역량 강화를 위한 논문 인용 네트워크 분석"의 공식 코드 및 보충 자료 저장소입니다.

**저자:** 이규현(경희대학교 물리학과)

---

## 📂 저장소 구성

이 저장소는 다음과 같이 구성되어 있습니다:

* **/code**:
    * `citation_network.ipynb`: OpenAlex API를 사용한 데이터 수집, 네트워크 생성, 커뮤니티 분석, 중심성 계산 등 주요 분석과 결과를 담은 코드

* **/file**: 
    * ‘paper_metadata.csv’ : 초기 48,510 편 논문의 메타데이터
    * ‘filtered_paper_metadata.csv’ : 필터링 결과 1,463 편 논문의 메타데이터
    * ‘cluster_node.csv’ : 필터링된 논문들의 커뮤니티 구별
    * ‘cluster_top5_node.csv’ : 논문 수가 많은 5개의 커뮤니티	

* **/figures**:
    * `2000_2024_total_publication_count.png`: (그림 1) 2000-2024동안 발행된 학술 논문 출판 수
    * `cs_publication_count.png`: (그림 1) 2000-2024동안 발행된 cs 분야 학술 논문 출판 수
    * `medicine_publication_count.png`: (그림 1) 2000-2024동안 발행된 medicine 분야 학술 논문 출판 수
    * `physics_publication_count.png`: (그림 1) 2000-2024동안 발행된 physics 분야 학술 논문 출판 수
    * `sociology_publication_count.png`: (그림 1) 2000-2024동안 발행된 sociology 분야 학술 논문 출판 수
    * `publication_trends_by_field.png`: (그림 1) 2000-2024동안 발행된 s각 분야 학술 논문 출판 수 종합
    * `adjacency_matrix.png`: 인용행렬(편)
    * `filtered_adjacency_matrix.png`: 필터링된 인용행렬(편)
    * `network_visualization.png`: 논문 인용 네트워크 시각화
    * `mds.png`: MDS 결과

* ** /tables**:
* 
