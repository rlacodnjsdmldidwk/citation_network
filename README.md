# 연구 역량 강화를 위한 논문 인용 네트워크 분석 - 물리학 분야를 중점으로
# (Analysis of the Papers Citation Network to Strengthen Research Capacity – Focusing on Physics)

> 한국정보기술전략혁신학회(KIITI) 학술대회 2025에 제출한 논문 "연구 역량 강화를 위한 논문 인용 네트워크 분석"의 공식 코드 및 보충 자료 저장소입니다.

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

* **tables** :
   * 표 1: 다양한 중심성(centrality) 척도들

     
| centrality | 설명 | 수학적 정의 | 공식 |
| :--- | :--- | :--- | :--- |
| degree (CDi) | 한 노드와 직접 연결된 엣지의 수 | 노드 i의 연결 수 | $CD_i=k_i$ |
| in-degree (Cini) | 해당 노드를 인용한(가리킨) 다른 노드의 수 | 노드 i에 들어오는 엣지 수 | $C_{i}^{in}=\sum_{j}A_{ij}$ |
| out-degree (Couti) | 해당 노드가 인용한(가리키는) 다른 노드의 수 | 노드 i에서 나가는 엣지 수 | $C_{i}^{out}=\sum_{j}A_{ij}$ |
| pagerank (PRi) | 중요 노드로부터 연결된 링크의 영향력을 순환적으로 고려한 중심성 | 엣지 기반의 확률적 중요도 | $PR_i=\frac{1-d}{N}+d\sum_{j \in M_i} \frac{PR_j}{L_j}$ |
| eigenvector (xi) | 연결된 노드의 중심성이 높을수록 높은 점수를 받는 지표 | 노드i의 점수는 연결된 노드들의 점수의 선형 결합 | $Ax=\lambda x$ |
| betweenness (btw(i)) | 해당 노드가 다른 노드 간 최단 경로에 얼마나 자주 등장하는지 | 노드i가 최단 경로에 위치한 비율 | $btw_i=\sum_{s \neq i \neq t} \frac{\sigma_{st}(i)}{\sigma_{st}}$ |

   * 표 2: PC loading 값

| | PC1 | PC2 | PC3 | PC4 | PC5 | PC6 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| degree | 0.506 | 0.103 | -0.051 | -0.289 | -0.387 | 0.705 |
| in-degree | 0.510 | -0.021 | 0.073 | -0.401 | -0.401 | -0.698 |
| out-degree | 0.012 | 0.703 | -0.697 | 0.056 | 0.056 | -0.124 |
| eigenvector | 0.474 | -0.107 | -0.083 | 0.869 | -0.046 | 1.94E-14 |
| pagerank | 0.505 | -0.092 | -0.024 | -0.024 | 0.822 | -3.18E-14 |
| betweenness | 0.069 | 0.689 | 0.706 | 0.120 | 0.091 | -4.72E-16 |

   * 표 3: 각 커뮤니티들의 제목과 속한 논문 수

| Community Index | Community Title | Number of papers |
| :--- | :--- | :--- |
| 2 | Ga2O3 기반 광전자 소자 및 자외선 센서 | 334 |
| 0 | 레이저 기술 기반 금속 적층 공정(Addaptive Manufacturing) | 324 |
| 9 | 2D전자소자의 contact engineering | 214 |
| 1 | Ga2O3 기반 초고전력 반도체 소자 | 206 |
| 4 | Ga2O3 기반 반도체의 결함 제어 및 도핑 특성 분석 연구 | 175 |
| 3 | Ga2O3 계열 산화물 반도체의 박막 성장 및 조성 제어 | 74 |
| 6 | 트랩 이온 기반 양자컴퓨팅 및 시뮬레이션 | 69 |
| 5 | Ga2O3 소자의 발열관리 및 열전달 | 46 |
| 8 | Ga2O3 단결정 전위 및 결함 구조 분석 | 11 |
| 7 | Ga2O3 계열 이종접합 구조의 밴드 정렬 및 계면공학 | 10 |

   * 표 4: 주제별 대표 논문 5편

| | Ga2O3 기반 소재 및 소자 | 양자 컴퓨팅(6) | 금속 적층 공정(0) | 2D 전자소자(9) |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Perspective: Ga2O3 for ultra-high power rectifiers and MOSFETS | Crosstalk Suppression for Fault-tolerant Quantum Error Correction with Trapped Ions | Particle-reinforced metal matrix nanocomposites fabricated by selective laser melting: A state of the art review | Approaching the Schottky–Mott limit in van der Waals metal–semiconductor junctions |
| 2 | "Ga2O3 Schottky rectifiers with 1 ampere forward current, 650 V reverse breakdown and 26.5 MW.cm-2 figure-of-merit" | Crossing a topological phase transition with a quantum computer | Is the energy density a reliable parameter for materials synthesis by selective laser melting? | Ultralow contact resistance between semimetal and monolayer semiconductors |
| 3 | Review of gallium-oxide-based solar-blind ultraviolet photodetectors | Scalable and Parallel Tweezer Gates for Quantum Computing with Long Ion Strings | Influence of re-melting on surface roughness and porosity of AlSi10Mg parts fabricated by selective laser melting | van der Waals Stacking Induced Transition from Schottky to Ohmic Contacts: 2D Metals on Multilayer InSe |
| 4 | "Recent progress on the electronic structure, defect, and doping properties of Ga2O3" | Controlling long ion strings for quantum simulation and precision measurements | Emerging metallic systems for additive manufacturing: In-situ alloying and multi-metal processing in laser powder bed fusion | Efficient Ohmic contacts and built-in atomic sublayer protection in MoSi2N4 and WSi2N4 monolayers |
| 5 | Electrical properties of bulk semi-insulating β- Ga2O3 (Fe) | Neural-network variational quantum algorithm for simulating many-body dynamics | An overview of residual stresses in metal powder bed fusion | Universal Fermi-Level Pinning in Transition-Metal Dichalcogenides |

   * 표 5: 시드 논문을 제외한 물리학 연구 분야 네트워크의 상위 10편 핵심 논문

