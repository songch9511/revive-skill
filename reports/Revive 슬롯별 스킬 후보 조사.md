# Revive는 적게 묶고 관문을 직접 써야 한다

> **범위 변경 (2026-11-22, 보고서 작성 뒤):** Revive의 기준 시장을 글로벌(영어권, 미국 기준)로 정했다. 결제, 랜딩·카피, 출시 채널이 모두 해당한다. 이 보고서의 한국 전용 내용은 Revive 범위 밖이다: 한국 PG, 사업자등록, 한국 개인의 Polar·Stripe 가입과 정산, 한국어 카피와 휴머나이저, 한국 출시 채널, 한국산 SEO/GEO 스킬. 결제 슬롯의 기본 경로는 스펙(`docs/specs/revive-skill.md`) §6의 결제 연동 규칙을 따른다. 영어권 출시 채널은 이 보고서에서 조사하지 않았다.

2026년 11월 22일 기준으로 여섯 슬롯 모두에 후보는 있지만, Reddit 41개 스레드와 Threads 글 14건을 직접 읽고 나니 함께 배포할 만한 제3자 스킬은 1차 보고서 때보다 줄었다. 디자인은 Anthropic `frontend-design`을 기본으로 싣고 `pbakaus/impeccable`은 `critique` 명령 중심의 선택 설치로 둔다. 결제의 MoR 경로에는 Polar 공식 `setup-polar`, 배포에는 Vercel `deploy-to-vercel`(라이선스 확인 전까지 런타임 설치), 랜딩·카피에는 `coreyhaines31/marketingskills`에서 고른 4~5개를 권한다. 디버깅과 출시 전 점검은 추천이 바뀌었다. Reddit의 직접 비교 테스트에서 `systematic-debugging`과 `diagnosing-bugs`는 맨 프롬프트보다 나은 점이 없었고, Cloudflare `security-audit`은 구독 요금제에서 감당이 안 된다는 보고가 나왔으며, 사람들이 실제로 돌리는 것은 스킬이 아니라 30분짜리 수동 체크리스트였다. 이 두 슬롯은 Revive가 얇은 절차와 결정적 점검 스크립트를 직접 쓰는 편이 맞다. 두 플랫폼의 1인칭 기록에서 사람들이 멈추는 곳은 깨진 코드가 아니라 발견, 수요 검증, 결제 승인과 정산, 한국의 사업자·PG 서류였다. 그래서 Revive의 값은 번들 목록보다 저장된 프로젝트 상태, 단계 관문, 판정에서 나온다. 가장 중요한 미해결 질문은 그대로다. 사업자등록이 없는 한국 개인이 Polar에서 승인받고 실제로 정산까지 받았다는 1인칭 기록을 어디에서도 찾지 못했다. X와 YouTube는 여전히 검색 스니펫 수준이고, 이번에 새로 나온 후보 대부분은 저장소 사실을 확인하지 않아 NOT VERIFIED로 남아 있다.

## 2차 보충에서 달라진 점

1차 보고서는 Reddit과 Threads를 한 건도 직접 읽지 못한 상태에서 썼다. 이번에는 사용자 본인의 브라우저로 두 곳을 직접 읽은 노트 두 개가 추가됐고, 그 결과 아래 항목이 바뀌었다.

| 항목 | 1차 | 2차 | 바뀐 이유 |
|---|---|---|---|
| 소셜 근거 | Reddit·Threads 직접 읽은 글 0건 | Reddit 스레드 41개, Threads 글 14건 직접 읽음. X·YouTube는 그대로 스니펫뿐 | 사용자 브라우저로 직접 열람 |
| 디버깅 슬롯 | superpowers `systematic-debugging` 복사본 | Revive 자체의 얇은 절차. 제3자 스킬을 꼭 하나 싣는다면 `diagnosing-bugs` | Reddit의 직접 비교 테스트에서 두 스킬 모두 효과 없음. Superpowers 전반에 대한 최근 여론이 부정적 |
| 출시 전 점검 | `vibe-security` + `verification-before-completion` + 내장 `/security-review` | 자체 결정적 점검 스크립트 + 새 컨텍스트의 독립 리뷰어 + `/security-review` 영역별 실행. `vibe-security`는 참고 체크리스트로 강등, Cloudflare `security-audit`은 기본 대안에서 제외 | 1인칭 보고: Cloudflare는 비용 감당 불가, `/vibe-security`는 찾는 것이 적음, 세션 내 리뷰 스킬은 본 자리의 버그도 놓침 |
| 결제 슬롯 | Polar 스킬을 기본값으로 | 자체 라우터가 자격·정산 요건을 먼저 확인하고, MoR 경로에서만 Polar 스킬 사용. 대안 순서는 Paddle·Stripe 먼저, Creem·Dodo는 보류 | MoR 승인 거절, 정산 보류, 자금 몰수 사례. 한국 PG 심사 지연과 계좌이체 우선 조언 |
| 디자인 슬롯 | Impeccable 1순위, `frontend-design` 폴백 | `frontend-design`을 기본 동봉, Impeccable은 `critique` 중심 선택 설치. 브리프·레퍼런스 수집 단계를 자체 작성 | Reddit이 Impeccable 인기를 확인했지만 비용이 1.6~5배이고 설치 흔적이 크다는 보고(단일 출처) |
| 배포 슬롯 | `deploy-to-vercel`, 대안 Railway·Cloudflare·Netlify | 1순위는 유지. 대안 순서는 Cloudflare를 앞으로, Railway는 자동 승인 훅을 뺀 스킬 폴더만 | 비기술 빌더가 가장 많이 꼽는 무료 호스트가 Cloudflare. Railway 훅이 Vercel 텔레메트리보다 큰 위험이라는 지적 |
| 랜딩·카피·론칭 | marketingskills 8개 안팎 + humanizer 복사본 | 4~5개로 축소. humanizer는 선택 사항. 첫 고객의 말을 카피로 쓰는 단계와 문체 프로필을 자체 작성 | 사람들은 팩에서 낱개만 뽑아 쓰고, 범용 휴머나이저보다 개인 문체 프로필이 낫다는 합의 |
| Revive가 직접 쓸 것 | 복구 절차, 결제 라우터, 한국 론칭 등 | 여기에 수요 검증·이름 충돌 점검, 상태 파일과 관문, PG 심사 준비 점검이 더해짐 | 멈추는 지점이 코드가 아니라는 1인칭 기록 |
| 번들 크기 | 마크다운 폴더 십여 개 | 열 개 미만. 스킬마다 검증 시점과 고정 SHA를 적고 모델이 바뀔 때마다 재검증 | 제3자 스킬은 일시적이라는 Reddit의 일관된 메시지 |
| 신규 후보 | 없음 | `heydamir/unslop`, `nutlope/hallmark`, Ponytail, Freemius, 한국산 SEO/GEO 스킬, `michael-ilic/solo-venturing` 등 | 두 노트에서만 등장. 저장소 사실은 이번 라운드에 확인하지 않아 NOT VERIFIED |

## Reddit 41개 스레드와 Threads 14개 글은 직접 읽었고 X·YouTube는 여전히 스니펫뿐이다

독자가 요청한 네 플랫폼 가운데 둘은 이제 직접 읽은 근거가 있다. Reddit은 로그아웃 상태의 브라우저로 검색 35회를 돌려 스레드 41개를 열었다. Threads는 로그인된 브라우저로 검색 26회를 돌려 글 14건을 열었고 대부분 한국어다. 두 곳 모두 읽기만 했다. 그래도 한계는 남는다.

| 플랫폼 | 접근 결과 | 남은 한계 |
|---|---|---|
| Reddit | 스레드 41개의 본문과 기본 노출 댓글을 직접 읽음 | 접힌 댓글과 "댓글 더 보기"는 펼치지 않아 큰 스레드는 표본이다. 댓글별 추천 수는 보이지 않았다. 한국 관련 검색 세 번은 쓸 만한 결과가 없었다. "테스트해 봤다" 류 글 넷은 같은 사람이 자기 블로그로 연결하는 글이다 |
| Threads | 글 14건을 직접 읽음. 나머지는 검색 목록의 제목과 수치만 봄 | 검색이 얕고 부정확해 질의당 5~10건만 나오고, 브랜드명을 섞으면 무관한 글이 나온다. 영어권 Threads와 배포 슬롯은 거의 다루지 못했다. 여러 부로 나뉜 글 일부는 뒷부분이 표시되지 않았다. 큐레이션·홍보 계정 비중이 높다 |
| X | 본문 열람 불가(HTTP 402) | 검색 스니펫만. 대부분 리스티클과 저자 홍보 |
| YouTube | 영상 0편 열람 | 제3자 요약 페이지 1건과 영상 제목 스니펫 |
| Hacker News | Algolia API로 댓글 원문을 직접 읽음 | 1차와 같음 |
| GitHub 이슈 | API로 직접 읽음(일부는 제목만) | 1차와 같음 |
| 한국어 커뮤니티·블로그 | 다모앙, wikidocs, gpters, 개인 블로그 일부를 직접 읽음 | 강의를 파는 큐레이터 비중이 높음 |

이 보고서는 근거마다 접근 수준을 붙인다. "Reddit 직접 읽음"과 "Threads 직접 읽음"은 글 본문과 기본 노출 댓글을 연 경우다. "목록만"은 검색 결과에서 제목, 날짜, 추천 수만 본 경우라 글 내용의 근거로 쓰지 않는다. "직접 읽음"은 그 밖의 페이지나 API 원문을 연 경우, "요약 경유"는 가져오기 도구의 소형 모델이 만든 요약만 본 경우, "스니펫만"은 검색 엔진 요약만 본 경우, "2차 인용"은 제3자가 전한 말이다. 저장소 사실은 1차 조사 때 2026-11-22에 GitHub에서 읽은 것만 확인된 것으로 치고, 이번 노트에서 처음 나온 저장소는 NOT VERIFIED로 적는다. Reddit과 Threads의 내용은 모두 익명 사용자의 경험담이고, 여러 "벤치마크"는 한 사람이 한두 번 돌린 결과다.

직접 읽은 결과는 1차의 간접 근거를 일부 확인하고 일부 뒤집었다. 확인된 것은 Impeccable이 현재 디자인 스킬 가운데 이름으로 가장 많이 추천된다는 점, `frontend-design`이 싸고 안전한 기본값이라는 점, Lemon Squeezy가 문을 닫고 판매자들이 Polar로 가장 많이 옮긴다는 점, marketingskills에서 사람들이 낱개 스킬만 뽑아 쓴다는 점이다. 뒤집힌 것은 디버깅 스킬과 보안 감사 스킬의 효용, 그리고 MoR 서비스를 저위험 기본값으로 보던 전제다. 1차에서 2차 인용으로만 다뤘던 Subframe의 Reddit 집계는 방향이 맞는 것으로 보이지만 수치 자체는 여전히 검증할 수 없다.

## 슬롯별 재평가: 둘은 추천이 바뀌고 넷은 범위가 좁아졌다

| 슬롯 | 권장 구성 | 함께 배포할 후보 | 선택 설치·호출·보류 |
|---|---|---|---|
| 디자인/UI·UX | 브리프와 레퍼런스 수집(자체) → `frontend-design` → Impeccable `critique`로 점검 | `frontend-design` 복사본 | Impeccable(선택 설치). `heydamir/unslop`·`nutlope/hallmark`는 NOT VERIFIED |
| 막힘 해소/디버깅 | Revive 자체의 얇은 절차 | 싣는다면 mattpocock `diagnosing-bugs` | `systematic-debugging`은 대안으로 강등. Ponytail은 NOT VERIFIED |
| 결제 연동 | 자체 라우터가 자격·정산 요건 확인 → MoR 경로는 Polar 스킬 | Polar `setup-polar` + `polar-integration` | Paddle, Stripe. Freemius는 스킬 미확인. Creem·Dodo 보류 |
| 배포 | `deploy-to-vercel`. 저장소당 플랫폼 하나만 | 라이선스 확인 전에는 없음. 복사가 필요하면 `cloudflare/skills` | Railway(훅 제외), Netlify |
| 랜딩·카피·론칭 | marketingskills 4~5개 + 고객의 말 수집과 문체 프로필(자체) | `copywriting`, `pricing`, `offers`, `prospecting`, `launch` | humanizer 계열, 한국산 SEO/GEO 스킬(NOT VERIFIED) |
| 출시 전 점검 | 자체 결정적 점검 스크립트 + 독립 리뷰어 + 내장 `/security-review` 영역별 실행 | `vibe-security`는 참고 체크리스트로만 | Anthropic `security-guidance`(선택 설치). Cloudflare `security-audit`은 비권장 |

