---
title: "2024 AAS CanSat Competition"
excerpt: "American Astronautical Society(AAS) 주관 캔위성 경연대회 하드웨어 설계 및 제작 프로젝트"
layout: single # 테마 적용
auther_profile: true # true: 왼쪽에 프로필 띄움
header:
  teaser: /assets/images/CanSat/b.gif  # [핵심] 카드에 보일 움짤/이미지 경로
  overlay_image: /assets/images/CanSat/1.jpg # 상세 페이지 상단에 뜰 배경 이미지 (선택)
  overlay_filter: 0.5 # 배경 이미지 어둡게 처리
toc: true
toc_sticky: true
sidebar:
  nav: "counts" # (선택사항) 왼쪽 메뉴
categories:
  - Project
tags:
  - Aerospace
  - Satellite
  - HW_design
last_modified_at: 2026-01-30
project_images:
  - /assets/images/CanSat/1.jpg
  - /assets/images/CanSat/2.png
  - /assets/images/CanSat/b.gif
  - /assets/images/CanSat/3.jpg
  - /assets/images/CanSat/4.jpg
  - /assets/images/CanSat/5.jpg
  - /assets/images/CanSat/6.jpg
  - /assets/images/CanSat/7.jpg
  - /assets/images/CanSat/8.jpg
  - /assets/images/CanSat/9.jpg
  - /assets/images/CanSat/10.jpg
  - /assets/images/CanSat/a.gif
  - /assets/images/CanSat/11.jpg
  - /assets/images/CanSat/12.jpg
  - /assets/images/CanSat/13.jpg
  - /assets/images/CanSat/14.jpg
  - /assets/images/CanSat/15.jpg
---

## 프로젝트 개요

American Astronautical Society(AAS)와 NASA 등이 주관하는 국제 캔위성 경연대회(AAS CanSat Competition)에 참가했던 프로젝트입니다. 대회에서 요구하는 복합적인 임무 시나리오를 수행할 수 있는 캔위성을 설계, 제작, 발사하여 데이터를 수신하는 것이 목표입니다.

저는 **하드웨어 팀(Mechanical Team)** 소속으로 캔위성의 구조 설계, 메커니즘 구현, 그리고 제작을 전담했습니다.

###  2024 Mission Profile
이번 대회의 핵심 미션은 **대기권 재진입 시뮬레이션**입니다.

<figure style="text-align: center; margin: 20px 0;">
  <img src="/assets/images/CanSat/mission-profile.png" alt="Mission Profile Diagram" style="max-width: 100%; height: auto;">
  <figcaption style="font-size: 0.8em; color: gray;">[그림 1] 2024 CanSat Competition Mission Profile</figcaption>
</figure>

1. **Deploy:** 고도 725m에서 로켓으로부터 캔위성 사출
2. **Aero-braking:** Heat Shield를 전개하여 공기 저항으로 감속 ($10m/s \sim 30m/s$) 및 노즈콘 분리
3. **Descent:** 고도 100m에서 Heat Shield 분리 후 낙하산 전개 ($< 5m/s$)
4. **Landing:** 페이로드(달걀) 손상 없이 안전 착륙

**핵심 과제:**
가장 중요한 미션은 **Heat Shield를 이용한 효과적인 공력 감속(Aero-braking)**과 착륙 시 충격으로부터 **페이로드(달걀)를 완벽하게 보호**하는 구조 설계였습니다.

<br>

##  프로젝트 수행 기간 및 일정
**2023.09 - 2024.06 (약 10개월)**

