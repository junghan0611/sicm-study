# CLAUDE.md - SICM Study 에이전트 지침

## 이슈 트래킹: bd (beads)

**중요**: 이 프로젝트는 **bd (beads)** 로 모든 이슈를 관리합니다.
마크다운 TODO 리스트나 다른 트래킹 방법을 사용하지 마세요.

### 필수 명령어

```bash
# 작업 찾기
bd ready --json              # 블로커 없는 작업 가능 이슈

# 이슈 생성
bd create "제목" -t bug|feature|task -p 0-4 --json

# 작업 시작/완료
bd update <id> --status in_progress --json
bd close <id> --reason "완료" --json

# 동기화
bd sync                      # 세션 종료 시 필수
```

### 워크플로우

1. `bd ready` 로 작업 가능한 이슈 확인
2. `bd update <id> --status in_progress` 로 작업 시작
3. 코드 구현, 테스트
4. 새 이슈 발견 시: `bd create "제목" --deps discovered-from:<parent-id>`
5. `bd close <id>` 로 완료
6. `.beads/` 파일과 코드 변경사항 함께 커밋

---

## 프로젝트 개요

**sicm-study**: "앎의 구도를 위한 여정"

SICM이라는 이름이지만, SICM은 출발점일 뿐. 궁극적 목표는:
- **자연철학 학습**: 장회익 교수님의 심우십도(十牛圖) 구조
- **표기와 지식의 통합**: 수식 = 코드 (함수형 물리학)
- **에이전트 협력 학습**: 재현 가능한 앎의 체계

## 철학적 배경

### 심우십도 - 앎의 단계

| 단계 | 심우십도 | 자연철학 | 학습 대응 |
|------|----------|----------|-----------|
| 1장 | 소를 찾아 나서다 | 앎의 바탕 구도 | SICP |
| 2장 | 소의 자취를 보다 | 고전역학 | SICM |
| 3장 | 소를 보다 | 상대성이론 | FDG → 일반상대성 |
| 4장 | 소를 얻다 | 양자역학 | 확장 |
| 10장 | 저자거리로 돌아오다 | 온생명 | 보편학 |

### 핵심 참고 자료

- **장회익**: 《자연철학강의》, 《물질, 생명, 인간》 - 한국 자연철학의 틀
- **로저 펜로즈**: 《실체에 이르는 길》 - "비유 아닌 수학으로 쌓아올리기"
- **레너드 서스킨드**: 《물리의 정석》 시리즈 - 단계적 물리학
- **이종필**: 《샐러리맨 아인슈타인 되기》 - 일반인의 수식 이해

## 리포지토리 구조

```
sicm-study/
├── VISION.org           # 철학적 배경 상세
├── README.org           # 학습 가이드
├── CREDITS.org          # 원저자 감사
├── sicp/                # 1단계: 계산적 사고
│   ├── book/sicp.org    # 전체 책 (Babel 실행 가능)
│   └── info/            # Emacs info 버전
├── sicm/                # 2단계: 고전역학
│   ├── book/            # 9개 챕터 (org-mode)
│   ├── reference/       # Sam Ritchie의 Scheme 풀이
│   └── my-solutions/    # 사용자 풀이
├── fdg/                 # 3단계: 미분기하학
│   └── book/            # PDF + Scheme/Clojure 코드
├── foundations/         # 수리물리학 기초 (채워나갈 공간)
│   ├── calculus/
│   ├── linear-algebra/
│   ├── differential-geometry/
│   └── variational-principles/
├── essays/              # Road to Reality (Clerk 에세이)
└── tools/scheme/        # MIT Scheme 설정
```

## 에이전트 역할

### 학습 도우미로서

1. **개념 설명**: 물리학 배경 없이도 이해할 수 있게 단계적으로
2. **수식-코드 연결**: 전통 표기 → Scheme/Clojure 함수형 표현
3. **맥락 제공**: 왜 이 개념이 중요한지, 다음 단계 연결
4. **연습문제 힌트**: 직접 풀이 대신 방향 제시

### 원칙

- **함수형 표기법**: 전통 물리학 표기의 모호성 피하기
- **기하학적 이해**: 수식보다 궤도의 기하학적 특성 파악
- **코드로 검증**: 이해했다면 코드로 표현할 수 있어야 함

## 도구

### Emmy (별도 설치)

```bash
# clone해서 사용
git clone https://github.com/mentat-collective/emmy.git ~/repos/3rd/emmy

# 또는 deps.edn 의존성
{:deps {org.mentat/emmy {:mvn/version "RELEASE"}}}
```

Emmy는 scmutils의 Clojure 재구현:
- 4200+ 테스트
- ClojureScript 지원 (브라우저 실행)
- Clerk 노트북으로 시각화

### Scheme

```bash
# Docker 기반 실행
sicm/reference/bin/mechanics
```

## 사용 예시

```
사용자: "라그랑주 방정식이 뭐야?"
→ 개념 설명 + sicm/book/chapter001.org 참조 + 코드 예시

사용자: "Exercise 1.5 힌트 줘"
→ reference 풀이 참조하지 않고 힌트만

사용자: "변분법 기초가 필요해"
→ foundations/variational-principles/ 에 기록할 내용 제안

사용자: "이 수식을 Scheme으로 어떻게?"
→ 함수형 표기 변환 설명
```

## 관련 문서 (사용자 지식베이스)

사용자의 ~/org/ 에 관련 노트:
- 장회익 자연철학: `bib/20240510T113546--장회익-자연철학-온생명-스승__*.org`
- 펜로즈 RTR: `notes/20241203T142716--로저펜로즈-rtr-실체에이르는길__*.org`
- 서스킨드 물리의정석: `bib/20240515T101158--레너드서스킨트-물리의정석__*.org`
- 이종필 아인슈타인: `bib/20240307T103507--이종필-아인슈타인__*.org`

## 목표

> "그게 완성이 되면 아이들에게 현대 과학지식의 전체 틀을 명확하게 전달할 수 있을 것이다.
> 여기에 에이전트가 확실히 협력할 수 있는 체계가 완성되는 것이다."

**보편학의 기반**: 인간지능과 인공지능이 표기법을 공유하는 학습 체계