조사팀은 어떤 스킬도 직접 실행해 비교하지 않았다. 품질 판단은 SKILL.md를 읽은 결과와 제3자의 단발 테스트, 그리고 사용자 경험담에 기대고 있다.

### 디자인: 기본은 frontend-design, Impeccable은 critique를 위해 선택 설치한다

| 후보 | 라이선스 | 유지 상태 | 무게·의존성·훅 | 사용자 근거(접근 수준) | 번들 판단 |
|---|---|---|---|---|---|
| [frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design) (Anthropic) | Apache-2.0 (스킬 폴더의 LICENSE.txt) | 스킬 경로 커밋 2026-09-03, 플러그인 v1.1.1은 2026-10-26 | 9.4KB SKILL.md 한 장. 의존성·훅·네트워크 없음 | Reddit 직접 읽음: 랜딩 스레드의 최상위 답이 좋은 출발점으로 꼽음. 단발 대시보드 테스트에서 가장 싸고 가장 뚜렷한 결과(자기 블로그 홍보 글). HN은 호평과 "티가 난다"는 비판이 섞임 | 복사해 기본으로 동봉 |
| [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | Apache-2.0, NOTICE.md 있음 | v4.10.0, main 커밋 2026-11-18, 별 114,603 | `plugin/` 약 2.3MB. 네이티브 엔진 바이너리 다운로드. 훅 3개. impeccable.style로 요청 발생 | Reddit 직접 읽음: 추천 스레드에서 첫 답이자 가장 많이 반복된 답. 반론도 있음(여전히 평범하다, 토큰을 많이 쓴다). HN 댓글과 블로그 테스트 4곳 | 복사하지 않음. 선택 설치, `critique` 중심 |
| [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) 2.5.1 | MIT. 동봉 사진·로고는 별도 라이선스 | main 커밋 2026-11-07, 별 119,795 | 약 36.6MB. Node 22+와 Chrome 필요. Stop 훅 | Reddit 직접 읽음: 단발 테스트에서 스킬 없는 쪽보다 한 단계 나았지만 두 번 돌리면 결과가 달랐고 보조 스크립트가 권한 검사에 막힘(같은 블로거) | 복사 부적합. 랜딩 단계의 선택 설치 정도 |
| [ui-ux-pro-max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) | MIT (`ui-styling`은 Apache-2.0) | v2.15.0, 2026-11-22, 별 152,563 | 약 10MB. Python 3 필요 | Reddit에서 2026년의 실질 토론 스레드를 찾지 못함. Threads에서는 별 순위 목록에만 등장(목록만) | 추천 근거가 약함 |
| [emilkowalski/skills](https://github.com/emilkowalski/skills) | MIT (1차 확인) | 별 58,690(1차 확인), 최근 커밋 NOT VERIFIED | 모션·인터랙션 원칙 | Threads 소개 글 직접 읽음(큐레이션 계정, 사용 후기 댓글 없음). Reddit 댓글 추천(순위 사이트 운영자) | 주 스킬이 아니라 덧붙이는 용도 |
| `heydamir/unslop` | NOT VERIFIED | NOT VERIFIED | 이미 만든 화면의 AI 티를 평가·수정한다고 소개됨 | Threads 소개 글 직접 읽음(조회 약 5만, 작성자가 아닌 큐레이션 계정) | 저장소 확인 전에는 판단 보류 |
| `nutlope/hallmark` | 게시자는 MIT라고 적음. NOT VERIFIED | NOT VERIFIED | 대기 컨텍스트 비용이 약 90토큰이라는 보고 | Reddit 단발 테스트 직접 읽음(자기 블로그 홍보 글, 추천 7·댓글 0) | 저장소 확인 전에는 판단 보류 |
| `vercel-labs/agent-skills` `web-design-guidelines` | LICENSE 파일 없음(1차 확인) | 저장소 2026-11-20 | 기존 디자인 감사용 지침 | Reddit 댓글 1건이 감사 단계로 추천 | 복사 보류 |

Reddit을 직접 읽으니 Impeccable의 인기는 사실이었다. 백엔드 개발자가 AI 템플릿 같은 화면을 피할 스킬을 묻는 스레드(추천 49·댓글 32)에서 첫 답이자 가장 많이 되풀이된 답이 Impeccable이었다. 문서를 읽고 제대로 써야 힘을 쓴다는 단서와, 어떤 시각 방향을 원하는지 어느 정도는 알고 있어야 한다는 단서가 붙었다 ([r/claudeskills](https://www.reddit.com/r/claudeskills/comments/1xwwree/best_skill_for_uiux_designing/)). 같은 스레드에는 Impeccable 결과물도 여전히 평범하다는 반론이 있고, 주간 인기 스킬 글에는 토큰을 너무 많이 쓴다는 댓글이 달렸다 ([r/claudeskills 주간](https://www.reddit.com/r/claudeskills/comments/1y0ikqe/my_favorite_claude_skills_this_week_drop_yours_in/)). Hacker News의 실사용 댓글과 블로그 비교 테스트 네 곳도 기존 화면 개선에 Impeccable을 꼽는다는 1차의 근거는 그대로다 ([HN 49294522](https://news.ycombinator.com/item?id=49294522), [Subframe](https://www.subframe.com/tips/best-claude-code-skills-for-ui-design)).

비용과 설치 흔적은 1차 때보다 무겁게 봐야 한다. 한 사용자가 같은 대시보드 브리프를 세 번 만든 단발 테스트에서 `frontend-design`은 3분 2초에 출력 약 2만 토큰, Impeccable은 5분 1초에 약 3만 3천 토큰이었고 세 결과 모두 같은 점검을 통과했다. 이 테스트에서 Impeccable의 런처와 훅은 돌지 않았다 ([r/ClaudeCode](https://www.reddit.com/r/ClaudeCode/comments/1xp9mtq/same_dashboard_brief_built_3_times_no_skill/)). 같은 사람의 다른 글은 Impeccable과 Hallmark가 모두 맨 빌드의 다섯 배쯤 든다고 적고, 가장 쓸모 있던 것은 실제 폼 버그를 찾아낸 `/impeccable critique`였으며 `polish`는 거의 바꾸지 못했다고 평했다. 이 글은 Impeccable이 스킬 폴더 외에 에이전트 4개, 훅 3개, 프로젝트 설치인데도 홈 디렉터리의 `~/.impeccable` 폴더, 기본으로 켜진 텔레메트리를 설치한다고 보고한다 ([r/claudeskills](https://www.reddit.com/r/claudeskills/comments/1xjghnu/tested_hallmark_and_impeccable_in_claude_code/)). 이 글들은 모두 자기 블로그로 연결하는 한 사람의 단발 측정이라 수치는 참고용이다. 설치 흔적 보고는 단일 출처이므로 번들 전에 저장소와 대조해야 한다. 1차 저장소 확인과 맞춰 보면 훅 3개와 `~/.impeccable/bin`으로의 엔진 다운로드는 일치하고, 에이전트 수는 1차에서 5개로 읽었으며, 텔레메트리의 기본값은 따로 확인하지 않았다 ([README](https://github.com/pbakaus/impeccable/blob/main/README.md), [hooks.json](https://raw.githubusercontent.com/pbakaus/impeccable/main/plugin/hooks/hooks.json)). 엔진 다운로드 호스트와 바이너리 크기, Apache-2.0 외의 상표 조건도 NOT VERIFIED다.

두 플랫폼에서 반복된 조언은 스킬 선택보다 브리프와 레퍼런스가 중요하다는 것이다. Reddit의 랜딩 스레드에서는 실제 레퍼런스, 대상 독자, 페이지가 이끌 행동 하나, 모바일 폭 확인이 스킬보다 큰 몫을 한다는 답이 최상위였다 ([r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/comments/1xhhjjf/best_current_skills_for_landing_page_development/)). 한국어 Threads에서 반응이 컸던 디자인 글 둘도 새로 생성하는 스킬이 아니라 이미 만든 화면을 고치거나 실제 앱을 레퍼런스로 먹이는 내용이었다 ([Threads @sandpia_com](https://www.threads.com/@sandpia_com/post/DfnrHoZExAf), [Threads @aicoffeechat](https://www.threads.com/@aicoffeechat/post/DfTHWKUitbh)). 그래서 이 슬롯의 첫 단계는 Revive가 직접 쓰는 브리프·레퍼런스 수집이고, 그다음이 `frontend-design`, 마지막이 설치돼 있을 때의 Impeccable `critique`다. gstack의 `/design-review`가 이미 Impeccable을 감지해 쓰는 방식을 보여 준다 ([gstack README](https://github.com/garrytan/gstack)). `unslop`은 버려 둔 프로젝트의 기존 화면을 고친다는 점에서 Revive와 잘 맞아 보이지만 저장소를 열어 보지 않았다. taste-skill은 1차 판단 그대로다. 2.5.x는 마케팅 사이트 전용으로 재작성됐고 사진과 로고를 동봉해 재배포 부담이 크다 ([CHANGELOG](https://github.com/Leonxlnx/taste-skill/blob/main/CHANGELOG.md), [photos.json](https://raw.githubusercontent.com/Leonxlnx/taste-skill/main/skills/taste-skill/assets/photos/photos.json)).

### 막힘 해소·디버깅: 직접 비교에서 두 선두 스킬은 맨 프롬프트를 이기지 못했다

| 후보 | 라이선스 | 유지 상태 | 형태·의존성 | 사용자 근거(접근 수준) | 번들 판단 |
|---|---|---|---|---|---|
| Revive 자체의 얇은 절차 | 해당 없음 | 직접 유지 | 재현 → 원인 확인 → 가장 작은 수정 → 독립 검증 | Reddit 직접 읽음: 남는 스킬은 직접 쓴 좁은 절차라는 반복된 조언 | 직접 작성(권장) |
| [mattpocock/skills](https://github.com/mattpocock/skills/tree/main/skills/engineering/diagnosing-bugs) `diagnosing-bugs` | MIT | 2026-11-19, 별 329,858 | 1,427단어 + 스크립트 템플릿. 자체 완결 | Reddit 직접 비교: 맨 프롬프트와 해결 수 동일. 다른 테스트를 깨뜨린 적이 없고 수정 폭이 가장 작음. 다모앙 리뷰어의 네 개에 포함 | 싣는다면 이것 |
| [obra/superpowers](https://github.com/obra/superpowers) `systematic-debugging` | MIT | v7.0.2, 2026-11-03, 별 323,828 | 약 40KB. 형제 스킬 참조 2곳 | Reddit 직접 비교: 효과 없음, 버그당 약 3분 추가. HN 자발적 추천 1건(직접 읽음). Threads에서는 Superpowers가 계획 도구로만 알려짐(목록만) | 1순위에서 대안으로 강등 |
| [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills/tree/main/skills/debugging-and-error-recovery) `debugging-and-error-recovery` | MIT | 0.6.17, 2026-11-18, 별 119,615 | SKILL.md 한 장 | Reddit에서 이 팩을 실제로 쓴다는 댓글을 찾지 못함 | 복사는 쉽지만 근거 없음 |
| Ponytail (`DietrichGebert/ponytail`) | NOT VERIFIED | NOT VERIFIED | 코드를 덜 쓰게 하는 지침으로 소개됨 | Reddit 직접 읽음: 읽은 스레드 중 최소 6곳에서 언급. 한국 wikidocs 가이드북도 상위로 꼽음 | 저장소 확인 전에는 판단 보류 |
| mattpocock `grill-me`, `handoff`, `improve-codebase-architecture` | MIT | 위와 같음 | 인터뷰·인계·구조 정리 | Reddit 직접 읽음: 디버깅 스킬보다 훨씬 자주 칭찬받음 | 디버깅용은 아니지만 보조 후보 |
| [trailofbits/skills](https://github.com/trailofbits/skills) `supply-chain-risk-auditor` | CC BY-SA 4.0 | 2026-11-12, 별 8,341 | 플러그인 단위 | 이 용도의 사용자 근거 없음 | 참조만 권장 |

1차 보고서는 `systematic-debugging`을 1순위로 꼽았다. 그 근거는 Hacker News 사용자 한 명의 자발적 추천과 블로그 리뷰였다 ([HN 47134241](https://news.ycombinator.com/item?id=47134241)). Reddit에는 바로 그 두 선두 스킬을 맨 프롬프트와 견준 글이 있다. 글쓴이는 자기 저장소의 실제 버그 15개를 세 번씩 돌리고 실제 수정에서 가져온 숨은 테스트로 채점했다. 세 방식 모두 15개 중 9개를 고쳤고, 스킬을 쓴 쪽은 같은 결과에 이르는 데 버그당 3분쯤 더 걸렸다. 차이라면 `diagnosing-bugs`만 다른 테스트를 깨뜨린 적이 없고 수정 줄 수가 가장 적었다는 점이다. 글쓴이는 팩이 마음에 들면 두되 디버깅 부분은 지워도 된다고 권했고 댓글은 대체로 동의했다 ([r/claudeskills](https://www.reddit.com/r/claudeskills/comments/1wv6eoq/matt_pocock_and_superpowers_are_overratedfor/)). 이 글쓴이는 자기 평가 프레임워크를 홍보하고 있고 저장소도 본인 것이라, 결과를 일반화하기는 어렵다.

그래도 방향은 다른 스레드들과 같다. Superpowers에 대한 의견을 묻는 나흘 전 스레드(추천 39·댓글 64)의 주된 반응은 아홉 달 전에는 좋았지만 지금은 대부분 불필요하다는 것이었다. `brainstorming`과 `writing-plans`만 여전히 쓸 만하다는 말이 여러 번 나왔다 ([r/ClaudeCode](https://www.reddit.com/r/ClaudeCode/comments/1xz7w0k/what_is_your_opinion_on_the_superpowers_skill/)). 추천 255개를 받은 다른 글은 Superpowers의 TDD 규칙 때문에 테스트가 2주 만에 1,400개에서 4,000개 가까이로 불었고 그 70% 이상이 동작이 아니라 구현을 검사했다고 보고한다. 본인이 써 둔 지침이 긴 무인 실행에서 스킬 규칙에 밀렸다는 점이 번들 설계에 특히 중요하다 ([r/ClaudeCode](https://www.reddit.com/r/ClaudeCode/comments/1xwmeln/psa_superpowers_skill_with_opus_ruined_my_codebase/)). 1차에서 읽은 Hacker News의 토큰·속도 불만과 저장소 이슈도 같은 쪽을 가리킨다 ([HN 48016488](https://news.ycombinator.com/item?id=48016488), [#743](https://github.com/obra/superpowers/issues/743)). 반대 의견도 있다. 문제를 겪은 적이 없다는 사용자와 절차의 일관성 때문에 계속 쓴다는 소수가 있다.

그래서 이 슬롯의 추천을 바꾼다. Reddit에는 합의된 디버깅 스킬이 아예 없고, 남는 것은 스스로 쓴 좁은 절차라는 조언이 반복된다. Revive가 재현, 원인 확인, 가장 작은 수정, 독립 검증으로 이어지는 얇은 절차를 직접 쓰는 편이 맞다. 오너의 결정대로 제3자 스킬을 하나 싣는다면 부작용이 가장 적었던 `diagnosing-bugs`가 `systematic-debugging`보다 변호하기 쉽다. 어느 쪽이든 오케스트레이터가 이름으로 호출해야 한다. 지피터스의 비개발자 리뷰어는 자기 세션에서 디버깅 스킬이 한 번도 발동하지 않았다고 기록했다(요약 경유) ([gpters.org](https://www.gpters.org/news/post/superpowers-review-nondev-iGXKkr9Pr37dXue)). 몇 달 방치된 뒤 깨진 빌드, 낡은 의존성, AI가 쌓아 둔 엉킨 코드를 절차로 다루는 스킬은 이번에도 찾지 못했다. 방치된 코드베이스를 되살려 첫 유료 고객까지 데려가는 스킬이나 플러그인도 Reddit에서 나오지 않았다. Anthropic 공식 마켓플레이스의 `code-modernization`과 `code-simplifier`는 내용이 NOT VERIFIED다.

### 결제: 막히는 곳은 연동이 아니라 승인과 정산이다

| 제공자·저장소 | 라이선스·유지 상태 | 형태 | 한국 개인 사용 가능성 | 사용자 경험(접근 수준) | 판단 |
|---|---|---|---|---|---|
| Polar [polarsource/agent-toolkit](https://github.com/polarsource/agent-toolkit) (공식) | MIT. 0.2.3, 2026-11-17, 별 8 | 스킬 4개 + 원격 MCP | 한국이 정산 국가 목록에 있음. 개인 유형 허용은 NOT VERIFIED. 승인 경험담은 블로그 1건, 정산 완료 기록은 0건 | Reddit 직접 읽음: Lemon Squeezy 이탈자가 가장 많이 고름. 반면 자동 거절, 본인 확인 실패, 정산 2개월 심사 보류, 체크아웃 오류 사례도 있음 | MoR 경로의 1순위. 승인과 첫 정산 확인이 전제 |
| Paddle [PaddleHQ/paddle-agent-skills](https://github.com/PaddleHQ/paddle-agent-skills) (공식) | Apache-2.0. 2026-11-19, 별 9 | 스킬 13개 | 조사하지 않음 | Threads 직접 읽음: 한국 빌더 1명이 바로 인증받아 쓰기 시작했다고 보고. Reddit 직접 읽음: 승인 뒤 며칠~몇 주 만에 해지됐다는 사례 여럿과 5년 무탈 사례가 공존 | 대안. 해지 위험을 고지 |
| Stripe [stripe/ai](https://github.com/stripe/ai) (공식) | MIT. 2026-11-21, 별 2,077 | 스킬 11개 + 훅 있는 플러그인 + 원격 MCP | 한국 거주 판매자의 가입 가능 여부 NOT VERIFIED. Managed Payments의 한국 지원도 NOT VERIFIED | Reddit 직접 읽음: 지원 국가에 있으면 Stripe가 다수 의견. Lemon Squeezy가 Stripe Managed Payments로 안내 중. Threads 직접 읽음: 한국 개인은 못 쓴다고 알고 있다는 글 | Stripe를 쓸 수 있는 사용자용 대안 |
| Freemius | 스킬·저장소 NOT VERIFIED | NOT VERIFIED | NOT VERIFIED | Reddit 직접 읽음: 회사 없는 개인에게 가장 일관되게 긍정적. 세 곳에서 거절당한 모로코 창업자를 받아 줌 | 라우터의 선택지로만. 스킬은 없다고 가정 |
| Creem [armitage-labs/creem](https://github.com/armitage-labs/creem) (공식) | MIT. 2026-11-20, 별 36 | 스킬만 | 한국이 지원 국가에 있음. 개인 규정은 페이지에 없음 | Reddit 직접 읽음: 영국 사용자는 수월, 이집트 창업자는 초대제라는 답을 받음(7개월 전). 그 외 언급 거의 없음. Threads에서는 검색에 나오지 않음 | 보류 |
| Dodo [dodopayments/skills](https://github.com/dodopayments/skills) (공식) | MIT. 2026-11-09, 별 14 | 스킬 + 별도 플러그인 | NOT VERIFIED(지원 국가 페이지 404) | Reddit 직접 읽음: 잔액을 120일 보류한 뒤 전액 몰수했다는 글, 예고 없는 차단 사례. 문제없다는 사용자도 셋 | 보류 |
| PortOne [portone-io/cli](https://github.com/portone-io/cli) (공식 조직) | **LICENSE 파일 없음**. 2026-09-22, 별 0 | 스킬 4개 + CLI + npx MCP | 사업자등록과 PG 계약 필요 | Threads 직접 읽음: PortOne 경유 KG이니시스 심사가 8영업일째 대기, 다른 신청자는 두 달째 | 복사 보류. 국내 PG 경로의 참조 |
| 토스페이먼츠 | 공식 MCP만. npm 메타데이터상 MIT | 문서 검색 MCP | 사업자등록 필요 | Threads 목록만: 가입비가 예상보다 높다는 글 | 참조만 |
| 페이플, 카카오페이 직접 연동 | 스킬·저장소 NOT VERIFIED | NOT VERIFIED | 사업자등록 필요로 보임(NOT VERIFIED) | Threads 직접 읽음: 답글 여러 건이 페이플을 추천. 카카오페이 직접 연동이 가장 빨랐지만 한 달 걸렸다는 답글 | 라우터의 선택지로만 |
| Lemon Squeezy | 공식 스킬 없음 | 해당 없음 | 해당 없음 | Reddit 직접 읽음: 판매자들이 종료 통지를 받음. 2027년 3월까지 | 라우팅에서 제외 |

스킬 자체에 대한 판단은 1차와 같다. Stripe, Polar, Paddle, Dodo, Creem, PortOne이 공식 SKILL.md 묶음을 내고, 그중 "첫 결제를 빨리"라는 목적과 설명이 일치하는 것은 MCP 설치부터 첫 상품과 체크아웃 생성까지 안내하는 Polar의 `setup-polar`다 ([setup-polar SKILL.md](https://github.com/polarsource/agent-toolkit/blob/main/skills/setup-polar/SKILL.md)). 결제 스킬을 이름으로 추천하는 사용자는 Reddit과 Threads에서도 한 명도 찾지 못했다. 사람들이 이야기하는 것은 스킬이 아니라 제공자이고, 그 이야기가 이 슬롯의 설계를 바꾼다.

Reddit의 1인칭 기록에서 비미국권 개인이 막힌 곳은 코드가 아니었다. 법인이 없는 모로코의 18세 창업자는 6월에 제품을 끝내고 8월에야 결제를 받을 수 있었는데 기술 문제 때문이 아니었다고 썼다. Lemon Squeezy, Paddle, Polar에서 거절당했고 Polar는 사람이 보기도 전에 자동 거절했다는 것이다 ([r/SaaS](https://www.reddit.com/r/SaaS/comments/1wj23y1/got_rejected_by_lemon_squeezy_paddle_and_polar_as/)). Polar에 대해서는 승인이 3분 만에 났다거나 연동이 순조로웠다는 짧은 긍정 댓글이 더 많다. 그러나 영국 사용자가 본인 확인을 수십 번 시도하고도 통과하지 못한 사례, 정산이 두 달째 심사 상태라는 댓글, 호스팅 체크아웃에서 고객들이 오류를 겪었는데 판매자가 손쓸 방법이 없었다는 글도 있다 ([r/SaaS MoR](https://www.reddit.com/r/SaaS/comments/1sqfvcu/whats_the_most_solofounderfriendly_merchant_of/), [r/SaaS Polar](https://www.reddit.com/r/SaaS/comments/1wmbv4o/polarsh_in_2026_real_experience_with_reviews_and/), [r/SaaS Polar→Stripe](https://www.reddit.com/r/SaaS/comments/1v9pr0m/thinking_about_moving_from_polar_to_stripe_has/)). Paddle은 승인받고 옮긴 뒤 며칠이나 몇 주 만에 해지됐다는 사례가 한 스레드에서만 다섯 건이고, Dodo는 500달러가 안 되는 돈을 120일 보류한 끝에 돌려주지 않았다는 글이 있다 ([r/SaaS Paddle](https://www.reddit.com/r/SaaS/comments/1whzvnu/do_not_use_paddle_as_your_payment_processor/), [r/PaymentProcessing](https://www.reddit.com/r/PaymentProcessing/comments/1x0to6o/dodo_payments_held_my_money_for_120_days_then/)). 이 때문에 1차에서 대안으로 올렸던 Dodo와 Creem은 보류로 내리고, 회사 없는 개인에게 평이 가장 고른 Freemius를 라우터의 선택지에 더한다. Freemius의 에이전트 스킬 유무는 확인하지 않았다.

한국 상황은 Reddit에서는 전혀 나오지 않았고 Threads에서 윤곽이 잡혔다. 한 바이브 코더는 PortOne을 거쳐 KG이니시스에 신청한 지 8영업일째 기다리라는 답만 받고 있다고 썼다. 답글 40개 가운데 두 달을 넘겼다는 신청자, 카카오페이 직접 연동이 가장 빨랐는데도 한 달 걸렸다는 사람, 페이플을 권하는 사람들이 있었다. 기다리는 동안 푸터의 사업자정보, 이용약관, 환불규정, 가격 표시를 갖춰 두면 보완 요청이 하루짜리 일로 줄어든다는 실무 조언도 있었다 ([Threads @kimminkkki](https://www.threads.com/@kimminkkki/post/DfRDyjeHU-K)). 사업자등록을 마친 뒤에야 결제 수단이 없다는 것을 깨달았다는 글에는 특정 PG를 권하는 답이 없었다. 계좌이체로 먼저 받아 보고 사용자가 실제로 돈을 내는지 보라는 답, 모바일이면 인앱결제가 가장 쉽다는 답이 달렸다 ([Threads @myuk__tt](https://www.threads.com/@myuk__tt/post/De523OuEoAi)). 15년 경력의 엔지니어 겸 멘토는 한국에서 합법적으로 매출을 받으려면 개인사업자가 필요하고, 등록하면 건강보험 지역가입 전환과 국민연금 같은 비용이 수입보다 먼저 생기며, 사업자등록 없이 할 수 있는 길은 Polar나 Lemon Squeezy 같은 MoR 또는 광고 모델뿐이라고 정리했다. 이것은 한 사람의 의견이지 세무 자문이 아니다 ([Threads @dalgom.bami](https://www.threads.com/@dalgom.bami/post/DQYy48QEgAY)). 따라서 계좌이체 우선 조언도 사업자등록이 필요 없다는 뜻으로 옮기면 안 된다.

Polar가 한국 개인에게 실제로 통하는지는 여전히 열려 있다. 1차에서 읽은 2026-03-26자 블로그는 사업자등록 없는 개인이 Polar 계정 심사를 거의 바로 통과하고 체크아웃 링크까지 만든 과정을 적었지만, 정산 계좌 연결은 SWIFT 코드와 영문 예금주명 요건에 막혀 은행 방문이 필요했다고 끝난다 ([kichang.info](https://kichang.info/blog/polar-payment-no-registration)). Threads에서는 Lemon Squeezy로 해외 구매자에게 달러 결제를 받는 판매자가 다시 만든다면 Polar를 쓰고 싶다고 했는데, 이 사람은 한국 개인사업자로 운영하고 있고 달러 수익 강의 자료를 파는 계정이다 ([Threads @yooyoung.design](https://www.threads.com/@yooyoung.design/post/DSuZKYNj79v)). 사업자등록 없는 한국 개인이 Polar에서 돈을 실제로 받았다는 1인칭 기록, 그 정산이 어떻게 과세되는지에 대한 기록은 Reddit, Threads, 블로그 어디에서도 찾지 못했다. Stripe Connect Express가 한국에서 개인 유형을 받는지도 NOT VERIFIED다.

Lemon Squeezy 종료는 Reddit에서 판매자들이 받은 통지로 확인됐다. 결제 처리는 2027년 3월까지이고, 판매자들은 Polar를 가장 많이 고르며, Lemon Squeezy는 Stripe Managed Payments로 안내하고 있다 ([r/SaaS](https://www.reddit.com/r/SaaS/comments/1xxsrn7/lemon_squeeze_shutting_down/), [r/macapps](https://www.reddit.com/r/macapps/comments/1xxs6ek/lemon_squeezy_shutdown/)). Threads에서는 종료에 관한 글이 한 건도 나오지 않았으므로 Threads를 이 사실의 근거로 쓰면 안 된다. Stripe Managed Payments는 결제와 부가세만 처리하고 라이선스 키나 파일 호스팅은 없으며 지원하지 않는 나라가 있다. 지원 국가 수는 스레드의 Stripe 직원이 80개국 이상이라고 했고 1차에서 본 제3자 블로그는 37개국이라 했으니, 한국 포함 여부는 NOT VERIFIED다. Reddit에서 반복된 실무 조언은 세 가지다. 가입 전에 문의를 보내 지원 속도를 시험하고, Paddle은 사이트와 가격과 환불 정책을 심사하니 출시 며칠 전에 신청하고, 첫 정산이 진짜 시험이라는 점을 감안하라는 것이다 ([r/SaaS](https://www.reddit.com/r/SaaS/comments/1xx6d79/payment_platforms_which_oneee/)).

벤더 스킬의 기술적 주의점은 1차와 같다. Stripe의 `stripe-best-practices`는 API 버전이 본문에 박혀 있어 복사본이 빨리 낡고, 플러그인 전체를 가져오면 사용 보고 훅이 따라온다. 무엇이 전송되는지는 NOT VERIFIED다 ([SKILL.md](https://github.com/stripe/ai/blob/main/skills/stripe-best-practices/SKILL.md), [hooks.json](https://github.com/stripe/ai/blob/main/providers/claude/plugin/hooks/hooks.json)). Polar, Creem, Dodo, Paddle 스킬의 웹훅 처리 품질은 본문을 한 줄씩 검토하지 않았다. 한국 블로그가 추천한 Hookdeck의 webhook-skills 저장소도 NOT VERIFIED다.

### 배포: deploy-to-vercel은 그대로 두고, 저장소당 플랫폼 하나만 켠다

| 후보 | 라이선스 | 유지 상태 | 형태 | 사용자 근거(접근 수준) | 번들 판단 |
|---|---|---|---|---|---|
| [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) `deploy-to-vercel` | **LICENSE 파일 없음**. README는 MIT라고 표기 | v4.0.0, 2026-11-20, 별 34,681 | 스킬만. MCP·훅 없음 | Reddit에서 이 스킬을 다룬 스레드를 찾지 못함. Vercel 자체는 비기술 빌더가 자주 꼽는 호스트 | 확인 전에는 런타임 설치 |
| [cloudflare/skills](https://github.com/cloudflare/skills) | Apache-2.0 | 2026-11-17, 별 3,424 | 스킬 22개 + 원격 MCP | Reddit 직접 읽음: 비기술 빌더 스레드에서 Cloudflare Pages/Workers가 가장 자주 나온 답 | 복사가 필요할 때의 첫 대안 |
| [railwayapp/railway-skills](https://github.com/railwayapp/railway-skills) `use-railway` | MIT | 2026-11-18, 별 345 | 스킬 1개 + 원격 MCP + Bash 자동 승인 훅 | Reddit 직접 읽음: DevOps를 몰라도 띄울 수 있었다는 평. 자동 승인 훅이 Vercel 텔레메트리보다 큰 문제라는 지적 | 훅을 뺀 스킬 폴더만 |
| [netlify/context-and-tools](https://github.com/netlify/context-and-tools) `netlify-deploy` | MIT | 2026-11-20, 별 55 | 스킬 16개 + 원격 OAuth MCP | Reddit 직접 읽음: 자주 꼽히는 호스트 중 하나 | 복사 가능 |
| [render-oss/skills](https://github.com/render-oss/skills) `render-deploy` | MIT | 2026-11-20, 별 106 | 스킬 22개. MCP에 API 키 필요 | Reddit 직접 읽음: 전송량 요금이 월 1,300달러 페이스였다는 사용자 1명 | 후순위 |
| [vercel/vercel-plugin](https://github.com/vercel/vercel-plugin) | Apache-2.0(짧은 고지문만) | v0.56.0, 2026-11-20, 별 344 | 스킬 39개 + 훅 + CLAUDE.md 주입 + 원격 MCP | Reddit 직접 읽음: 텔레메트리가 기본으로 켜져 있고 환경 변수로 끈다는 보고(자기 블로그 홍보 글). HN의 4월 고발(직접 읽음) | 번들 부적합 |

1순위는 바꾸지 않는다. `deploy-to-vercel`은 프리뷰 배포가 기본이고, git push 전에 묻고, 계정 없이 임시 URL을 받는 폴백이 있으며, 지시문만 있고 훅이나 텔레메트리가 없다 ([SKILL.md](https://github.com/vercel-labs/agent-skills/blob/main/skills/deploy-to-vercel/SKILL.md)). 걸림돌도 그대로다. 저장소에 LICENSE 파일이 없어 Vercel에 확인받기 전에는 복사하지 말고 런타임 설치를 안내해야 한다 ([choosealicense.com](https://choosealicense.com/no-permission/)). 이 스킬 자체를 다룬 Reddit 스레드는 찾지 못했고, Threads에서는 배포 관련 글이 거의 나오지 않았다.

대안의 순서는 바꾼다. 비기술 바이브 코더에게 어디에 배포하느냐고 물은 스레드(추천 44·댓글 68)에서 가장 자주 나온 답은 무료 구간이 넉넉한 Cloudflare Pages/Workers였고, 그다음이 Vercel과 Supabase 조합, Railway였다. 배포 자체는 대개 쉬운 부분이고 어려운 것은 환경 변수, 인증, 노출된 데이터처럼 걱정해야 하는지조차 모르는 것들이라는 댓글이 이 슬롯과 출시 전 점검 슬롯의 관계를 잘 요약한다 ([r/vibecoding](https://www.reddit.com/r/vibecoding/comments/1vt6kkl/vibe_coders_especially_if_youre_not_very/)). `cloudflare/skills`는 Apache-2.0이라 복사가 필요하면 첫 대안이 된다. 다만 한 사용자의 계획 비교에서 Cloudflare 스킬이 일반 Node 서버는 Workers에서 돌지 않는다고 경고했듯이, 모든 프로젝트에 맞는 것은 아니다.

플러그인을 통째로 들이는 일은 Reddit에서도 경계 대상이다. 공식 마켓플레이스의 배포 플러그인 14개를 모두 켜면 스킬 165개와 MCP 연결 11개가 추가된다는 보고가 있고, 그 글의 최상위 댓글은 Railway 훅이 `railway up`이나 변수 설정 명령을 확인 없이 운영 환경에 실행할 수 있어 Vercel의 텔레메트리보다 큰 문제라고 지적했다. 권고는 사용자 수준에 설치하되 저장소마다 `.claude/settings.json`에서 정확히 하나만 켜라는 것이다 ([r/ClaudeCode](https://www.reddit.com/r/ClaudeCode/comments/1xqxg43/loaded_14_deploy_plugins_into_claude_code_vercel/)). 이 글도 자기 블로그를 홍보하는 한 사람의 측정이지만, Railway 훅과 Vercel 텔레메트리의 존재는 1차 저장소 확인과 일치한다 ([railway hooks.json](https://github.com/railwayapp/railway-skills/blob/main/plugins/railway/hooks/hooks.json), [vercel-plugin README](https://github.com/vercel/vercel-plugin/blob/main/README.md)). 한국어 Threads에서는 토스 미니앱(앱인토스)이 배포·유통 대상으로 몇 번 보였다(목록만). 직접 읽은 글 하나는 미니앱 8개가 14일 동안 9,000원을 벌었다는 경고성 수치를 준다 ([Threads @devjihwan](https://www.threads.com/@devjihwan/post/DbdmBOuEYmX)).

### 랜딩·카피·론칭: 팩에서 낱개만 뽑고, 카피는 첫 고객의 말에서 가져온다

| 후보 | 라이선스 | 유지 상태 | 형태·의존성 | 사용자 근거(접근 수준) | 번들 판단 |
|---|---|---|---|---|---|
| [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) | MIT | v2.14.25, 2026-11-20, 별 61,910 | 스킬 53개. 스킬마다 `references/` 폴더 | Reddit 직접 읽음: 설치 수 상위 7개 중 6개가 이 팩의 낱개 스킬(순위 사이트 운영자의 글). 품질에 대한 1인칭 댓글은 쓸 만하지만 구멍이 뚜렷하다는 것 하나. 마케터 블로그 2곳(직접 읽음) | 4~5개를 버전 고정해 복사 |
| [whawkinsiv/solo-founder-skills](https://github.com/whawkinsiv/solo-founder-skills) `landing-page`, `first-customers`, `pricing` | MIT | 2026-10-16, 별 269 | 60~80줄 단일 파일 | Reddit과 Threads 어디에서도 언급을 찾지 못함 | 대안이자 자체 스킬의 본보기 |
| [blader/humanizer](https://github.com/blader/humanizer) | MIT | 2026-11-19, 별 72,039 | SKILL.md 한 장. 영어 | Reddit 직접 읽음: 휴머나이저 전용 스레드의 노출 댓글에는 이름이 없음. 일반 스레드에서 humanizer를 매일 쓴다는 사용자는 있음. HN 댓글(직접 읽음). Threads에서는 별 순위 목록에만(목록만) | 선택 사항 |
| [hjongc/humanizer-kr](https://github.com/hjongc/humanizer-kr) | MIT | 2026-11-19, 별 27 | 장르 인식, 저장되는 문체 프로필 | Threads 검색에 나오지 않음. 기여자 1명 | 문체 프로필 방식이 Reddit의 합의와 맞음. 유지 위험 |
| [epoko77-ai/im-not-ai](https://github.com/epoko77-ai/im-not-ai), [NomaDamas/k-skill](https://github.com/NomaDamas/k-skill) `korean-humanizer` | 둘 다 MIT | 2026-11-17 / 2026-11-16 | Python·에이전트 9개 / 프롬프트만 | Threads 검색에 나오지 않음. 채택 근거는 별 수뿐 | 권장 설치 / 복사 가능 |
| 한국산 SEO·GEO 스킬(작성자 @kindainvestor) | NOT VERIFIED. 저장소 이름을 확보하지 못함 | NOT VERIFIED | 진단과 구현을 함께 한다고 소개됨 | Threads 직접 읽음: 조회 24만 4천으로 이번 조사 최대. 두 달 뒤 꾸준히 쓴다는 사용 답글 1건. 작성자 본인의 홍보 글 | 저장소 확인이 먼저 |
| `last30days` | NOT VERIFIED | NOT VERIFIED | 최근 30일의 Reddit·X·YouTube 반응 수집으로 소개됨 | Threads 목록만. 한국 wikidocs 가이드북은 상위로 꼽음 | 수요 조사 보조 후보. 확인 필요 |
| [slavingia/skills](https://github.com/slavingia/skills) | **LICENSE 파일 없음** | 2026-04-14, 별 11,197 | 스킬 10개 | 작성자 본인의 HN 제출 1점 | 복사 불가 |

marketingskills의 위치는 Reddit에서 확인됐다. 설치 수로 본 마케팅·SEO 스킬 상위 일곱 중 여섯이 이 팩의 낱개 스킬이고, 사람들은 저장소 전체가 아니라 필요한 스킬만 뽑아 간다는 것이 글쓴이의 해석이다. 이 글쓴이는 순위 사이트를 운영한다. 같은 스레드의 유일한 1인칭 품질 평가는 일찍 나온 만큼 쓸 만하지만 아는 사람 눈에는 구멍이 뚜렷하다는 것이었고, 설치 수는 먼저 발견된 것을 보여 줄 뿐 계속 쓰이는 것을 보여 주지 않는다는 지적도 있었다 ([r/Agentic_SEO](https://www.reddit.com/r/Agentic_SEO/comments/1vpgr1w/top_7_claude_skills_for_marketing_and_seo_by/)). 이 팩으로 첫 유료 고객을 얻었다는 기록은 이번에도 없다. 그래서 복사 대상을 1차의 8개 안팎에서 `copywriting`, `pricing`, `offers`, `prospecting`(demand-signals 분기), `launch`의 4~5개로 줄인다. `.agents/product-marketing.md` 파일은 팩의 `product-marketing` 스킬 대신 Revive가 이미 모은 맥락으로 직접 써 넣으면 된다 ([copywriting SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/copywriting/SKILL.md)). 2.0에서 스킬 이름 17개가 바뀐 점, `launch` 본문의 협찬사 언급, 하루에도 여러 번 찍히는 릴리스는 1차에서 적은 대로 주의해야 한다 ([README](https://github.com/coreyhaines31/marketingskills/blob/main/README.md), [launch SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/launch/SKILL.md)).

AI 티를 지우는 단계는 평가가 내려갔다. 1차는 Hacker News 댓글을 근거로 `blader/humanizer`를 복사 대상에 넣었다 ([HN 50153144](https://news.ycombinator.com/item?id=50153144)). Reddit의 휴머나이저 전용 스레드(추천 98·댓글 52)에서 가장 강한 합의는 범용 휴머나이저보다 개인 문체 프로필이 낫다는 것이었다. 질문 100개쯤에 답해 만들거나 자기 글의 수정 전후 20쌍 이상으로 만든 프로필을 쓰고, 그래도 손으로 다 고친다는 사람들이다. 노출된 댓글에 `blader/humanizer`의 이름은 없었고, 제3자 스킬은 설치 전에 프롬프트 인젝션이 없는지 저장소를 살피라는 경고가 있었다 ([r/claudeskills](https://www.reddit.com/r/claudeskills/comments/1v8wa5r/whats_the_best_humanizer_skill_out_there/)). 한국어 휴머나이저는 Threads 검색에서 한 건도 나오지 않아, im-not-ai를 사실상 표준이라 부른 1차의 표현은 별 수에만 근거한 것으로 낮춰 읽어야 한다. Threads 검색이 얕으니 이것도 약한 부정 근거다. 문체 프로필을 저장하는 `hjongc/humanizer-kr`의 방식은 Reddit의 합의와 맞지만 README 스스로 문체 재현 품질이 검증되지 않았다고 밝힌다 ([humanizer-kr README](https://github.com/hjongc/humanizer-kr/blob/main/README.md)).

카피의 재료에 대한 조언은 더 구체적이다. 5달러짜리 제품으로 첫 유료 고객 넷을 얻은 사람에게 달린 최고의 조언은 그 네 명이 한 말을 그대로 적어 두라는 것이었다. 그 표현이 지어낸 어떤 문구보다 좋은 랜딩 카피가 된다는 이유다 ([r/SideProject](https://www.reddit.com/r/SideProject/comments/1w3e8hh/six_days_ago_i_posted_about_my_first_customer_i/)). 고객의 말을 수집해 상태 파일에 저장하고 카피 스킬에 넘기는 일은 Revive가 직접 쓸 부분이다. Threads에서 가장 큰 반응을 얻은 것은 한국 개발자가 무료로 공개했다는 SEO·GEO 스킬 글이다. 조회 24만 4천에 두 달 뒤의 사용 답글이 하나 있다. 저장소 링크가 든 글의 3부가 표시되지 않아 이름조차 확보하지 못했고 작성자 본인의 홍보 글이므로, 지금은 후속 확인 대상일 뿐이다 ([Threads @kindainvestor](https://www.threads.com/@kindainvestor/post/Dchdl9vE5gP)). ChatGPT가 제품을 추천해 줘서 고객이 왔다는 이야기가 Reddit의 첫 고객 사례 세 건(그중 하나는 제목만 봄)에 나오는 것을 보면 AI 검색 노출은 살펴볼 만한 주제다.

### 출시 전 점검: 사람들이 실제로 돌리는 것은 스킬이 아니라 30분짜리 체크리스트다

| 후보 | 라이선스 | 유지 상태 | 형태·의존성 | 사용자 근거(접근 수준) | 번들 판단 |
|---|---|---|---|---|---|
| Revive 자체의 결정적 점검 스크립트 | 해당 없음 | 직접 유지 | 계정 둘로 ID 바꿔 넣기, 번들 키 검색, 이력 시크릿 스캔, 무세션 `curl`, 지출 상한, RLS | Reddit 직접 읽음: 보안 점검을 물은 스레드에서 거의 모두가 스킬이 아니라 이 수동 점검을 꼽음 | 직접 작성(권장) |
| 새 컨텍스트의 독립 리뷰어(자체 서브에이전트) | 해당 없음 | 직접 유지 | 읽기 전용, 전체 diff 대상 | Reddit 직접 읽음: 수천 회 실행했다는 사용자가 유일하게 계속 값을 한다고 꼽은 것 | 직접 작성(권장) |
| 내장 `/security-review` ([프롬프트 공개 저장소](https://github.com/anthropics/claude-code-security-review)) | 명령 파일은 MIT. Claude Code 본체는 재배포 불가 | 저장소 마지막 커밋 2026-02-11 | 미반영 변경만 검토 | Reddit 직접 읽음: 없는 것보다 낫지만 diff가 클수록 조용해짐. 영역별로 나눠 돌리라는 조언 | 번들하지 말고 호출 |
| [raroque/vibe-security-skill](https://github.com/raroque/vibe-security-skill) | MIT | **마지막 커밋 2026-03-15**, 별 1,241 | SKILL.md + 참조 9개 | Reddit 직접 읽음: `/vibe-security`에 대한 유일한 1인칭 언급이 웬만큼 하는 빌더라면 찾는 것이 적고 거짓 안도감을 준다는 것. 작성자의 X 홍보(스니펫만) | 1순위에서 참고 체크리스트로 강등 |
| Anthropic [`security-guidance`](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/security-guidance) 플러그인 | Apache-2.0 (1차 확인) | 공식 마켓플레이스 | 편집 시 패턴 경고, 턴 종료 시 diff 리뷰, 커밋 시 리뷰. Python 3.8+ | Threads 소개 글 직접 읽음(큐레이션 계정, 사용 후기 답글 없음) | 선택 설치로 안내 |
| superpowers [`verification-before-completion`](https://github.com/obra/superpowers/blob/main/skills/verification-before-completion/SKILL.md) | MIT | v7.0.2, 2026-11-03 | SKILL.md 한 장, 580단어 | Reddit에서 이름으로 다룬 스레드 없음. 세션 내 리뷰 스킬 전반이 버그를 놓친다는 보고 | 복사 대상에서 제외. 원칙만 자체 관문에 흡수 |
| [cloudflare/security-audit-skill](https://github.com/cloudflare/security-audit-skill) | MIT | 2026-09-14, 별 76,749 | 약 24,800단어. 병렬 서브에이전트, 샌드박스 | Reddit 직접 읽음: Max 요금제의 5시간 창 셋과 주간 토큰 절반을 쓰고 감사의 11%만 진행. 다른 사용자도 같은 경험 | 구독 요금제 사용자에게 비권장 |
| Anthropic [`claude-security`](https://github.com/anthropics/claude-plugins-official/blob/main/plugins/claude-security/LICENSE) 플러그인 | **독점, 재라이선스 불가** | 공식 마켓플레이스 | 다중 에이전트 스캔 | 영상 제목만(스니펫만) | 재배포 불가 |
| [getsentry/skills](https://github.com/getsentry/skills/tree/main/skills/security-review) `security-review` | Apache-2.0. 참조 자료는 CC BY-SA 4.0 | 2026-11-14, 별 1,193 | 자체 완결 폴더 | 없음 | 대안. share-alike 유의 |
| [trailofbits/skills](https://github.com/trailofbits/skills), [semgrep/skills](https://github.com/semgrep/skills) | CC BY-SA 4.0 / Semgrep Rules License v1.0 | 2026-11-12 / 2026-07-27 | 전문가용 / 스킬 3개 | HN 사용자 1명(직접 읽음) / 없음 | 참조만 / **재배포 불가** |

1차가 꼽은 세 조각 가운데 둘이 Reddit의 1인칭 보고로 약해졌다. Cloudflare의 `security-audit`은 1차에서 심층 감사용 대안이었는데, 한 사용자는 Max 요금제의 5시간 창 세 번과 주간 토큰의 절반을 쓰고도 감사가 11%만 진행됐다고 썼고, 다른 사용자는 더 작은 모델로도 API 일부를 한 번 도는 데 5시간 창 셋이 들었다고 답했다 ([r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/comments/1xkrwiv/i_tried_running_the_cloudflare_securityaudit/)). 구독 요금제를 쓰는 1인 빌더에게 권할 수 없다. `/vibe-security`에 대해서는 보안 스킬 조합을 소개한 글이 웬만큼 하는 바이브 코더라면 찾아내는 것이 많지 않고 거짓 안도감을 줄 수 있다고 적었다. 별을 모으려는 글처럼 읽히는 단일 언급이고, 그 명령이 `raroque/vibe-security-skill`과 같은 것인지는 저장소 이름으로 확인되지 않았다 ([r/vibecoding](https://www.reddit.com/r/vibecoding/comments/1uve1hy/best_claude_skills_to_secure_vibe_coded_apps/)). 그래도 독립 사용 기록이 없던 스킬에 처음 붙은 1인칭 평가가 부정적이라는 점은 무겁다.

대신 드러난 것은 사람들이 실제로 하는 일이다. 출시 전에 보안을 확인했느냐고 물은 스레드(댓글 32)에서 스킬을 꼽은 사람은 거의 없었다. 답은 수동 점검이었다. 테스트 계정 둘을 만들어 한쪽 요청에 다른 쪽 ID를 넣어 보고, 빌드된 JS 번들에서 비밀 키 문자열을 검색하고, gitleaks나 trufflehog으로 커밋 이력 전체를 훑어 한 번이라도 올라간 키는 교체하고, 유료 API를 부르는 경로마다 인증과 사용자별 호출 제한을 걸고 제공자 대시보드에 지출 상한을 두고, 세션 없이 각 API 경로에 `curl`을 날려 보고, Supabase의 `service_role` 키가 클라이언트에 없고 RLS가 켜져 있는지 보는 것이다 ([r/startups](https://www.reddit.com/r/startups/comments/1xvcark/did_you_actually_check_security_before_launching/)). 이 여섯 항목은 대부분 스크립트로 만들 수 있다. 1차가 Revive의 몫으로 적었던 결정적 검사가 이제 이 슬롯의 중심이 된다.

내장 `/security-review`는 바닥선으로 쓰되 관문으로 쓰면 안 된다는 것이 Reddit의 평가다. 큰 PR에서 문제없음이 나왔다는 글에 달린 답은 없는 것보다 낫지만 나중에 문제가 발견된 코드에서도 깨끗하다고 나온 적이 있고, diff가 클수록 조용해진다는 것이었다. 인증, 입력 처리, DB처럼 영역별로 나눠 돌리고, 리뷰어는 읽기가 제한된 별도 에이전트로 두고, 통과 여부는 모델이 아니라 스크립트가 정하게 하라는 권고가 따랐다 ([r/ClaudeCode](https://www.reddit.com/r/ClaudeCode/comments/1xyrw11/securityreview/)). 되살린 프로젝트는 코드가 이미 커밋돼 있어 이 명령이 볼 미반영 변경이 없다는 1차의 지적도 유효하다 ([security-review.md](https://github.com/anthropics/claude-code-security-review/blob/main/.claude/commands/security-review.md)). 검증 쪽에서는 석 달 동안 수천 회를 돌렸다는 사용자의 보고가 가장 구체적이다. 실행 중의 리뷰 스킬은 문제 지점을 들여다보고도 놓치는 일이 잦았고, 전체 diff를 읽기 전용으로 보는 독립된 적대적 리뷰어가 열 번에 한 번꼴로 실행을 막았다고 한다 ([r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/comments/1xckkpr/are_superpowers_skills_and_sdd_still_worth_it_on/)). 한 사람의 수치이지만, 세션 안에서 스스로 확인하게 하는 `verification-before-completion`을 복사하는 것보다 Revive가 새 컨텍스트의 리뷰어를 직접 두는 쪽을 지지한다.

Threads에서는 Anthropic 공식 `security-guidance` 플러그인을 소개하는 글이 읽혔다. 편집, 턴 종료, 커밋의 세 시점에 자동으로 점검하고, 쉬운 문제만 잡으며 숙련된 리뷰를 대체하지 않는다는 Anthropic의 단서를 그대로 전한다 ([Threads @eddiemoon0720](https://www.threads.com/@eddiemoon0720/post/DY4C-oeD6jp)). 1차 저장소 확인으로는 Apache-2.0이고 Python 3.8 이상과 LLM 리뷰용 자격 증명이 필요하며 턴마다 LLM 호출이 생긴다 ([README](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/security-guidance)). 선택 설치로 안내할 만하다. 보안이 아닌 출시 전 점검 두 가지도 Threads의 실제 경험에서 나왔다. PG 심사에 대비한 푸터 사업자정보·약관·환불규정·가격 표시 점검과, 디자인을 바꾸기 전후에 360px 모바일 화면과 키보드 탭 순서를 기록해 두는 회귀 점검이다. `/code-review`가 내장 기능인지는 여전히 NOT VERIFIED다. Threads에서는 유출이나 해킹을 겪었다는 1인칭 글을 찾지 못했다.

## 사람들이 멈추는 곳은 코드가 아니라 발견·검증·결제·서류다

두 플랫폼의 1인칭 기록은 Revive가 어디에 힘을 실어야 하는지에 대해 1차 보고서와 다른 그림을 준다. Threads에서 읽은 글에서 멈춤의 원인이 깨진 코드로 서술된 경우는 드물었다. 자주 나온 순서대로 적으면 아무도 제품을 찾지 못한다는 것, 시장 확인을 하지 않았다는 것, 결제와 서류, 그리고 조금만 더 다듬자는 미루기였다. 1년에 iOS 앱 14개와 토스 미니앱 8개를 만든 개발자는 기획부터 심사 제출까지 하루에 끝낸 앱이 같은 이름의 앱 열 개 중 여덟 번째였다는 것을 나중에 알았다. Claude Code는 이름을 검색해 보지 않았고, 에이전트가 쓴 기획 문서는 경쟁자가 많다는 사실을 검증된 시장으로 읽었다고 한다 ([Threads @devjihwan](https://www.threads.com/@devjihwan/post/DbdmBOuEYmX)). 넉 달 동안 앱 다섯 개를 낸 20년 차 개발자도 수익이 나지 않는 이유가 먼저 자리 잡은 앱만 노출되는 스토어 검색에 있다는 답글들을 받았다 ([Threads @hangkok2023](https://www.threads.com/@hangkok2023/post/DeTLFKuk7jD)). 서류 쪽에서는 사업자 관련 절차에 돈과 품이 드는데 아직 1원도 벌지 못했다며 의욕이 꺾였다는 인용 글이 있었다 ([Threads @dalgom.bami](https://www.threads.com/@dalgom.bami/post/DQYy48QEgAY)).

Reddit도 같은 이야기를 한다. 아이디어에 며칠이나 몇 주를 몰입해 만들고는 그대로 끝나는 프로젝트로 GitHub이 가득하다는 글이 Revive의 사용자를 그대로 묘사한다. 글쓴이는 90일 동안 커밋이 없으면 죽은 것으로 정의했다 ([r/SideProject](https://www.reddit.com/r/SideProject/comments/1xxqq3p/i_cant_finish_my_vibecoded_projects_so_i_built_a/)). 바이브 코딩 앱으로 실제 돈을 번 사람이 있느냐는 스레드(댓글 213, 표본만 읽음)의 일관된 교훈은 만드는 일은 쉬워졌고 고객을 찾고 대화하고 파는 데 시간이 든다는 것, 그리고 자기 문제를 풀려고 만든 제품이 돈을 번다는 것이었다 ([r/vibecoding](https://www.reddit.com/r/vibecoding/comments/1vk6y8b/has_anyone_here_actually_made_serious_money_from/)).

첫 유료 고객에 이른 사례에서 사람들이 꼽은 계기는 다섯 가지로 모인다. 이미 가진 청중이나 이메일 명단, 직접 연락, 본인이 겪은 문제, 사용자가 이미 모여 있는 곳에 올린 글, 그리고 작동하는 결제다. 3주 만에 유료 구독자 9명을 얻은 사람은 본인이 손으로 하던 일을 디렉터리로 만들고 목록 4,502건을 미리 채운 뒤 등록 업체에 콜드 메일을 보냈다 ([r/vibecoding](https://www.reddit.com/r/vibecoding/comments/1vmmc3d/my_first_vibecoded_app_just_hit_9_paying/)). Threads에서 읽힌 계기는 나중에 전환하지 않고 첫날부터 돈을 받은 것, PG보다 먼저 계좌이체로 받은 것, 모바일에서 인앱결제를 택한 것, MoR로 해외 구매자에게 달러로 판 것, 기능이 아니라 귀여움으로 차별화한 것, Threads에서 청중을 먼저 만든 것이었다 ([Threads @simon.dsgn](https://www.threads.com/@simon.dsgn/post/DZOUBjSjogt)). 어느 플랫폼에서도 스킬 덕분이라고 말한 사람은 없다. 석 달 가까이 플러그인으로 이메일 1,097통을 보내 사람 답장 11건에 유료 0건이었다는 Reddit 글 제목(목록만)은 반대 방향의 경고다.

이것이 Revive가 직접 다루기로 한 수요 검증과 고객 발견에 주는 함의는 분명하다. 검증은 더 만들기 전에 와야 하고, 에이전트의 낙관을 그대로 믿지 않는 장치가 필요하다. 이름과 키워드 충돌 검색, 경쟁자가 많다는 사실을 수요의 증거로 읽지 않는 판정 규칙, 돈을 낼 의사를 가장 싼 방법으로 확인하는 단계가 들어가야 한다. 계좌이체나 결제 링크 하나로 먼저 받아 보는 것이 그 방법이 될 수 있다. 첫 열 명은 손으로 구하고, 그들이 한 말을 그대로 기록해 카피에 쓰며, Reddit에서만 온 구매자는 유통을 증명하지 못한다는 점도 판정에 반영해야 한다. Threads를 읽은 조사자의 판단으로는 디버깅을 앞세우는 Revive는 더 작은 문제를 겨누게 된다. 막힘 해소 슬롯은 필요하지만 입구는 복구가 아니라 "이것을 살릴 가치가 있는가"의 판정이어야 한다.

한국 론칭 채널에 대해서는 Threads 자체가 채널이라는 것이 이번 표본의 결론이다. 과정을 공개하며 만드는 방식으로 쓰이고, 직접 읽은 글에서는 스토어 키워드 검색을 기존 앱이 차지하고 있어 사람들이 앱 이름으로 검색하게 하려고 제작 과정을 올린다는 답글이 있었다. 실패담도 반응을 얻는다. 수치가 있는 사례는 대부분 목록만 본 것이다. Threads에만 알린 무료 사이트가 일주일 만에 일일 방문 1,000명을 넘겼다는 글, 게시글에 URL을 넣지 말고 기능을 나열하지 말라는 규칙 글이 그렇다. hypevibe나 앱자랑 같은 새 쇼케이스 디렉터리는 운영자 본인의 홍보 글로 등장했고 효과는 검증되지 않았다 ([Threads @hype.vibe_official](https://www.threads.com/@hype.vibe_official/post/DfyrLqoGRWh)). 디스콰이엇과 긱뉴스는 읽은 글 어디에도 나오지 않았지만 질의를 한 번만 돌렸으니 쓰이지 않는다는 근거로는 약하다. 영어권에서는 Reddit 게시가 첫 고객의 통로로 여러 번 나왔다. marketingskills의 디렉터리 목록에 한국 항목이 없다는 1차의 확인과 합치면, 한국 채널용 게시글 초안과 예절은 Revive가 직접 써야 한다 ([directory-list.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/directory-submissions/references/directory-list.md)).

## 제3자 스킬은 일시적이고 남는 것은 저장된 상태와 관문이다

Reddit을 직접 읽고 나온 가장 불편한 결과는 개별 슬롯이 아니라 번들이라는 발상 자체에 대한 것이다. 스킬을 실제로 쓰느냐는 스레드(추천 57·댓글 71)에서 남아 있는 스킬은 거의 다 직접 쓴 것이었다. 결정적 스크립트를 부르는 스킬, 자기 저장소 지식, 세션 인계 같은 것들이고, 인터넷에서 스킬을 찾아본 적이 없다는 댓글도 있다 ([r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/comments/1xw4eoc/are_people_here_actually_using_skills/)). 1인 개발자용 추천 스레드의 첫 답은 Superpowers를 권하면서도 코드베이스의 맥락을 더하는 것이 아니면 모든 스킬을 일시적인 것으로 여기라고 덧붙였다 ([r/claudeskills](https://www.reddit.com/r/claudeskills/comments/1wqg6mj/are_there_any_best_skills_to_install_for_solo/)). 반복되는 조언은 모델이 새로 나올 때마다 스킬을 다시 평가하고, 두 번 넘게 겪은 실패에만 스킬을 붙이고, 그 스킬이 산출물을 바꾸는지 대화 기록만 바꾸는지 물으라는 것이다. 한 사용자는 Superpowers를 필수 흐름으로 돌렸을 때 병합된 티켓당 비용이 가벼운 구성의 두 배를 넘었다고 보고했다 ([r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/comments/1xckkpr/are_superpowers_skills_and_sdd_still_worth_it_on/)).

Revive와 가장 닮은 실험도 같은 결론을 낸다. 아이디어 검증, 가격, 랜딩, 사용자 인터뷰 등 창업자용 스킬 13개를 만든 작성자가 `claude plugin eval`로 직접 평가했더니 10개 사례 중 8개는 플러그인이 있든 없든 점수가 같았다. 분명히 이긴 한 가지는 새 숫자가 저장된 숫자와 어긋날 때 사실 파일을 갱신하는 일이었다. 댓글 하나는 값은 상태 관리에 있고 프롬프트 문장은 흔한 재화라고 요약했다 ([r/ClaudeCode](https://www.reddit.com/r/ClaudeCode/comments/1xcl0zp/13_claude_code_skills_for_the_founder_side_of_a/)). 추천 1개짜리 작성자 글이지만 자기 제품에 불리한 결과를 스스로 밝힌 것이라 무게가 있다. 가장 큰 스킬 추천 스레드의 최고 인기 댓글도 세션을 닫으며 수정 사항, 결정, 할 일을 기록하는 스킬이었다. 닫을 때마다 여덟 가지를 쏟아내면 쓰지 않게 되니 의식을 가볍게 하라는 설계 원칙이 붙어 있었다 ([r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/comments/1xevkyg/drop_your_best_claude_skills_in_here/)). 어떤 스킬이 작업 방식을 바꿨느냐는 질문에 스킬이 아니라 관문이라고 답한 사람도 있다 ([r/claude](https://www.reddit.com/r/claude/comments/1xuknes/what_claude_skills_have_changed_your_entire/)).

프로젝트 오너는 추천 스킬을 Revive와 함께 배포하기로 이미 정했다. 이 근거는 그 결정을 뒤집을 이유가 아니라 번들의 크기와 성격을 정하는 기준이 된다. 첫째, 함께 배포하는 스킬은 열 개 미만으로 두고 슬롯마다 근거가 가장 단단한 것만 넣는다. 이번 재평가로 보면 `frontend-design`, Polar 스킬 둘, marketingskills 4~5개가 그 대상이고, `diagnosing-bugs`와 `vibe-security`는 넣더라도 선택적 참고 자료라는 표시가 붙어야 한다. 둘째, 번들한 스킬마다 업스트림 커밋 SHA, 마지막으로 검증한 날짜와 모델, 그 스킬이 겨누는 실패를 적는다. 모델이 바뀔 때마다 스킬 없는 실행과 견주어 보고 이기지 못하면 뺀다. 주간 스레드에서 두 번 나오고 아무도 답하지 못한 질문, 곧 내려받은 스킬을 몇 달 뒤에 업데이트해야 하느냐와 이 스킬들을 모두 켜 두느냐에 Revive가 답을 주는 셈이다 ([r/claudeskills 주간](https://www.reddit.com/r/claudeskills/comments/1y0ikqe/my_favorite_claude_skills_this_week_drop_yours_in/)). 셋째, 번들 스킬은 상시 라우터가 아니라 Revive가 단계에 맞춰 이름으로 부르는 부품으로 둔다. 사용자의 지침이 스킬 규칙에 밀렸다는 보고가 있으므로 Revive의 관문 규칙이 번들 스킬보다 우선한다는 점을 구조로 보장해야 한다.

Revive가 직접 써야 하는 것은 1차 때보다 늘었고, 그것이 제품의 본체다. 프로젝트 상태 파일에는 사실과 숫자, 판정 이력, 고객이 한 말, 결제 자격과 정산 요건의 확인 결과가 들어간다. 단계 관문은 살릴 가치 판정, 수요 확인, 결제 가능 확인, 출시 가능 확인으로 이어지고, 통과 여부는 가능한 한 스크립트가 정한다. 여기에 방치된 빌드와 의존성의 복구 절차, 얇은 디버깅 절차, 결제 라우터, 결정적 보안 점검과 독립 리뷰어, 디자인 브리프와 레퍼런스 수집, 수요 검증과 이름 충돌 점검, 한국 채널용 게시글 초안과 한국어 카피 생성, 가벼운 세션 종료 기록이 더해진다. 약관과 개인정보처리방침도 여기에 속한다. wikidocs 가이드북이 소개한 `korean-privacy-terms`는 평가가 낮고 저장소를 특정하지 못했다 ([wikidocs](https://wikidocs.net/435360)). Threads에는 어떤 스킬을 써야 할지 몰라서 스킬을 찾아 주는 `find-skills`가 가장 많이 설치됐다는 글이 있다(목록만). 슬롯 라우팅이라는 Revive의 발상을 지지하는 신호이면서 가장 가까운 범용 대체재가 이미 있다는 뜻이기도 하다.

## 패키징: 복사는 더 적게, 검증 시점을 적고, 훅은 물려받지 않는다

Claude Code 플러그인이 제3자 스킬을 싣는 방법은 문서상 세 가지다. `skills/<name>/SKILL.md`로 복사하는 방법, 자체 마켓플레이스에 업스트림 저장소를 `github`나 `git-subdir` 소스로 등록하고 40자 커밋 `sha`로 고정하는 방법, `plugin.json`의 `dependencies`로 다른 플러그인을 요구하는 방법이다 ([marketplace reference](https://code.claude.com/docs/en/plugins/marketplace-reference.md), [dependencies](https://code.claude.com/docs/en/plugins/dependencies.md)). Anthropic 공식 디렉터리는 317개 항목 중 261개가 SHA로 고정한 외부 참조이고, 커뮤니티 모음은 대개 저장소 안에 복사해 둔다. 조사한 마켓플레이스 13곳 가운데 `dependencies`를 선언한 곳은 없었다 ([claude-plugins-official marketplace.json](https://github.com/anthropics/claude-plugins-official/blob/main/.claude-plugin/marketplace.json)).

혼합형이라는 1차의 권장은 유지하되 각 갈래의 내용이 바뀐다. 복사하는 것은 훅·바이너리·네트워크 호출이 없는 허용적 라이선스의 마크다운 스킬 가운데 이번 재평가를 통과한 것뿐이다. `frontend-design`과 marketingskills 4~5개가 여기에 들고, 선택적으로 `diagnosing-bugs`와 참고 체크리스트로서의 `vibe-security`가 더해진다. 1차에서 복사 대상이던 `systematic-debugging`, `verification-before-completion`, `blader/humanizer`는 빠진다. 빨리 낡는 벤더 스킬인 Polar와, 쓸 수 있는 사용자에 한해 Stripe는 플러그인 전체가 아니라 스킬 폴더만 가져오고 SHA를 기록해 갱신한다. 훅·바이너리·다중 에이전트를 달고 오는 Impeccable, `security-guidance`, im-not-ai, vercel-plugin은 설치를 안내하고 깔려 있으면 감지해서 쓴다. 내장 명령과 재배포할 수 없는 것은 호출하거나 언급만 한다. 배포 스킬은 저장소당 하나만 켜도록 Revive가 프로젝트 설정을 안내한다.

`dependencies`를 기본 수단으로 삼지 않는 이유는 1차와 같다. 마켓플레이스를 넘는 의존성은 사용자가 이미 같은 범위에 설치해 둔 경우가 아니면 루트 마켓플레이스가 `allowCrossMarketplaceDependenciesOn`으로 허용해야 설치되고, 의존 플러그인이 꺼지면 Revive도 꺼지며, 버전 범위 고정은 업스트림이 정해진 형식의 태그를 찍어 줘야 동작한다 ([dependencies](https://code.claude.com/docs/en/plugins/dependencies.md)). 자체 마켓플레이스 항목과 bare-name 의존성을 조합하는 방법, 자체 `plugin.json`이 있는 업스트림에서 특정 스킬 폴더만 골라 오는 방법은 테스트하지 않았다. 오케스트레이터가 다른 플러그인의 스킬을 얼마나 안정적으로 부르는지도 NOT VERIFIED다.

Reddit의 보고는 번들 크기에 대한 문서상의 제약을 실감 나게 한다. 스킬 목록에는 컨텍스트 창의 1%만 배정되고 넘치면 덜 쓰인 스킬의 설명부터 잘리며 항목당 설명은 1,536자로 제한된다 ([Claude Code skills docs](https://code.claude.com/docs/en/skills.md)). 두 팩을 동시에 라우터로 켜면 슬래시 명령 이름이 겹치고 세션 시작 훅이 경쟁한다는 경고, 쓰지 않는 스킬을 걷어내는 데 내장 `/skill-doctor`를 쓰라는 권고가 각각 다른 스레드에 있었다 ([r/AgentSkills](https://www.reddit.com/r/AgentSkills/comments/1w7zmqf/superpowers_vs_agent_skills_vs_matt_pocock_which/), [r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/comments/1xevkyg/drop_your_best_claude_skills_in_here/)). 번들 스킬의 설명은 짧게 쓰고, 프로세스 팩은 하나도 넣지 않으며, Revive 자신이 유일한 프로세스 층이 된다.

고지 의무도 그대로다. MIT는 저작권 고지와 허가 고지를, Apache-2.0은 라이선스 사본, 수정 표시, NOTICE 승계를 요구한다 ([MIT](https://opensource.org/license/mit), [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0)). 복사한 스킬 옆에 업스트림 LICENSE를 두고 루트에 `THIRD_PARTY_NOTICES.md`를 두면 된다. 이것은 라이선스 문면을 읽은 결과이고 법률 자문은 아니다. 재포장이나 재판매를 둘러싼 분쟁 사례는 이번에 Reddit을 읽으면서도 마주치지 않았지만, 그 주제로 검색한 것은 아니다.

### 재배포할 수 없거나 보류해야 하는 후보

| 후보 | 상태 | 근거 | 권장 처리 |
|---|---|---|---|
| Anthropic `claude-security` 플러그인 | 재배포 불가 | 독점 라이선스 ([LICENSE](https://github.com/anthropics/claude-plugins-official/blob/main/plugins/claude-security/LICENSE)) | 언급만 |
| `anthropics/claude-code` (내장 명령 포함) | 재배포 불가 | 모든 권리 유보 ([LICENSE.md](https://github.com/anthropics/claude-code/blob/main/LICENSE.md)) | 내장 명령은 호출만 |
| `semgrep/skills` | 재배포 불가 | Semgrep Rules License v1.0 ([Semgrep Rules License](https://semgrep.dev/legal/rules-license)) | 제외 |
| `slavingia/skills` | 재배포 불가 | LICENSE 파일 없음 ([repo](https://github.com/slavingia/skills)) | 읽고 배우기만 |
| `deanpeters/Product-Manager-Skills` | 유료·재라이선스 제품에는 불가 | CC BY-NC-SA 4.0 ([LICENSING.md](https://github.com/deanpeters/Product-Manager-Skills/blob/main/LICENSING.md)) | 읽기 자료 |
| `vercel-labs/agent-skills` (`deploy-to-vercel`, `web-design-guidelines`) | 보류 | LICENSE 파일 없음. README에 "MIT" 표기만 ([repo](https://github.com/vercel-labs/agent-skills)) | Vercel에 확인하거나 런타임 설치 |
| `portone-io/cli` | 보류 | LICENSE 파일 없음. package.json은 MIT 표기 ([repo](https://github.com/portone-io/cli)) | PortOne에 확인하거나 런타임 설치 |
| `supabase-community/supabase-plugin`, `netlify/netlify-mcp`, `armitage-labs/creem-skills` | 복사 금지 | LICENSE 파일 없음 ([supabase-plugin](https://github.com/supabase-community/supabase-plugin), [netlify-mcp](https://github.com/netlify/netlify-mcp), [creem-skills](https://github.com/armitage-labs/creem-skills)) | 참조만 |
| `multica-ai/andrej-karpathy-skills`, `ComposioHQ/awesome-claude-skills` | 복사 금지 | 라이선스 미검출 ([karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills), [Composio](https://github.com/ComposioHQ/awesome-claude-skills)) | 참조만 |
| `hesreallyhim/awesome-claude-code` | 복사·개작 불가 | CC BY-NC-ND 4.0 ([LICENSE](https://github.com/hesreallyhim/awesome-claude-code/blob/main/LICENSE)) | 링크만 |
| `trailofbits/skills`, getsentry `security-review`의 참조 자료 | 조건부 | CC BY-SA 4.0 ([trailofbits LICENSE](https://github.com/trailofbits/skills/blob/main/LICENSE), [getsentry LICENSE](https://github.com/getsentry/skills/blob/main/skills/security-review/LICENSE)) | 수정하지 않고 참조 |
| `taste-skill` 2.5.x 스킬 폴더 | 조건부 | 코드는 MIT. Unsplash License 사진 274장 등 동봉 ([photos.json](https://raw.githubusercontent.com/Leonxlnx/taste-skill/main/skills/taste-skill/assets/photos/photos.json)) | 복사하지 않음 |
| `yayashuxue/solo-founder-playbook` | NOT VERIFIED | 기본 경로에 LICENSE 없음 ([repo](https://github.com/yayashuxue/solo-founder-playbook)) | 확인 전 제외 |
| 토스페이먼츠 문서 MCP | 참조 권장 | npm 메타데이터만 MIT ([npm](https://registry.npmjs.org/@tosspayments/integration-guide-mcp)) | 버전을 고정해 참조 |

### 2차에서 새로 나왔지만 저장소를 확인하지 않은 후보

아래 후보는 Reddit이나 Threads에서만 확인됐다. 라이선스, 최근 커밋, 재배포 가능 여부를 이번 라운드에 GitHub에서 읽지 않았으므로 번들 대상으로 다루면 안 된다.

| 후보 | 등장한 곳(접근 수준) | 저장소 사실 | 다음 단계 |
|---|---|---|---|
| `heydamir/unslop` | Threads 직접 읽음(큐레이션 계정) | 전부 NOT VERIFIED | 저장소·라이선스 확인 후 디자인 슬롯 재검토 |
| `nutlope/hallmark` | Reddit 직접 읽음(자기 블로그 홍보 글) | 게시자는 MIT라고 적음. NOT VERIFIED | 저장소 확인 |
| Ponytail (`DietrichGebert/ponytail`) | Reddit 직접 읽음(최소 6개 스레드), wikidocs | 전부 NOT VERIFIED | 저장소 확인. 과잉 구현 방지용 후보 |
| 한국산 SEO·GEO 스킬(@kindainvestor) | Threads 직접 읽음(작성자 홍보 글) | 저장소 이름 미확보. 전부 NOT VERIFIED | 글 3부에서 저장소 이름 확보 |
| `last30days` | Threads 목록만, wikidocs | 전부 NOT VERIFIED | 저장소 확인. 수요 조사 보조 후보 |
| `michael-ilic/solo-venturing` | Reddit 직접 읽음(작성자 댓글) | 전부 NOT VERIFIED | 선행 사례로 열람 |
| `emotixco/claude-skills-founder` | Reddit 직접 읽음(작성자 글) | 전부 NOT VERIFIED | 선행 사례로 열람. 평가 방법 참고 |
| `Beakpoint-Insights/roost` | Reddit 직접 읽음(작성자 댓글) | 전부 NOT VERIFIED | 선행 사례로 열람 |
| `Jakeschincariol/replica-skill` | Threads 목록만 | 게시글은 MIT라고 적음. NOT VERIFIED | 필요하면 확인 |
| `petergyang/no-ai-slop`, `manish-uxai/design-review`, `Arcanum-Sec/sec-context` | Reddit 댓글(직접 읽음) | 전부 NOT VERIFIED | 필요하면 확인 |
| Freemius, 페이플, Stripe Managed Payments | Reddit·Threads 직접 읽음 | 서비스. 에이전트 스킬 유무와 한국 개인 지원 NOT VERIFIED | 결제 라우터의 선택지로 조사 |

`emilkowalski/skills`와 Anthropic `security-guidance`는 이 표에 넣지 않았다. 앞의 것은 1차에서 MIT LICENSE를, 뒤의 것은 Apache-2.0 LICENSE를 읽었다. `emilkowalski/skills`의 별 수는 Threads 글이 1만에 가깝다고 적었지만 1차에서 GitHub 페이지로 읽은 수는 58,690이었고, 최근 커밋일은 NOT VERIFIED다. `anthropics/skills`의 문서 스킬이 현재 Apache-2.0이라는 1차의 정정과, 그 변경 시점이 NOT VERIFIED라는 점도 그대로다 ([README](https://github.com/anthropics/skills/blob/main/README.md)).

## 부활에서 첫 결제까지 가는 선행 사례는 없고, 가까운 것들의 강점은 상태와 판정이다

방치된 코드베이스를 되살려 첫 유료 고객까지 데려가는 스킬이나 플러그인은 Reddit과 Threads를 직접 읽고도 나오지 않았다. 구조가 가장 닮은 것은 여전히 `whawkinsiv/solo-founder-skills`다. 스킬 21개, MIT, 별 269개이고, 유료 고객 수로 단계를 판정하는 `journey`와 랜딩, 결제, 보안, 출시 판정, 첫 고객 스킬을 갖췄다(요약 경유) ([repo](https://github.com/whawkinsiv/solo-founder-skills)). 다만 Reddit과 Threads 어디에서도 이 저장소에 대한 언급을 찾지 못했다. 채택이 검증되지 않았다는 1차의 평가가 굳어진다.

이번에 더해진 선행 사례는 셋이다. `michael-ilic/solo-venturing`은 작성자가 주간 스레드 댓글에서 소개한 것으로, 앱 아이디어를 비판적으로 코칭해 측정 가능한 결과와 진행·전환·중단·보류 판정을 낸다고 한다. 코칭 태도로는 Revive와 가장 가깝지만 부활 도구는 아니고 저장소는 열어 보지 않았다. `emotixco/claude-skills-founder`는 앞 절에서 다룬 대로 산출물을 폴더에 쌓고 앞선 결과를 읽게 하는 구조와, 스킬 없는 모델과 견준 자체 평가를 보여 준다. `Beakpoint-Insights/roost`는 아이디어를 운영 환경까지 조각 단위로 만들고 실제 브라우저에서 QA하는 엔지니어링 파이프라인이다. 세 곳 모두 작성자 본인의 소개이고 저장소 사실은 NOT VERIFIED다. Threads 목록에서 본 `replica-skill`은 기존 앱을 분석해 복제하는 11단계 파이프라인으로, 1차에서 확인한 `Jakeschincariol/founder-skill`과 같은 작성자다 ([founder-skill](https://github.com/Jakeschincariol/founder-skill)). 세션 연속성 스킬들, 곧 세션 종료 기록과 프로젝트 인계 스킬이 "되살리기"에 가장 가까운 기존 습관이라는 점도 Reddit에서 확인됐다.

gstack(MIT, 별 142,296)은 1차의 평가 그대로 가상 제품팀 흐름과 감지 후 사용 방식을 보여 주는 참고 사례다 ([gstack README](https://github.com/garrytan/gstack)). Revive가 다를 수 있는 지점은 조금 달라졌다. 아이디어가 아니라 이미 있는 방치된 코드베이스에서 출발한다는 점과 한국 시장의 결제·서류·채널을 다룬다는 점은 그대로다. 1차가 꼽았던 "슬롯별로 검증된 커뮤니티 스킬로 보낸다"는 차별점은 약해졌다. 검증된 커뮤니티 스킬이 생각보다 적기 때문이다. 그 자리를 대신할 것은 저장된 상태와 판정이다. 선행 사례의 작성자가 스스로 측정해 확인한 유일한 우위가 바로 그것이었다. 창업자용 팩 대부분의 채택이 낮다는 사실은 자리가 비어 있다는 뜻이면서 수요가 증명되지 않았다는 뜻이기도 하다.

## 오너가 정해야 할 것: 가장 먼저 Polar의 한국 개인 승인과 정산

가장 중요한 질문부터 적는다. **사업자등록이 없는 한국 개인이 Polar에서 승인받고 실제로 정산받을 수 있는가.** 승인까지 갔다는 블로그 경험담이 1건 있지만 정산을 받았다는 1인칭 기록은 Reddit, Threads, 블로그 어디에도 없고, Stripe Connect Express의 한국 개인 유형 지원과 그 정산의 과세 처리도 NOT VERIFIED다. 이것이 확인되지 않으면 결제 슬롯의 기본 경로를 정할 수 없다. 오너가 직접 소액으로 시험해 보는 것이 가장 빠른 확인 방법이다.

| 질문 | 왜 결정이 필요한가 |
|---|---|
| 한국 개인의 Polar 승인·정산을 누가, 언제 실제로 시험해 볼 것인가? | 위에 적은 대로 결제 슬롯 전체가 이 답에 달려 있다. 실패한다면 사업자등록을 전제로 한 국내 경로나 다른 MoR이 기본이 된다. |
| Revive의 입구를 복구와 디버깅이 아니라 살릴 가치 판정과 수요 확인으로 둘 것인가? | 두 플랫폼의 1인칭 기록에서 멈춤의 원인은 발견, 검증, 결제, 서류였다. 입구가 어디냐에 따라 제품의 첫인상과 개발 순서가 바뀐다. |
| 함께 배포할 스킬을 몇 개로 제한하고, 모델이 바뀔 때 재검증을 누가 할 것인가? | 번들 결정은 유지하되 Reddit의 근거는 작고 재검증되는 번들을 가리킨다. 재검증 절차가 없으면 번들은 몇 달 안에 부채가 된다. |
| 디버깅 슬롯에 제3자 스킬을 아예 넣지 않을 것인가, `diagnosing-bugs`를 선택 항목으로 넣을 것인가? | 직접 비교에서 효과는 없었지만 부작용이 가장 적었다. 넣는다면 선택 항목이라는 표시가 필요하다. |
| 사업자등록이 없는 사용자에게 계좌이체 우선을 안내할 것인가? | Threads의 조언은 계좌이체로 먼저 받아 보라는 것이지만, 같은 플랫폼의 엔지니어는 한국에서 매출을 받으려면 개인사업자가 필요하다고 적었다. 세무·법률 판단이 필요한 영역이라 Revive가 어디까지 말할지 정해야 한다. |
| 국내 원화 결제(PortOne, 토스페이먼츠, 페이플, 카카오페이)와 모바일 인앱결제, 앱인토스를 범위에 넣을 것인가? | 넣으면 사업자등록과 통신판매업 신고, PG 심사 대기까지 안내해야 한다. 빼면 한국 내수 프로젝트의 상당수가 대상에서 빠진다. |
| Impeccable의 설치 흔적 보고를 저장소와 대조한 뒤 권할 것인가? | 에이전트 수, 홈 디렉터리 폴더, 텔레메트리 기본값에 대한 보고가 단일 출처다. 권한다면 설치 전에 고지할 문구가 필요하다. |
| `unslop`, Hallmark, Ponytail, 한국산 SEO·GEO 스킬의 저장소를 확인할 것인가? | 넷 다 Revive의 상황과 맞아 보이지만 저장소 사실이 NOT VERIFIED다. 확인 결과에 따라 디자인과 론칭 슬롯이 다시 바뀔 수 있다. |
| 오너가 써 보고 마음에 들었던 taste-skill은 어느 버전인가? | 다이얼 방식의 v1과 현행 2.5.x는 전혀 다른 물건이다. 답에 따라 "v1 복사", "랜딩 단계의 선택 설치", "쓰지 않음"이 갈린다. |
| Revive는 유료로 팔거나 다른 라이선스로 배포할 것인가? | CC BY-SA와 CC BY-NC-SA 콘텐츠를 넣을 수 있는지와 Revive 자신의 라이선스 표기가 여기서 정해진다. |
| `vercel-labs/agent-skills`와 `portone-io/cli`의 라이선스를 업스트림에 문의할 것인가? | 문의하지 않으면 두 스킬은 런타임 설치로만 안내할 수 있다. |
| 벤더 MCP 설정을 Revive가 실어 보낼 것인가? | 원격 MCP는 실제 리소스를 바꿀 수 있고, `npx ...@latest` 방식은 고정되지 않은 코드를 실행한다. 필요할 때 사용자가 직접 추가하도록 안내하는 쪽이 위험이 낮다. |
| 한국어 문장 다듬기는 문체 프로필 방식으로 직접 쓸 것인가, 기존 휴머나이저를 권할 것인가? | Reddit의 합의는 개인 문체 프로필이고, 한국어 휴머나이저의 사용자 근거는 별 수뿐이다. |
| 약관·개인정보처리방침 초안 생성을 범위에 넣을 것인가? | PG 심사에서 약관과 환불규정이 실제로 요구된다. 넣는다면 직접 써야 하고 전문가 검토 고지가 따라붙어야 한다. |
| 후보를 실제 방치 프로젝트에 돌려 스킬 없는 Claude와 비교할 것인가? | 조사팀은 어떤 스킬도 직접 실행하지 않았다. Reddit의 비교 글들은 한 사람의 단발 측정이다. 창업자용 스킬 작성자가 쓴 `claude plugin eval` 방식이 본보기가 된다. |
| X와 YouTube, 영어권 Threads를 추가로 확인할 것인가? | 세 곳은 여전히 스니펫 수준이거나 다루지 못했다. 다만 Reddit과 한국어 Threads를 읽은 지금은 남은 구멍이 1차 때보다 작다. |

## 결론

Reddit과 Threads를 직접 읽기 전에는 근거의 구멍을 메우면 1차의 추천이 더 단단해질 것으로 기대했다. 실제로는 추천이 줄었다. 사용자들이 가장 신뢰하는 것은 스스로 쓴 좁은 절차, 스크립트로 판정하는 점검, 독립된 리뷰어, 저장된 상태였고, 유명한 팩의 디버깅·검증·감사 스킬은 직접 써 본 사람들에게서 좋은 평가를 받지 못했다. 오너가 정한 대로 추천 스킬을 함께 배포하되, 그 번들은 근거가 남은 몇 개로 줄이고 모델이 바뀔 때마다 다시 시험하는 부품으로 다루는 것이 이 근거와 맞는다.

제품의 중심도 옮겨 간다. 되살려야 할 것은 대개 코드가 아니라 멈춘 지점의 판단이다. 이 프로젝트를 살릴 가치가 있는지, 누가 돈을 낼지, 그 돈을 어떤 경로로 받을 수 있는지를 묻고 답을 기록하는 일이 먼저다. 한국에서는 마지막 질문이 사업자등록과 PG 심사, 그리고 아직 아무도 끝까지 확인해 주지 않은 Polar의 정산에 걸려 있다. 다음 한 걸음으로는 조사를 더 하는 것보다 오너가 Polar에서 소액 결제와 정산을 직접 시험하고, 방치된 프로젝트 하나에 후보 스킬과 맨 모델을 나란히 돌려 보는 것이 더 많은 것을 알려 준다.