| 순위 | 합성 영향력 점수(PC1) 기준 | 커뮤니티 | 주제 |
| :--- | :--- | :--- | :--- |
| 1 | Perspective: Ga2O3 for ultra-high power rectifiers and MOSFETS | 1 | Ga2O3 기반 연구 |
| 2 | "Ga2O3 Schottky rectifiers with 1 ampere forward current, 650 V reverse breakdown and 26.5 MW.cm-2 figure-of-merit" | 1 | Ga2O3 기반 연구 |
| 3 | Review of gallium-oxide-based solar-blind ultraviolet photodetectors | 2 | Ga2O3 기반 연구 |
| 4 | "Recent progress on the electronic structure, defect, and doping properties of Ga2O3" | 3 | Ga2O3 기반 연구 |
| 5 | Electrical properties of bulk semi-insulating β- Ga2O3 (Fe) | 4 | Ga2O3 기반 연구 |
| 6 | Approaching the Schottky–Mott limit in van der Waals metal–semiconductor junctions | 9 | 금속 적층 공정 |
| 7 | Radiation damage effects in Ga2O3 materials and devices | 4 | Ga2O3 기반 연구 |
| 8 | Editors' Choice—Review—Theory and Characterization of Doping and Defects in β- Ga2O3 | 4 | Ga2O3 기반 연구 |
| 9 | Review of Ga2O3 -based optoelectronic devices | 2 | Ga2O3 기반 연구 |
| 10 | High resistivity halide vapor phase homoepitaxial β- Ga2O3 films co-doped by silicon and nitrogen | 4 | Ga2O3 기반 연구 |

   * 표 6: 주제별 브리지 중심성 상위 논문 5편

| | Ga2O3 기반 소재 및 소자 | 양자 컴퓨팅 | 금속 적층 공정 | 2D전자소자 |
| :--- | :--- | :--- | :--- | :--- |
| 1 | "Deep-ultraviolet integrated photonic and optoelectronic devices: A prospect of the hybridization of group III–nitrides, III–oxides, and two-dimensional materials" | Ytterbium Nuclear-Spin Qubits in an Optical Tweezer Array | Particle-reinforced metal matrix nanocomposites fabricated by selective laser melting: A state of the art review | Ultralow contact resistance between semimetal and monolayer semiconductors |
| 2 | Editors' Choice—Review—Theory and Characterization of Doping and Defects in β- Ga2O3 | Preparation of the SU(3) lattice Yang-Mills vacuum with variational quantum methods | Emerging metallic systems for additive manufacturing: In-situ alloying and multi-metal processing in laser powder bed fusion | van der Waals Integrated Devices Based on Nanomembranes of 3D Materials |
| 3 | Review of gallium-oxide-based solar-blind ultraviolet photodetectors | Raman Scattering Errors in Stimulated-Raman-Induced Logic Gates in Ba133+ | Electrochemical studies on the effect of residual stress on the corrosion of 316L manufactured by selective laser melting | Ohmic Contact Engineering for Two-Dimensional Materials |
| 4 | Enhancing the intrinsic p-type conductivity of the ultra-wide bandgap Ga2O3 semiconductor | A high-fidelity quantum matter-link between ion-trap microchip modules | Laser powder bed fusion for metal additive manufacturing: perspectives on recent developments | Fermi-level depinning of 2D transition metal dichalcogenide transistors |
| 5 | Hydrogen plasma treatment of β- Ga2O3 : Changes in electrical properties and deep trap spectra | A Race-Track Trapped-Ion Quantum Processor | Improvement of corrosion resistance of SS316L manufactured by selective laser melting through subcritical annealing | 2D HfN2/graphene interface based Schottky device: Unmatched controllability in electrical contacts and carrier concentration via electrostatic gating and out-of-plane strain |

## 📄 인용 (Citation)

본 연구를 인용하시려면 다음 정보를 사용해 주십시오:

> 이규현. (2025). 연구 역량 강화를 위한 논문 인용 네트워크 분석. *한국정보기술전략혁신학화(KIITI) 학술대회 논문집*, 00(00), pp.xx-xx.

---

## 📄 라이선스

본 프로젝트의 코드는 [MIT 라이선스](LICENSE) 하에 배포됩니다.
