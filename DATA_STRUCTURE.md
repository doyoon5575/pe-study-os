# 전공체육 임용 OS 데이터 구조 및 스키마 명세서

## 1. 기출 문항 스키마 (Past Questions Schema)
기출 문항 데이터는 PDF 명세서의 23개 필수 필드를 준수합니다.

```json
{
  "id": "q-2024-A-01",
  "year": "2024",
  "examYear": "2023",
  "period": "1교시",
  "qNumber": 1,
  "type": "단답형",
  "score": 2,
  "mainArea": "체육과 교육과정",
  "midArea": "2022 개정 교육과정",
  "subArea": "성격 및 역량",
  "keywords": ["움직임 수행 역량", "건강관리 역량", "신체활동 문화 향유 역량"],
  "sourceUrl": "https://www.imiso.co.kr/bbs/board.php?bo_table=exam_problem&wr_id=370",
  "sourceName": "한국교육과정평가원 / 아이미소",
  "summary": "2022 개정 체육과 3대 신체활동 역량 중 문화적 가치 향유 역량 작성 문항.",
  "actionRequired": "정의/용어인출",
  "difficulty": "하",
  "frequencyRank": "최빈출",
  "isIncorrect": false,
  "myAnswer": "",
  "modelKeywords": ["신체활동 문화 향유 역량"],
  "reviewDate": "",
  "tags": ["2022개정", "신체활동역량", "출제1순위"],
  "memo": "2015 4대 역량과 2022 3대 역량 명칭 절대 혼동하지 말 것."
}
```

---

## 2. 40일 학습 플랜 스키마 (40-Day Plan Schema)
```json
{
  "day": 12,
  "week": 2,
  "title": "운동생리학 II · 젖산역치·EPOC·피로와 회복",
  "mainArea": "운동생리학",
  "goal": "점증부하 운동 시 젖산역치(LT)와 OBLA 발생 기전을 이해하고, EPOC 구성요소와 피로 요인을 분석한다.",
  "concepts": ["젖산역치(LT)", "OBLA", "EPOC", "산소결손", "글리코겐 고갈", "능동적 회복"],
  "plan2h": "점증부하 운동 시 젖산 축적 그래프 및 EPOC 발생 기전 도식화 (120분)",
  "plan3h": "지구력 트레이닝 전·후 LT 그래프의 우측 이동 기전과 젖산 셔틀 이론 심화 (180분)",
  "pastTask": "2024 A-7번(VO2max), 2022 생리학 피로 기출 풀이",
  "essayTask": "EPOC의 빠른 요소와 느린 요소의 생리학적 발생 원인 서술",
  "shortKeywords": ["젖산역치", "OBLA", "산소결손", "EPOC", "글리코겐 고갈", "능동적 회복"],
  "isCompleted": false,
  "studyMinutes": 0,
  "difficultyRating": 3,
  "mistakeMemo": "",
  "nextReviewDate": ""
}
```

---

## 3. 사용자 영속성 데이터 모델 (LocalStorage `pe_study_os_user_state_v2027`)
- `planStartDate`: 사용자가 지정한 40일 플랜 시작일 (YYYY-MM-DD)
- `planDays`: Day 번호별 완료 상태, 순공 시간, 난이도 체감, 오답 메모
- `cardStats`: 단답형 카드별 박스 등급(1, 2, 3) 및 최근/차기 복습일
- `writingSubmissions`: 서술형 과제별 작성한 개요(draft), 최종본(final), 루브릭 체크 여부
- `mistakes`: 오답 등록 문항 목록 (원인 분류, 재학습 메모, 날짜)
- `mockAnswers`: 모의고사 문항별 정오답 및 획득 점수
- `todayStudyMinutes`: 당일 누적 집중 학습 시간(분)
- `todayReflection`: 일일 회고 (가장 헷갈린 개념, 내일 복습 주제, 만족도)
