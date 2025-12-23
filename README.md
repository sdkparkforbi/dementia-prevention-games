# 🧠 두뇌 건강 전통놀이 (Dementia Prevention Games)

어르신들을 위한 인터랙티브 치매예방 게임 모음입니다.  
한국 전통 놀이를 기반으로 한 6가지 두뇌 훈련 게임과 MySQL 기반 점수 저장 시스템을 제공합니다.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![PHP](https://img.shields.io/badge/PHP-7.4+-purple.svg)
![MySQL](https://img.shields.io/badge/MySQL-5.7+-orange.svg)

---

## 🎮 게임 목록

| 게임 | 설명 | 두뇌 훈련 효과 |
|------|------|---------------|
| 🎴 화투 짝맞추기 | 뒤집어진 화투 패의 짝을 찾기 | 단기 기억력 |
| 🎯 윷놀이 | 윷을 던져 도착점까지 이동 | 판단력, 기대감 |
| 🔢 숫자 기억하기 | 화면에 나타난 숫자 순서대로 입력 | 작업 기억력 |
| 📜 속담 완성하기 | 한국 전통 속담의 빈 칸 채우기 | 언어능력, 장기기억 |
| 🧮 산수 계산 | 간단한 덧셈/뺄셈 문제 | 계산력, 집중력 |
| 🔄 순서 맞추기 | 그림을 논리적 순서로 배열 | 논리력, 추론능력 |

---

## 📁 프로젝트 구조

```
dementia-prevention-games/
├── index.html          # 메인 게임 페이지
├── api.php             # 백엔드 API (점수 저장/조회)
├── db_config.php       # 데이터베이스 연결 설정
├── setup_database.sql  # DB 초기화 스크립트
└── README.md           # 프로젝트 설명
```

---

## 🚀 설치 방법

### 1️⃣ 요구사항

- PHP 7.4 이상
- MySQL 5.7 이상 또는 MariaDB 10.2 이상
- 웹 서버 (Apache, Nginx 등)

### 2️⃣ 데이터베이스 설정

```bash
# MySQL에 접속하여 SQL 스크립트 실행
mysql -u your_username -p < setup_database.sql
```

또는 phpMyAdmin에서 `setup_database.sql` 파일을 가져오기(Import) 합니다.

### 3️⃣ DB 연결 정보 수정

`db_config.php` 파일을 열어 본인의 DB 정보로 수정합니다:

```php
$host = 'localhost';        // DB 호스트
$username = 'your_user';    // DB 사용자명
$password = 'your_pass';    // DB 비밀번호
$database = 'dementia_games'; // DB 이름
```

### 4️⃣ 파일 업로드

모든 파일을 웹 서버에 업로드합니다.

### 5️⃣ 접속

브라우저에서 `http://your-server/index.html` 접속

---

## 🗃️ 데이터베이스 구조

### game_records 테이블

| 컬럼 | 타입 | 설명 |
|------|------|------|
| id | INT | 기록 ID (자동증가) |
| player_name | VARCHAR(50) | 플레이어 이름 |
| session_number | INT | 회차 번호 |
| hwatu_score | INT | 화투 짝맞추기 점수 |
| yut_score | INT | 윷놀이 점수 |
| memory_score | INT | 숫자 기억하기 점수 |
| proverb_score | INT | 속담 완성하기 점수 |
| calc_score | INT | 산수 계산 점수 |
| sequence_score | INT | 순서 맞추기 점수 |
| total_score | INT | 총점 |
| created_at | TIMESTAMP | 기록 생성 시간 |

---

## 📡 API 엔드포인트

| 액션 | 메소드 | 설명 |
|------|--------|------|
| `save` | POST | 게임 기록 저장 |
| `get_records` | GET | 개인 기록 조회 |
| `get_ranking` | GET | 전체 랭킹 조회 |
| `get_today` | GET | 오늘의 기록 조회 |
| `get_stats` | GET | 개인 통계 조회 |

---

## 🎨 주요 기능

- ✅ **전통 한국 디자인**: 단청 색상, 한지 배경
- ✅ **시니어 친화적 UI**: 큰 글씨, 큰 버튼
- ✅ **즉각적인 피드백**: 정답/오답 시각적 반응
- ✅ **점수 저장 시스템**: MySQL 기반 기록 관리
- ✅ **회차 자동 관리**: 같은 이름으로 플레이 시 회차 증가
- ✅ **랭킹 시스템**: 전체 랭킹 및 오늘의 기록
- ✅ **개인 통계**: 게임별 최고 기록, 평균 점수
- ✅ **반응형 디자인**: PC, 태블릿, 모바일 지원

---

## 📜 라이선스

MIT License - 자유롭게 사용, 수정, 배포 가능합니다.

---

💡 **Tip**: 매일 조금씩, 건강한 두뇌를 위한 즐거운 습관! 🌿
