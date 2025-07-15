# 📊 생체신호해석 과제 모음

## 👤 학생 정보
- **이름**: 정민섭  
- **소속**: 순천향대학교 의공학과  
- **과목**: 생체신호해석  

---

## 📦 개요

이 저장소는 생체신호해석 수업의 과제들을 정리한 자료입니다. MATLAB을 활용하여 ECG, EEG 데이터를 처리하고, IIR 필터 설계 및 HRV 분석을 수행하였습니다. 각 과제는 주차별로 생체신호에 대한 분석, 알고리즘 구현 및 해석을 포함하고 있습니다.

---

## 📁 과제 목록

### 🔹 9주차: IIR 필터 설계

**과제 목표**  
Butterworth 및 Chebyshev 저역 통과 필터를 주어진 조건에 맞춰 설계하고 주파수 응답과 극점-영점 분포를 시각화합니다.

**주요 내용**  
- 필터 사양: 통과대역, 저지대역, 감쇠량 기준
- `butter`, `cheby1`, `buttord`, `cheb1ord` 함수 사용
- 필터 차수, 차단 주파수 계산 및 시스템 함수 추출

**결과 요약**  
- Butterworth 필터: 차수 3, cutoff = 0.5122  
- Chebyshev 필터: 차수 4, cutoff = 0.6283  
- Butterworth는 리플 없음, Chebyshev는 통과대역 리플 존재

---

### 🔹 10주차: ECG QRS Complex 검출

**과제 목표**  
ECG 신호에서 전처리를 수행한 후 **Pan-Tompkins 알고리즘을 사용해 R-peak 및 QRS complex를 검출**합니다.

**처리 과정**  
1. 60Hz **노치 필터**로 전원 노이즈 제거  
2. 0.5Hz **HPF**로 베이스라인 드리프트 제거  
3. 30Hz **LPF**로 근전도 잡음 제거  
4. `pan_tompkins_R_peak` 함수로 QRS 검출

**결과 요약**  
- QRS 복합파 정확히 검출됨  
- 각 필터 단계별 효과를 시각적으로 확인함

---

### 🔹 11주차: HRV (심박변이도) 해석

**과제 목표**  
QRS 복합파를 이용하여 RR 간격을 계산하고, 시간영역 및 주파수 영역에서 HRV 분석을 수행합니다.

**분석 항목**  
- 시간영역: SDNN, RMSSD, pNN50  
- 주파수영역: nLF, nHF, LF/HF (Lomb-Scargle 방법 사용)

**결과 해석**  
- LF/HF 비율이 낮고, pNN50, RMSSD 수치가 높아 **부교감 신경이 우세한 안정 상태**로 해석됨  
- R-peak 검출을 기반으로 정확한 HRV 계산 수행

---

### 🔹 13주차: EEG 분석 및 Topology Map 시각화

**과제 목표**  
EEG 데이터에서 50Hz 노이즈 제거 및 필터링 후, 주파수 대역별 뇌파(power)를 계산하고 두피에 대한 **topographic map**을 시각화합니다.

**처리 절차**  
1. Notch(50Hz), HPF(0.5Hz), LPF(30Hz) 필터링  
2. Delta, Theta, Alpha, Beta 대역별 power 계산  
3. `eeg_topoplot` 함수로 topology map 시각화  
4. Resting vs Attention 상태 비교, 우수 수행자 분석

**주요 결과**  
- Resting 상태에서는 **Delta, Alpha파**가 강함  
- Attention 상태에서는 전두엽의 **Theta, Beta파**가 강하게 나타남  
- S2가 S1보다 **높은 집중력과 수행능력**을 보이는 것으로 해석됨

---

## 🛠 사용 도구 및 기법

- **언어**: MATLAB  
- **사용 함수**: `filtfilt`, `butter`, `iirnotch`, `bandpower`, `plomb`, `trapz`, `zplane`, `eeg_topoplot` 등  
- **알고리즘**:  
  - Pan-Tompkins QRS Detection  
  - Butterworth & Chebyshev IIR Filter Design  
  - HRV Time & Frequency Domain 분석  
  - EEG Band Power + Topology Map 시각화

---

## 📌 정리

본 과제를 통해 생체신호의 **전처리, 주파수 해석, 그리고 뇌파 및 심전도 신호의 의미 해석** 능력을 키웠습니다. MATLAB을 활용하여 다양한 **생체신호 처리 알고리즘**을 직접 구현하고 시각화함으로써 실전 분석 능력을 높일 수 있었습니다.

