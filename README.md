# 🎵 Compose Melody - 버튼으로 만드는 나만의 작곡 프로그램

> Java Swing 기반의 GUI 음악 작곡 프로그램
> 버튼 클릭만으로 누구나 쉽게 멜로디를 만들고 재생할 수 있습니다.

<br>

## 📋 프로젝트 정보

| 항목 | 내용 |
|------|------|
| 개발 기간 | 2023.03 ~ 2023.06 |
| 팀 구성 | 3인 팀프로젝트 |
| 담당 역할 | 전체 코드 설계 및 구현 |
| 과목 | 2023-2학기 객체지향프로그래밍 |

<br>

## 📌 프로젝트 소개

복잡한 악보나 음악 지식 없이도 버튼 클릭만으로 멜로디를 작성하고
재생할 수 있는 Java 기반 작곡 프로그램입니다.
8 x 30 격자 형태의 버튼 배열로 음표를 입력하고, Play 버튼으로 바로 들을 수 있습니다.

<br>

## 🛠 기술 스택

| 분야 | 기술 |
|------|------|
| 언어 | Java |
| GUI | Java Swing (JFrame, JPanel, JButton, JSlider) |
| 오디오 | Java Sound API (AudioSystem, Clip) |

<br>

## 👤 내가 맡은 역할

- **전체 코드 설계 및 구현** (SongMaker 클래스 전반)
- 8 x 30 버튼 배열 UI 구현 (GridLayout 활용)
- 버튼 클릭 시 색상 변경 및 음 재생 기능 구현 (`CellClickListener`)
- Play 버튼 클릭 시 **진행 중인 열 하늘색으로 표시**하는 애니메이션 구현 (`updateButtonColors`)
- Reset 버튼으로 전체 버튼 초기화 기능 구현 (`ResetButtonClickListener`)
- Tempo 슬라이더로 재생 속도 조절 기능 구현 (`JSlider`)
- WAV 파일 재생 로직 구현 (`playWAV`, `melodyFind`)

<br>

## ✨ 주요 기능

- **음표 입력**: 8 x 30 격자 버튼 클릭 시 행별 고유 색상으로 변경 (도~높은 도)
- **음 미리 듣기**: 버튼 클릭 시 해당 음의 WAV 파일 즉시 재생
- **멜로디 재생**: Play 버튼 클릭 시 왼쪽 열부터 순차적으로 음 재생
- **진행 열 표시**: 재생 중인 열이 반투명 하늘색으로 표시되어 현재 위치 시각화
- **Tempo 조절**: JSlider로 멜로디 재생 속도 조절 (0~10단계)
- **전체 초기화**: Reset 버튼으로 모든 음표 한 번에 삭제

<br>

## 🎨 음표 색상 구성

| 음 | 색상 |
|----|------|
| 도 (Do) | 🔴 빨강 |
| 레 (Re) | 🟠 주황 |
| 미 (Mi) | 🟡 노랑 |
| 파 (Fa) | 🟢 초록 |
| 솔 (Sol) | 🔵 파랑 |
| 라 (La) | 🩷 분홍 |
| 시 (Si) | 🟣 마젠타 |
| 높은 도 (Do2) | ⚫ 검정 |

<br>

## 📁 프로젝트 구조

```
SongMaker-project/
└── teamproject/
    └── SongMaker.java       # 전체 코드 (황민승 작성)
        ├── SongMaker            # 메인 클래스 (JFrame 상속)
        ├── CellClickListener    # 버튼 클릭 이벤트 처리
        ├── PlayButtonClickListener  # 재생 버튼 이벤트 처리
        ├── ResetButtonClickListener # 초기화 버튼 이벤트 처리
        └── initializeSlider     # Tempo 슬라이더 초기화
```

<br>

## 💡 트러블슈팅 & 배운 점

- **진행 중인 열 색상 표현**: 원래 색상과 반투명 하늘색의 RGB 평균값을 계산하여 자연스러운 오버레이 효과 구현
- **타이머 기반 순차 재생**: `javax.swing.Timer`를 활용해 열마다 일정 간격으로 소리 재생 및 색상 업데이트 구현
- **Java Sound API 예외 처리**: `UnsupportedAudioFileException`, `IOException`, `LineUnavailableException` 3가지 예외 처리로 안정적인 오디오 재생 구현
- 짧은 개발 기간 내 팀원 간 역할을 명확히 분담하여 협업의 효율성 경험

<br>

## 📸 화면 구성

> 추후 스크린샷 추가 예정

<br>

## 👥 팀원

| 이름 | 역할 |
|------|------|
| 조수영 | 팀장, Tempo 슬라이더 구현, PPT 제작 |
| 신예원 | GridLayout 틀 관리, 플레이 버튼 기능 구현 |
| 황민승 | 전체 코드 작성, 버튼 색상 표현, 진행 열 시각화 구현 |