|   시기    |     단계     | 주요 내용                                                                                                                                                                                                                                                              |
| :-----: | :--------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2024.03 |  **PDR**   | 예비 설계 검토 (Preliminary Design Review) 발표                                                                                                                                                                                                                            |
| 2024.04 |  **CDR**   | 상세 설계 검토 (Critical Design Review) 발표                                                                                                                                                                                                                               |
| 2024.05 |  **Test**  | 환경 평가 자료 제출 및 최종 기능 점검                                                                                                                                                                                                                                             |
| 2024.06 | **Flight** | **Competition (Monterey, VA)** <br> - Flight Readiness Review (6/7) <br> - Launch Operation @ [Jack Mountain Village](https://www.google.com/maps/search/?api=1&query=3003+Jackson+River+Rd,+Monterey,+VA+24465) (6/8) <br> - Post Flight Review (6/9)<br><br><br> |

<br>

##  주요 수행 업무 (Hardware Design)

### 1. 미션 메커니즘 설계
미션 시나리오의 성공적인 수행을 위해 초기 개념 설계를 주도했습니다. 특히 Heat Shield의 전개 및 분리 시퀀스, 각 모듈(배터리, 센서, 페이로드)의 최적 배치를 통한 무게 중심(CG) 설정을 수행했습니다.

### 2. 상세 하드웨어 설계 (Detail Design)

#### **Heat Shield 메커니즘 선정**
공기 저항을 극대화하기 위해 두 가지 방식을 비교 분석했습니다.
* **A안 (Origami):** 종이접기 방식. 공간 효율은 좋으나 고토크 서보모터가 필요하고, 전개 시 회전 발생으로 인한 불안정성 및 중량 초과 위험이 있어 배제했습니다.
* **B안 (Umbrella Type - 채택):** 우산형 전개 방식. 스프링의 탄성력을 이용한 **Passive Deployment** 방식을 적용했습니다. 로켓 사출 즉시 별도의 전력 소모 없이 신속하게 전개되며, 구조적으로 간단하여 **신뢰성(Reliability)**과 **경량화** 측면에서 유리하다고 판단했습니다.
#### **Egg Container**
깨지기 쉬운 달걀(페이로드)을 보호하기 위해 다중 충격 흡수 구조를 적용했습니다.
* **Floating Structure:** 고무 댐퍼를 사용해 컨테이너를 위성 본체와 이격(Floating)시켜 1차 충격을 감쇠했습니다.
* **Internal Volume:** 컨테이너 내부 용적을 최대화하여 완충재의 밀도를 높일 수 있도록 설계했습니다.
#### **Aerodynamic Fins (Stability Control)**
낙하 중 카메라의 시야각(FOV) 확보를 위해 위성의 회전(Spin) 제어가 필수적이었습니다.
* **Dual-Phase Fin:** Heat Shield 전개 시에는 Heat shield 전방의 3개 Fin이, 분리 후에는 낙하산 모듈의 앞의 2개 Fin이 순차적으로 작동하여 전 구간에서 공력 안정성을 확보했습니다.
#### **Nose Cone & Fairing**
* **외부 노즈콘 (Fairing Nose Cone):** Von Karman Ogive 형상을 기반으로 설계하여 로켓 상승 시 항력을 최소화했습니다.
* **내부 노즈콘(Satellite Nose Cone):** 내부 안테나, 센서, 카메라 모듈을 외부 충격으로부터 보호하는 하우징을 설계했습니다.
### 3. 하드웨어 통합 및 제작 (Integration)
설계된 모델을 3D 프린팅 및 가공을 통해 실제작했습니다. 제작 과정에서 **전체 중량 제한(900g)**을 준수하기 위해 설계를 단순화 하고, 내부 채움(Infill)을 조절하는 등 설계를 경량화 방향으로 최적화했습니다.

<br>

## 프로젝트 결과
#### 대회 성과
* **종합 15위 달성** (Top 15 / 40 Global Teams)
* 총점: **89.1056%**
* **우수활동상 수상:** 2024 외부경진대회 및 공모전 참가 지원사업 (인하대학교 LINC 3.0 사업단)
* **포스터 발표:** 2024 우주학술대회 참가 및 포스터 세션 발표

#### 대회 활동 모습
*(좌우 화살표를 눌러 현장 사진을 확인하세요)*

{% include carousel.html id="cansat-gallery" images=page.project_images %}

<br>

#### 프로젝트 자료 다운로드
설계 및 심사 과정에서 작성한 기술 문서입니다.

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 20px; text-align: center; margin-top: 30px; margin-bottom: 50px;">

  <div style="display: flex; flex-direction: column; align-items: center;">
    <a href="/assets/files/CanSat/PDR.pdf" target="_blank" style="text-decoration: none;">
      <img src="/assets/images/CanSat/thumb_pdr.png" alt="PDR 표지" 
           style="width: 100%; max-width: 200px; border: 1px solid #ddd; box-shadow: 3px 3px 10px rgba(0,0,0,0.2); border-radius: 5px; transition: transform 0.2s;">
    </a>
    <span style="margin-top: 10px; font-weight: bold; color: #555;">📕 PDR 자료</span>
  </div>

  <div style="display: flex; flex-direction: column; align-items: center;">
    <a href="/assets/files/CanSat/CDR.pdf" target="_blank" style="text-decoration: none;">
      <img src="/assets/images/CanSat/thumb_cdr.png" alt="CDR 표지" 
           style="width: 100%; max-width: 200px; border: 1px solid #ddd; box-shadow: 3px 3px 10px rgba(0,0,0,0.2); border-radius: 5px; transition: transform 0.2s;">
    </a>
    <span style="margin-top: 10px; font-weight: bold; color: #555;">📘 CDR 자료</span>
  </div>

  <div style="display: flex; flex-direction: column; align-items: center;">
    <a href="/assets/files/CanSat/EnvTest.pdf" target="_blank" style="text-decoration: none;">
      <img src="/assets/images/CanSat/thumb_env.png" alt="환경평가 표지" 
           style="width: 100%; max-width: 200px; border: 1px solid #ddd; box-shadow: 3px 3px 10px rgba(0,0,0,0.2); border-radius: 5px; transition: transform 0.2s;">
    </a>
    <span style="margin-top: 10px; font-weight: bold; color: #555;">📗 환경평가 자료</span>
  </div>

  <div style="display: flex; flex-direction: column; align-items: center;">
    <a href="/assets/files/CanSat/PFR.pdf" target="_blank" style="text-decoration: none;">
      <img src="/assets/images/CanSat/thumb_pfr.png" alt="PFR 표지" 
           style="width: 100%; max-width: 200px; border: 1px solid #ddd; box-shadow: 3px 3px 10px rgba(0,0,0,0.2); border-radius: 5px; transition: transform 0.2s;">
    </a>
    <span style="margin-top: 10px; font-weight: bold; color: #555;">📙 PFR 자료</span>
  </div>

  <div style="display: flex; flex-direction: column; align-items: center;">
    <a href="/assets/files/CanSat/Conference_Poster.pdf" target="_blank" style="text-decoration: none;">
      <img src="/assets/images/CanSat/thumb_poster.png" alt="포스터 미리보기" 
           style="width: 100%; max-width: 200px; border: 1px solid #ddd; box-shadow: 3px 3px 10px rgba(0,0,0,0.2); border-radius: 5px; transition: transform 0.2s;">
    </a>
    <span style="margin-top: 10px; font-weight: bold; color: #d9534f;">📄 우주학술대회 포스터</span>
  </div>

</div>
<br>

## Troubleshooting & Engineering Insights

최종 비행(Flight) 미션은 절반의 성공과 절반의 실패를 남겼습니다. 하지만 이 과정에서 발생한 기계적, 전자적 결함을 분석하며 엔지니어로서 가장 많이 성장할 수 있었습니다.

### 1. Mission Result Overview
* **성공 (Success)**
  * **Payload Protection:** 낙하산 전개 실패로 인한 빠른 추락 속도에도 불구하고, **Egg Container의 충격 흡수 설계가 완벽하게 작동하여 달걀이 깨지지 않고 회수**되었습니다.
  * **Data Recovery:** 온보드 메모리(SD Card)를 통해 비행 영상과 로그 데이터를 확보하여 사후 분석을 수행할 수 있었습니다.
* **실패 (Failure)**
  * **Telemetry Loss:** 비행 중 지상국(GCS)과의 실시간 데이터 통신이 끊겼습니다.
  * **Deployment Failure:** 낙하산 모듈 파손으로 인해 감속 시스템이 정상적으로 전개되지 않았고, 이로 인해 Heat Shield 분리 시퀀스가 실패했습니다.

### 2. Failure Analysis & Corrective Actions
가장 치명적이었던 두 가지 문제에 대한 **근본 원인 분석**과 **개선책**입니다.

#### **Issue 1: 낙하산 조기 전개 및 구조적 파손**
**문제 상황:** 로켓에서 위성 사출 시 폭약의 충격을 견디지 못하고 낙하산 구조물이 파손되었습니다. 이로 인해 낙하산이 예정된 고도보다 일찍 전개되었으며, 완전한 낙하산 전개에 실패했습니다.

* **원인 분석 (Root Cause)**
  1. **구조 설계의 문제:** 위성의 중량 제한(900g)을 준수하기 위해 구조물을 경량화하는 과정에서 낙하산 모듈의 강성이 약해져 충격에 취약해졌습니다.
  2. **소재 선정의 한계:** PLA/ABS 등 일반적인 3D 프린팅 소재는 비강도(Specific Strength)가 낮아 순간적인 발사 충격을 견디기에 부족했습니다.
* **기술적 개선안 (Solution)**
  * **Advanced Materials:** 하중을 집중적으로 받는 주요 부품은 **Carbon Composite**나 **발사 나무(Balsa Wood)**와 같이 가볍지만 강성이 뛰어난 소재로 변경하여 내구성을 확보해야 합니다.

#### **Issue 2: 통신 두절 (Telemetry Lost)**
**문제 상황:** 발사 직후 지상국(Ground Station)으로 들어오는 패킷이 끊겼으며, 비행 데이터를 실시간으로 확인할 수 없었습니다.

* **원인 분석 (Root Cause)**
  1. **Antenna Alignment:** 지향성 패널 안테나를 사용했으나, 육안으로 빠르게 움직이는 캔위성을 정확히 조준(Aiming)하는 데 실패했습니다.
* **기술적 개선안 (Solution)**
  * **Antenna Scope:** 안테나에 조준경(Scope) 부착하여 시각적 추적의 정확도를 높이고, 지향각 오차를 최소화합니다.

### 3. Lessons Learned
1. **Aerodynamic Forces:** 중량 제한에만 집중한 나머지 구조 안정성을 충분히 고려하지 못하였고, 그 결과 공력과 사출 충격에 의해 위성이 파손되었습니다. 이를 통해 설계 시 **구조적 안전율(Safety Factor)을 보수적으로 적용**해야 함을 배웠습니다.
2. **Fail-Safe Design:** 1차 시스템(낙하산)이 실패했을 때를 대비한 백업 시스템이 부족했습니다. 낙하산 모듈의 파손이 곧 다른 파트의 연쇄적인 실패로 이어지는 것을 보며, **Fail-Safe를 고려한 시스템 설계의 중요성**을 깨달았습니다.
