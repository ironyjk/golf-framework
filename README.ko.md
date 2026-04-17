**한국어** | [English](README.md)

# 골프 프레임워크

8개의 근거 기반 프레임워크로 구성된 데이터 중심 골프 코칭 시스템. 스윙 교정 없음 — 머리로 하는 골프에 집중합니다. 전략, 멘탈, 숏게임, 장비 관련 질문을 자동으로 최적 프레임워크로 라우팅합니다. Broadie의 Strokes Gained, DECADE 코스 매니지먼트, Rotella의 멘탈 게임, Pelz의 숏게임 연구, TPI 체력 관리를 기반으로 하며, 한국 아마추어 골프 맥락(골프존 스크린골프, 한국 핸디캡 시스템)이 내장되어 있습니다.

> 전문 레슨의 대체재가 아닙니다. 스윙 코칭은 공인 지도자와 상담하세요.

## 설치

```bash
claude plugin install ironyjk/golf-framework
```

## 단축 커맨드 설정

설치 후 `/golf` 래퍼 커맨드를 추가하세요:

```markdown
# ~/.claude/commands/golf.md
---
description: "Golf coaching — 8 frameworks. Shortcut for /golf-framework:golf"
---
Invoke the skill `golf-framework:golf` with these arguments: $ARGUMENTS
```

자세한 내용은 [마켓플레이스 래퍼 가이드](https://github.com/ironyjk/claude-frameworks-marketplace)를 참조하세요.

## 프레임워크

| 커맨드 | 프레임워크 | 저자 / 방법론 |
|--------|------------|--------------|
| `/golf` | 메타 라우터 | 최적 서브 프레임워크 1~3개 자동 선택 |
| `strokes-gained` | Strokes Gained 분석 | Broadie SG 모델, SG Driving/Approach/ATG/Putting |
| `course-management` | 코스 매니지먼트 | DECADE 의사결정, 미스 방향 전략 |
| `mental-game` | 멘탈 게임 | Rotella, 프리샷 루틴, 압박 상황 관리 |
| `short-game` | 숏게임 | Pelz 연구, 칩핑, 피칭, 벙커샷 |
| `practice-design` | 연습 설계 | 의도적 연습, 블록/랜덤 연습, 기술 전이 |
| `club-fitting` | 클럽 피팅 | 정적/동적 피팅, 14개 클럽 최적화 |
| `physical-conditioning` | 체력 관리 | TPI(타이틀리스트 퍼포먼스) 무브먼트 스크리닝 |
| `scoring-strategy` | 스코어 전략 | 리스크-리워드, 파 관리, 라운드 플랜 |

## 사용 예시

```
/golf  핸디캡 15. 연습 시간을 어디에 집중해야 하나요?
/golf  18번홀만 가면 긴장해서 망쳐요. 압박 관리 방법은?
/golf  380야드 왼쪽 도그레그, 드라이버 vs 아이언 선택 기준은?
```

## 라이선스

[CC-BY-NC 4.0](LICENSE) — 개인/교육 목적 무료. 상업적 이용 문의: ironyjk@gmail.com

## 관련 프레임워크

- `/fit` ([health-framework](https://github.com/ironyjk/health-framework)) — 일반 체력 관리
- `/think` ([strategy-frameworks](https://github.com/ironyjk/strategy-frameworks)) — 의사결정 프레임워크
- [claude-frameworks-marketplace](https://github.com/ironyjk/claude-frameworks-marketplace) — 전체 프레임워크 목록
