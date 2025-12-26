# ML Workflow Plugin

AI/ML 및 백엔드 프로젝트를 위한 **분석-설계-구현-리뷰** 워크플로우 플러그인입니다.

## 개요

프로젝트 시작부터 완료까지 체계적인 개발 프로세스를 지원합니다:

```
┌─────────────────────────────────────────────────────────────┐
│                    ML Workflow Pipeline                      │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  /kickoff                                                   │
│      ↓                                                      │
│  @requirements-analyst → PRD (요구사항 명세서)               │
│      ↓                                                      │
│  @experiment-designer → 실험 설계서 (메트릭, A/B 테스트)     │
│      ↓                                                      │
│  @system-architect → 아키텍처 설계서                        │
│      ↓                                                      │
│  @implementer → 코드 구현                                   │
│      ↓                                                      │
│  @code-reviewer → 코드 리뷰                                 │
│      ↓                                                      │
│  🎉 완성!                                                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

## 설치

### 로컬 테스트
```bash
claude --plugin-dir ./ml-workflow-plugin
```

### 플러그인 설치
```bash
claude plugin install ml-workflow@your-marketplace
```

## 사용법

### 전체 워크플로우 시작
```bash
/ml-workflow:kickoff

프로젝트: 고객 리뷰 감성 분석 시스템
- 고객 리뷰 텍스트를 분석해서 긍정/부정/중립을 분류
- 실시간 API로 서비스
- 하루 10만 건 처리 예상
```

### 개별 Agent 사용

#### @requirements-analyst
모호한 요구사항을 구체적인 PRD로 변환합니다.
```bash
@requirements-analyst 추천 시스템 만들어줘
```

#### @experiment-designer
ML 실험 및 A/B 테스트를 설계합니다.
```bash
@experiment-designer PRD 기반으로 평가 체계 설계해줘
```

#### @system-architect
백엔드 + ML 시스템 아키텍처를 설계합니다.
```bash
@system-architect 시스템 아키텍처 설계해줘
```

#### @implementer
설계 문서 기반으로 코드를 구현합니다.
```bash
@implementer 설계서 기반으로 구현해줘
```

#### @code-reviewer
코드 품질을 검증합니다 (5대 원칙 기반).
```bash
@code-reviewer src/api/users.py 리뷰해줘
```

## 포함된 컴포넌트

### Agents (5개)

| Agent | 설명 |
|-------|------|
| `requirements-analyst` | 요구사항 분석 및 PRD 생성 |
| `experiment-designer` | ML 실험 및 A/B 테스트 설계 |
| `system-architect` | 시스템 아키텍처 설계 |
| `implementer` | 설계 기반 코드 구현 |
| `code-reviewer` | 코드 품질 리뷰 |

### Commands (1개)

| Command | 설명 |
|---------|------|
| `/kickoff` | 전체 워크플로우 시작 |

## 코드 리뷰 5대 원칙

이 플러그인의 모든 구현/리뷰는 다음 원칙을 따릅니다:

1. **Import는 최상단에** - 표준 → 서드파티 → 로컬 순서
2. **최소한의 변경** - 과하게 하지 않고 필요한 것만
3. **클린 코드** - 명확한 네이밍, 한 함수 = 한 가지 일
4. **타입 검증 철저히** - 모든 함수에 타입 힌트
5. **논리적으로 한번 더 생각** - 엣지 케이스 고려

## 지원하는 프로젝트 유형

- ✅ 전통 ML (분류, 회귀, 추천, 검색)
- ✅ LLM/GenAI (RAG, 챗봇, 생성)
- ✅ 백엔드 API
- ✅ 하이브리드

## 요구사항

- Claude Code 2.0.0+
- context7 MCP 서버 (선택사항, 라이브러리 문서 참조용)

## 라이선스

MIT
