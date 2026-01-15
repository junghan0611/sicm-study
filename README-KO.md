# SICM Study - 앎의 구도를 위한 여정

[![English](https://img.shields.io/badge/lang-English-blue)](README.md)

> "프로그래밍은 단순히 도구가 아니라 **이해의 검증 도구**이다."
> — Gerald Jay Sussman & Jack Wisdom, SICM 서문

> "비유를 통해 설명하기보다는 처음부터 수학적 내용을 하나씩 쌓아올리며 결론에 도달한다."
> — 로저 펜로즈, 《실체에 이르는 길》

이 리포지토리는 *계산적 사고*에서 *고전역학*, *미분기하학*, 나아가 *자연철학*으로
이어지는 **앎의 구도**를 위한 학습 공간입니다.

*sicm-study*라는 이름이지만, SICM은 출발점일 뿐입니다.
궁극적 목표와 철학적 배경은 [VISION-KO.md](VISION-KO.md)를 참고하세요.

## 지적 계보 (Intellectual Lineage)

```
  SICP (1985)                    계산적 사고의 기초
  Structure and Interpretation   Scheme 언어
  of Computer Programs           "프로그램 = 수학적 표현"
       │
       ▼
  SICM (2001)                    고전역학 + 함수형 표기법
  Structure and Interpretation   scmutils 라이브러리
  of Classical Mechanics         "수식 = 코드"
       │
       ▼
  FDG (2013)                     미분기하학
  Functional Differential        일반상대성이론으로 가는 길
  Geometry
       │
       ▼
  Emmy (2020~)                   Clojure 재구현
  Computer Algebra System        ClojureScript (브라우저!)
                                 Clerk 노트북 (시각화!)
                                 "Scheme의 한계 극복"
```

### 왜 이 계보인가?

Seymour Papert의 Logo에서 시작된 "구성주의 학습"이 Gerald Sussman을 통해
물리학의 핵심까지 이어집니다. 수학적 도구로서 *수식과 코드가 동일*하다는 것,
이것이 *보편학(Universal Science)*의 기반입니다.

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
├── sicp/                # 1단계: 계산적 사고
│   ├── book/            # sicp.org (전체 책, Babel 실행 가능)
│   └── info/            # Emacs info 버전
├── sicm/                # 2단계: 고전역학
│   ├── book/            # 9개 챕터 (org-mode)
│   ├── reference/       # Sam Ritchie의 Scheme 풀이
│   └── my-solutions/    # 내 풀이
├── fdg/                 # 3단계: 미분기하학
│   └── book/            # PDF + Scheme/Clojure 코드
├── foundations/         # 수리물리학 기초 (채워나갈 공간)
│   ├── calculus/
│   ├── linear-algebra/
│   ├── differential-geometry/
│   └── variational-principles/
├── tools/
│   ├── emmy/            # Emmy 전체 프로젝트 (4200+ 테스트)
│   └── scheme/          # MIT Scheme 설정
├── essays/              # Road to Reality (Sam Ritchie 에세이)
├── README-KO.md         # 이 파일
├── CREDITS-KO.md        # 원저자 감사
└── .claude/commands/    # 학습 도우미 에이전트
```

## 학습 로드맵

### Phase 0: SICP 기초 (선택)
- [ ] SICP Chapter 1-2: 프로시저, 데이터 추상화
- [ ] Scheme/Emacs 환경 설정
- [ ] Babel로 코드 실행 연습

### Phase 1: SICM 준비
- [ ] 변분법(Calculus of Variations) 기초
- [ ] 라그랑주 역학 개념 이해
- [ ] Emmy 설치 및 REPL 사용

### Phase 2: SICM 본격 학습
- [ ] Chapter 1: Lagrangian Mechanics
- [ ] Chapter 2: Rigid Bodies
- [ ] Chapter 3: Hamiltonian Mechanics
- [ ] Chapter 4-9: 심화

### Phase 3: FDG로 확장
- [ ] 미분기하학 기초
- [ ] 미분형식(Differential Forms)
- [ ] FDG 책 학습

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
- `sicm/reference/bin/mechanics`: Docker 기반 scmutils

## 참고 자료

### 책
- [SICM 2nd Edition](https://mitpress.mit.edu/sites/default/files/titles/content/sicm_edition_2/book.html) (MIT Press)
- [SICP HTML5 버전](https://sarabander.github.io/sicp/) (sarabander)
- [SICM HTML 버전](https://tgvaughan.github.io/sicm/) (tgvaughan)

### 강의
- [MIT 6.946](https://groups.csail.mit.edu/mac/users/gjs/6946/) - Classical Mechanics: A Computational Approach
- [MIT 6.001](https://ocw.mit.edu/courses/6-001-structure-and-interpretation-of-computer-programs-spring-2005/) - SICP 강의

### 커뮤니티
- [Road to Reality](https://roadtoreality.substack.com/) - Sam Ritchie 뉴스레터
- [mentat-collective](https://github.com/mentat-collective) - Emmy 및 관련 프로젝트

## 라이선스

- 원본 SICP/SICM/FDG 책: CC BY-NC-SA 3.0 또는 해당 라이선스
- Emmy: MIT License
- 개인 노트: MIT License
