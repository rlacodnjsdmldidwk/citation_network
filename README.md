# 연구 역량 강화를 위한 논문 인용 네트워크 분석 - 물리학 분야를 중점으로(Analysis of the Papers Citation Network to Strengthen Research Capacity – Focusing on Physics)

> 한국정보기술전략혁신학화(KIITI) 학술대회 2025에 제출한 논문 "연구 역량 강화를 위한 논문 인용 네트워크 분석"의 공식 코드 및 보충 자료 저장소입니다.

**저자:** 이규현(경희대학교 물리학과)

---

## 📂 저장소 구성

이 저장소는 다음과 같이 구성되어 있습니다:

* **code**:
    * `citation_network.ipynb`: OpenAlex API를 사용한 데이터 수집, 네트워크 생성, 커뮤니티 분석, 중심성 계산 등 주요 분석과 결과를 담은 코드

* **file**: 
    * ‘paper_metadata.csv’ : 초기 48,510 편 논문의 메타데이터
    * ‘filtered_paper_metadata.csv’ : 필터링 결과 1,463 편 논문의 메타데이터
    * ‘cluster_node.csv’ : 필터링된 논문들의 커뮤니티 구별
    * ‘cluster_top5_node.csv’ : 논문 수가 많은 5개의 커뮤니티	

* **figures**:
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

* ** tables** :
   * 표 1: 다양한 중심성(centrality) 척도들
| centrality | 설명 | 수학적 정의 | 공식 |
| :--- | :--- | :--- | :--- |
| degree (CDi) | 한 노드와 직접 연결된 엣지의 수 | 노드 i의 연결 수 | $CD_i=k_i$ |
| in-degree (Cini) | 해당 노드를 인용한(가리킨) 다른 노드의 수 | 노드 i에 들어오는 엣지 수 | $C^{in}_i=\sum_j A_{ij}$ |
| out-degree (Couti) | 해당 노드가 인용한(가리키는) 다른 노드의 수 | 노드 i에서 나가는 엣지 수 | $C^{out}_i=\sum_j A_{ij}$ |
| pagerank (PRi) | 중요 노드로부터 연결된 링크의 영향력을 순환적으로 고려한 중심성 | 엣지 기반의 확률적 중요도 | $PR_i=\frac{1-d}{N}+d\sum_{j \in M_i} \frac{PR_j}{L_j}$ |
| eigenvector (xi) | 연결된 노드의 중심성이 높을수록 높은 점수를 받는 지표 | 노드i의 점수는 연결된 노드들의 점수의 선형 결합 | $Ax=\lambda x$ |
| betweenness (btw(i)) | 해당 노드가 다른 노드 간 최단 경로에 얼마나 자주 등장하는지 | 노드i가 최단 경로에 위치한 비율 | $btw_i=\sum_{s \neq i \neq t} \frac{\sigma_{st}(i)}{\sigma_{st}}$ |
