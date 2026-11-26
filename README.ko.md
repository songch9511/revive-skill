<div align="center">

# Revive

[English](README.md) | **한국어** | [日本語](README.ja.md)

**만들다 멈춘 프로젝트를 다시 꺼내 첫 유료 고객까지 데려가요.**

AI로 만들어 출시하려다가 어느새 열어 보지 않게 된 프로젝트를 위한 에이전트 스킬이에요. Revive는 레포를 읽고, 왜 멈췄는지 함께 찾아내고, 출시할지 줄일지 접을지 분명하게 말해요. 계속하기로 하면 모르는 사람이 돈을 낼 때까지 같이 작업해요.

[이런 분께 맞아요](#이런-분께-맞아요) | [설치](#설치) | [바로 시작하기](#바로-시작하기) | [동작 방식](#동작-방식)

</div>

## 이런 분께 맞아요

- AI 코딩 에이전트로 뭔가를 만들었지만 출시하지 못했어요.
- 마음속으로는 출시했는데, 돈을 낸 사람은 아직 없어요.
- 끝까지 만들 가치가 있는지 모르겠고, 솔직한 답을 듣고 싶어요.

이런 프로젝트는 대개 코드가 망가져서 멈춘 게 아니에요. 고객을 찾지 못해서, 원하는 사람이 있을지 확신이 서지 않아서, 결제를 붙이다가, 끝없이 다듬다가 멈춰요. 그래서 Revive는 고치는 일부터 하지 않아요. 이 프로젝트에 시간을 더 쓸 가치가 있는지부터 판단해요.

새 아이디어를 처음부터 찾아 주는 도구는 아니에요. 첫 결제에서 끝나고, 그 뒤의 성장은 다루지 않아요.

## 설치

[skills CLI](https://github.com/vercel-labs/skills)로 설치해요.

```text
npx skills add songch9511/revive-skill
```

직접 넣으려면 이 레포를 클론한 뒤 `skills/revive` 폴더를 에이전트의 스킬 폴더로 복사하세요.

```text
Claude Code:  ~/.claude/skills/revive
```

스킬은 전부 Markdown 파일이에요. 아래가 갖춰져 있으면 더 잘 동작해요.

- **git 기록.** 되살리려는 프로젝트에 커밋 기록이 있어야 작업이 어디서 멈췄는지 찾을 수 있어요.
- **서브에이전트를 쓸 수 있는 에이전트.** 구현은 더 가벼운 모델의 서브에이전트에 맡기고, 판단은 메인 세션이 해요. 서브에이전트가 없으면 Revive가 직접 구현해요.
- **시크릿 스캐너.** 출시 전 점검 한 항목에 gitleaks 같은 도구를 써요. 무엇이든 설치하기 전에 먼저 물어봐요.

## 바로 시작하기

멈춘 프로젝트의 루트에서 에이전트를 열고 실행하세요.

```text
/revive
```

상황을 그냥 말해도 돼요.

```text
작년 봄에 만들고 출시를 못 했어. 끝까지 만들 가치가 있을까?
```

그다음에는 이렇게 진행돼요.

1. 질문하기 전에 레포부터 읽어요. 무엇이 있고 무엇이 깨졌는지 함께 볼 수 있게 아키텍처를 그림으로 그려요.
2. 질문을 하나씩 해요. 질문마다 Revive의 추측을 함께 말하고, 프로젝트가 멈춘 진짜 이유에 서로 동의할 때까지 이어 가요.
3. 판정과 권고를 내놓아요. 고르는 건 사용자예요.
4. 계속하기로 하면 결제 1건까지 가는 가장 짧은 경로를 짜고, 세션을 이어 가며 함께 진행해요.

언제든 다시 돌아와도 돼요. Revive는 프로젝트의 `.revive/` 폴더에 기록을 남기고, 지난번에 멈춘 곳에서 이어서 시작해요.

## 동작 방식

```text
0 정찰 → 1 인터뷰 → 2 판정 → 3 첫 결제 경로 → 4 실행 ⇄ 5 체크인 → 종료
```

0. **정찰.** 사실부터 모아요. 마지막 커밋, 커밋이 끊긴 시점, 만들다 만 기능, 빌드가 되는지를 확인해요. 그다음 코드 전체를 도식으로 그리고 부분마다 동작함, 미완성, 깨짐, 안 쓰임을 표시해요.
1. **인터뷰.** 레포에서 확인한 사실을 근거로 한 번에 하나씩 물어요. 사용자가 든 이유마다 이렇게 확인해요. *"그 문제가 오늘 해결된다면 내일 출시하시겠어요?"* 아니라고 답하면 그건 원인이 아니라 핑계예요.
2. **판정.** 얼버무리지 않아요. 사실, 이유, 건질 것을 정리하고 권고를 하나 내요. 그대로 출시, 축소 또는 피봇, 접기 중 하나예요. 접어야 한다면 그렇게 말하고 이유를 밝혀요. 최종 선택은 사용자가 해요.
3. **첫 결제 경로.** 무엇을 누구에게 얼마에 팔지, 무엇을 뺄지 정해요. 더 만들기 전에 수요부터 확인해요. 기능을 한 달 더 만드는 것보다 실제 사람에게 결제 링크를 보여 주는 쪽이 낫기 때문이에요.
4. **실행.** 작업을 하나씩 처리해요. 구현은 서브에이전트에 넘기고, 결과는 Revive가 직접 빌드하고 실행하고 테스트 결제를 해 보며 확인해요. 출시 전에는 정해진 보안 점검을 통과해야 해요.
5. **체크인.** 세션을 시작할 때마다 지금 어디까지 왔는지부터 확인해요. 일주일 동안 진전이 없으면 멈추고 이유를 다시 물어요. 또 멈췄다면 첫 진단이 뭔가를 놓쳤다는 뜻이기 때문이에요.

끝은 둘 중 하나예요. 모르는 사람에게서 첫 결제를 받거나, 접기로 분명히 결정하고 배운 것을 기록으로 남기거나. 둘 다 끝낸 것으로 쳐요.

## 프로젝트에 남는 것

Revive가 아는 것은 모두 `.revive/` 폴더에 Markdown으로 남아요. 직접 읽고 고칠 수 있어요.

```text
.revive/state.md          현재 단계, 확인된 사실, 원인, 마일스톤, 고객이 한 말
.revive/architecture.md   코드 도식과 깨진 곳
.revive/verdict.md        판정과 사용자의 선택
.revive/log.md            세션마다 한 줄 기록
.revive/checks.md         출시 전 점검 결과
.revive/retro.md          끝날 때 한 번 쓰는 회고
```

## 알아두면 좋은 점

- **일부러 직설적이에요.** 격려가 필요하다면 맞는 도구가 아니에요.
- **범위를 작게 유지해요.** 첫 결제에 필요 없는 일은 적어만 두고 손대지 않아요.
- **바깥과 닿는 일은 사용자가 해요.** 결제 계정 개설, 본인 확인, 도메인 구매, 공개 게시, 플러그인 설치는 사용자가 직접 하거나 승인해요.
- **결제는 글로벌(미국) 판매자를 기준으로 해요.** 기본은 Stripe이고, 대안은 Polar 같은 판매 대행(Merchant of Record) 서비스예요. 국내 PG 심사나 사업자등록 같은 나라별 절차는 다루지 않아요.
- **고객에게 보이는 글은 영어로 써요.** 사용자와의 대화는 사용자의 언어로 해요.
- **법률이나 세무 자문은 하지 않아요.**

## 구성

```text
skills/revive/SKILL.md                         기본 원칙, 역할, 단계
skills/revive/references/recon.md              레포 점검, 아키텍처 도식
skills/revive/references/interview.md          진단 인터뷰
skills/revive/references/verdict.md            판정 형식과 문체
skills/revive/references/payment-path.md       계획, 수요 확인, 결제 규칙
skills/revive/references/execution.md          스킬 라우팅, 작업 지시, 디버깅
skills/revive/references/prelaunch-checks.md   출시 전 보안 점검
skills/revive/references/state-files.md        .revive/ 파일 템플릿
```

스킬 파일은 영어로 쓰여 있어요.

## 함께 쓰면 좋은 스킬

Revive는 혼자서도 동작해요. 아래 스킬이 설치되어 있으면 해당 작업에 그 스킬을 써요. 설치를 제안할 수는 있지만 묻지 않고 설치하지는 않아요.

- UI 작업: [frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design)
- 랜딩 페이지와 출시 글: [marketingskills](https://github.com/coreyhaines31/marketingskills)의 `copywriting`, `pricing`, `offers`, `prospecting`, `launch`
- 결제 연동: [Stripe](https://github.com/stripe/ai)와 [Polar](https://github.com/polarsource/agent-toolkit)의 공식 스킬
- 배포: [deploy-to-vercel](https://github.com/vercel-labs/agent-skills)

## 크레딧

진단 인터뷰는 Addy Osmani의 `interview-me` 스킬([addyosmani/agent-skills](https://github.com/addyosmani/agent-skills), MIT License)을 바탕으로 고쳐 썼어요. 고지 전문은 [THIRD_PARTY_NOTICES.md](skills/revive/THIRD_PARTY_NOTICES.md)에 있어요.

## 라이선스

MIT예요. [LICENSE](LICENSE)를 참고하세요. 가져온 저작물에는 원래의 라이선스가 그대로 적용돼요.
