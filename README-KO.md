# SICM Study - 유연한 설계의 내재화

[![English](https://img.shields.io/badge/lang-English-blue)](README.md)

> "프로그래밍은 단순히 도구가 아니라 **이해의 검증 도구**이다."
> — Gerald Jay Sussman & Jack Wisdom, SICM 서문

> "비유를 통해 설명하기보다는 처음부터 수학적 내용을 하나씩 쌓아올리며 결론에 도달한다."
> — 로저 펜로즈, 《실체에 이르는 길》

> "구현 자체는 더 이상 문제가 아니다. 오케스트레이션도 가능하다. 남은 것은 **유연한 설계의 내재화**다."
> — AI 에이전트 시대를 살며

## 왜 이 리포지토리인가?

AI 에이전트 시대에 **구현 자체는 더 이상 병목이 아닙니다**. 에이전트는 코드를 작성하고, 복잡한 워크플로우를 조율하고, 시스템에 대해 추론할 수 있습니다. 하지만 그들이 단순히 다운로드할 수 없는 것이 있습니다: **유연한 설계에 대한 깊은 직관**.

이 리포지토리는 소프트웨어를 적응 가능하고, 확장 가능하고, 변화에 탄력적으로 만드는 **설계 원칙을 내재화**하기 위한 학습 공간입니다. 계산적 사고에서 물리학을 거쳐, 진화할 수 있는 시스템을 구축하는 기술까지의 지적 계보를 추적합니다.

*sicm-study*라는 이름이지만, SICM은 출발점일 뿐입니다.
궁극적 목표와 철학적 배경은 [VISION.md](VISION.md)를 참고하세요.

## 지적 계보 (Intellectual Lineage)

```
                        ┌─────────────────────────────────────┐
                        │         SUSSMAN'S UNIVERSE          │
                        └─────────────────────────────────────┘

  ┌─────────────────────────────────────────────────────────────────────────┐
  │  계산적 사고                            유연한 설계                     │
  │                                                                         │
  │  SICP (1985)                            SDF (2021)                      │
  │  컴퓨터 프로그램의                       Software Design for Flexibility │
  │  구조와 해석                             "첨가적 프로그래밍"             │
  │  "프로그램 = 수학적 표현"                "진화하는 시스템"               │
  │       │                                      │                          │
  └───────┼──────────────────────────────────────┼──────────────────────────┘
          │                                      │
          ▼                                      ▼
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  코드로서의 물리학                                                      │
  │                                                                         │
  │  SICM (2001)                 FDG (2013)                                 │
  │  고전역학                     미분기하학                                │
  │  라그랑주/해밀턴 역학        일반상대성이론으로 가는 길                 │
  │  "수식 = 코드"               "기하학 = 계산"                            │
  │       │                           │                                     │
  │       └───────────┬───────────────┘                                     │
  │                   ▼                                                     │
  │  Emmy (2020~)     Clojure 재구현                                        │
  │                   브라우저 + 시각화 + 현대적 에코시스템                  │
  └─────────────────────────────────────────────────────────────────────────┘

  ┌─────────────────────────────────────────────────────────────────────────┐
  │  물리학 기초                                                            │
  │                                                                         │
  │  서스킨드의 Theoretical Minimum                                         │
  │  고전역학 → 양자역학 → 일반상대성이론                                   │
  │  "다음 단계로 가기 위해 필요한 것만"                                     │
  └─────────────────────────────────────────────────────────────────────────┘
```

### 왜 이 계보인가?

Seymour Papert의 Logo에서 시작된 "구성주의 학습"이 Gerald Sussman을 통해 물리학의 핵심까지 이어집니다. 수학적 도구로서 *수식과 코드가 동일*하다는 것, 이것이 *보편학(Universal Science)*의 기반입니다.

**SDF**는 결정적인 차원을 더합니다: 다시 작성하지 않고도 **진화할 수 있는** 시스템을 어떻게 구축하는가. AI 에이전트 시대에 이것은 단순한 좋은 관행이 아니라—번창하는 시스템과 레거시가 되는 시스템 사이의 **차별화 요소**입니다.

### 핵심 통찰: 첨가적 프로그래밍 (Additive Programming)

SDF의 중심 테제:

> **첨가적 프로그래밍**은 기존의 작동하는 코드를 수정하지 않고 새로운 코드를 추가함으로써 새로운 상황에 쉽게 적응할 수 있는 대규모 시스템을 구축하는 전략이다.

핵심 기법:
- **제네릭 프로시저**: 확장성을 위한 동적 디스패치
- **콤비네이터**: 수정 없이 행동을 조합
- **전파자(Propagators)**: 분산 계산 모델
- **생성자와 검사자의 분리**: 독립적 진화

### Scheme에서 Clojure로

| 특성 | scmutils (Scheme) | Emmy (Clojure) |
|------|-------------------|----------------|
| 런타임 | MIT Scheme | JVM, JavaScript |
| 시각화 | X Window | Clerk, 브라우저 |
| 에코시스템 | 제한적 | Maven, npm |
| 구조분해 | let/ref | `[[_ [r] [rdot φdot]]]` |

## 구조

```
sicm-study/
├── sicp/                    # 계산적 사고
│   ├── book/                # sicp.org (전체 책, Babel 실행 가능)
│   └── info/                # Emacs info 버전
│
├── sicm/                    # 고전역학 (Sussman & Wisdom)
│   ├── book/                # 9개 챕터 (org-mode)
│   └── my-solutions/        # 개인 풀이
│
├── fdg/                     # 함수적 미분기하학
│   └── book/                # Scheme/Clojure 구현
│
├── sdf/                     # Software Design for Flexibility (신규)
│   ├── book/                # 전체 책 (org-mode, gitignore)
│   └── README.md            # 핵심 개념 요약
│
├── susskind/                # Theoretical Minimum 시리즈
│   ├── book/                # 고전역학 (org-mode, gitignore)
│   └── lecture-*-깊이탐구.org  # 깊이 탐구 노트
│
├── foundations/             # 수학적 기초
│   ├── calculus/
│   ├── linear-algebra/
│   ├── differential-geometry/
│   └── variational-principles/
│
├── tools/                   # 개발 환경
│   └── scheme/              # MIT Scheme 설정
│
├── README.md                # 영어 버전
├── README-KO.md             # 이 파일
├── VISION.md                # 철학적 배경
├── CREDITS.md               # 원저자 감사
└── AGENTS.md                # AI 에이전트 지침
```

**참고**: `book/` 폴더들은 원서의 org-mode 변환본을 포함합니다. 저작권 존중을 위해 gitignore 처리되어 있습니다. 초점은 재배포가 아닌 **학습 노트와 개인적 이해**에 있습니다.

## 학습 로드맵

### 트랙 A: 코드로서의 물리학 (SICM 경로)

**Phase 0: 기초**
- [ ] SICP Chapter 1-2: 프로시저, 데이터 추상화
- [ ] 서스킨드 Lecture 1-3: 고전물리학의 본질, 운동, 동역학

**Phase 1: 고전역학**
- [ ] SICM Chapter 1: 라그랑주 역학
- [ ] SICM Chapter 3: 해밀턴 역학
- [ ] 서스킨드 Lectures 4-11: 에너지, 최소 작용, 대칭성

**Phase 2: 기하학**
- [ ] FDG: 미분기하학 기초
- [ ] 일반상대성이론으로 가는 길

### 트랙 B: 유연한 설계 (SDF 경로)

**Phase 0: 설계 원칙**
- [ ] SDF Chapter 1: 프로그램의 유연성
- [ ] SDF Chapter 2: 도메인 특화 언어

**Phase 1: 핵심 기법**
- [ ] SDF Chapter 3: Scheme의 변형들
- [ ] SDF Chapter 4: 패턴 매칭
- [ ] SDF Chapter 5: 평가

**Phase 2: 고급 패턴**
- [ ] SDF Chapter 6: 레이어링
- [ ] SDF Chapter 7: 전파

### 수렴: 확장 가능한 시스템의 기술

두 트랙은 같은 통찰로 이어집니다: **잘 설계된 시스템은 진화할 수 있는 시스템**입니다. 물리학은 불변량을 찾는 법을 가르치고, SDF는 그것을 중심으로 구축하는 법을 가르칩니다.

## 도구

### Emmy (권장)
```clojure
;; Emmy로 라그랑주 방정식 풀기
(defn L-central-polar [m U]
  (fn [[_ [r] [rdot φdot]]]
    (- (* 1/2 m (+ (square rdot)
                   (square (* r φdot))))
       (U r))))

(((Lagrange-equations (L-central-polar 'm (literal-function 'U)))
  (up (literal-function 'r) (literal-function 'φ)))
 't)
```

- `tools/emmy/`: 전체 프로젝트 포함
- `bb repl`: REPL 시작
- `bb clerk-watch`: 인터랙티브 노트북

### Scheme (전통적)
- Docker 기반 scmutils

## 참고 자료

### 책
- [SICP](https://sarabander.github.io/sicp/) - 컴퓨터 프로그램의 구조와 해석
- [SICM](https://tgvaughan.github.io/sicm/) - 고전역학의 구조와 해석
- [SDF](https://mitpress.mit.edu/9780262045490/) - Software Design for Flexibility (MIT Press, 2021)
- [The Theoretical Minimum](https://theoreticalminimum.com/) - 서스킨드의 강의 시리즈

### 강의
- [MIT 6.946](https://groups.csail.mit.edu/mac/users/gjs/6946/) - Classical Mechanics: A Computational Approach
- [Stanford Continuing Studies](https://theoreticalminimum.com/courses) - 서스킨드의 물리학 강좌

### 커뮤니티
- [Road to Reality](https://roadtoreality.substack.com/) - Sam Ritchie 뉴스레터
- [mentat-collective](https://github.com/mentat-collective) - Emmy 및 관련 프로젝트

## 라이선스

- 원본 SICP/SICM/FDG/SDF 책: CC BY-NC-SA 3.0 또는 해당 라이선스
- Emmy: MIT License
- 개인 노트: MIT License
