# 애미나이 ver 2 백업본 수정 보고서 (2026-11-24)

## 파일
| 파일 | 내용 |
|---|---|
| `original-live.html` | https://spontaneous-pasca-670937.netlify.app/ 에서 받은 원본 그대로(수정 안 함, Netlify가 끝에 붙이는 HUD 스크립트 포함) |
| `index.html` | 위 원본의 백업 사본에 작업한 결과물(Netlify HUD 스크립트 1줄만 뺌) |

라이브 사이트와 저장소 루트의 `index.html`(v1.26.0)은 건드리지 않았습니다.

## 1. 사진별 개별 프롬프트 · 합성용 사진
- 첨부 트레이의 사진을 누르면 창이 열림: **개별 프롬프트**, **합성용 사진 1장**, 그룹 지정, 🖌 마스크·☆ 기준·👤 얼굴 버튼, ◀ 이전 / 다음 ▶.
- 사진 #k에 보내는 지시 = **입력칸(공통) + 그룹 지시 + 개별 지시**. 공통 지시는 한 글자도 바꾸지 않고 앞에 둠. 합성용·그룹 참조 사진은 그 사진의 요청에만 함께 보냄.
- 적용 범위: 개별 편집 · 합성(사진 번호별 지시로 한 장에 반영) · 첨부 1장(글만 → 공통 지시에 붙임, 합성용 사진 → 대상+참조 편집) · 마스크 편집 · 언어 모델 대상별 계획 · Google/OpenAI/xAI/Qwen/MiniMax · Batch(50% 할인) · 대량 작업(20장 초과·폴더·압축, 파일 참조 사진도 개별 지시 가능) · 프롬프트 수정 후 저장&재생성 · 결과 1장 재생성 · 분석(🔍).
- ★ 기준·👤 얼굴 사진(편집하지 않는 사진)에 지시를 넣으면 쓰이지 않는다고 트레이와 창에서 안내. 사진마다 지시가 다르면 '일관성 강화'(첫 결과를 공통 기준으로)는 쓰지 않음(첫 사진의 개별 지시가 번지지 않게).

## 2. AI 분류 → 그룹 → 그룹별 프롬프트·참조 사진
- 트레이의 분류 기준 칸(예: "사람이 있는 사진끼리, 로봇이 있는 사진끼리")에 입력 → **🗂 AI로 분류**. 설정의 언어 모델(Gemini 4 Carbon · GPT-6.2 Astra · Grok 4.7 · MiniMax · HF Gemma 4)이 사진(긴 변 512px)을 보고 JSON 스키마(구조화 출력)로 그룹을 돌려줌. 한 번에 최대 20장(모델 한도가 작으면 그만큼), 두 번째 묶음부터 앞 그룹 이름을 함께 보내 같은 그룹으로 이어 나눔. 빠진·중복 번호는 앱이 검사.
- 그룹 칩을 누르면: **이름 변경**, **그룹 프롬프트**, **그룹 참조 사진 1장**, 사진을 눌러 그룹에 넣기·빼기, 그룹 삭제. 직접 그룹 만들기(＋ 그룹)도 가능. 다시 분류하면 같은 이름 그룹은 지시·참조 사진을 이어받음(잃는 것이 있으면 먼저 확인).
- 분류 요금은 사용액에 기록되고 완료 안내에 표시.
- **그룹별 내려받기**(추가 요청): 그룹 막대의 **📦 ZIP** / **📁 폴더에 저장**, 그룹 창의 **이 그룹만** ZIP·폴더.
  - 그룹마다 하위 폴더, 그룹 없는 사진은 `그룹 없음` 폴더. 같은 이름 그룹은 ` (2)`로 나눔. ZIP 이름 `애미나이_그룹별_날짜-시각.zip`(한 그룹은 `애미나이_그룹_그룹이름_…`).
  - 사진은 **원본 파일 그대로**(이름·바이트·수정 시각). 원본 파일이 없을 때(새로고침 뒤 프롬프트 수정 화면 등)만 앱이 저장한 사본을 담고 확장자를 실제 형식에 맞춤(안내 문구에 장수 표시).
  - 폴더 저장은 Chrome·Edge 데스크톱만(브라우저 폴더 선택 기능) — 휴대폰·Safari는 ZIP만 표시.
  - 대량 작업(20장 초과·폴더 첨부) 결과도 그룹이 있으면 같은 그룹 폴더로 나눠 저장.
  - 검증: ZIP 무결성 검사 통과, 4장(그룹 2 + 그룹 없음) 전부 원본과 바이트 동일, 폴더 업로드 24장(파일 참조 4장 포함) 24/24 원본 동일, 대량 작업 결과 ZIP `사람/` 12 · `로봇/` 12, 프롬프트 수정 화면(같은 탭 = 원본, 새로고침 뒤 = 사본 .webp), 폴더 저장(그룹별 하위 폴더), 휴대폰 화면 넘침 없음.

## 3. 휴대폰·태블릿
- 측정: iPhone SE·iPhone 13·Galaxy S9+·iPad 세로·가로 × 다크·라이트, 화면 10종(첫 화면·트레이·사진 창·그룹 창·결과·확대·설정·잔액·갤러리·사이드바). **가로 넘침 0건.**
- 수정: 휴대폰 상단 채팅방 제목이 "새 …"로 잘리던 문제, 트레이 사진(터치 화면 76px)·사진 위 버튼(26px 이상)·설정/잔액 창의 글자 링크·작은 버튼의 누르는 범위, 첨부 창 높이(단계 패널 유무에 따라), 사진별 지시 창은 휴대폰에서 아래에서 올라오는 시트·입력 글자 16px(iOS 자동 확대 방지), Esc로 맨 위 창 닫기(키보드 연결 태블릿).

## 4. 코드 점검
- 구문 검사 + ESLint(no-undef·no-unused-vars 등) 앱 스크립트 전체 **0건**. 도달 불가 선언 분석(자기 참조·상호 참조만 있는 선언 탐지, 심은 3건 검출 확인) **0건**.
- 정리: 읽히지 않는 데이터 필드 `replacedBy`(LEGACY_MODEL_KEY_MAP과 중복), `shortName` 2개 삭제. 사용하지 않는 CSS 클래스 0개(115개 전수 확인). 디버그 출력·주석 처리된 코드 없음.
- 버그 수정: 프롬프트 수정 중 사진을 지우면 👤 얼굴 참조 번호가 당겨지지 않던 문제.
- **기존 기능 회귀 없음**: 사진별 지시를 쓰지 않을 때 원본과 수정본이 보내는 API 요청을 4개 시나리오(개별 3장·합성 3장·1장·Batch)에서 비교 → **완전히 동일**.

## 5. API 키·HF 토큰 실시간 검증 · 호환성 검증
- 설정 창에서 키를 입력하면(입력이 멈추고 0.9초 뒤, 저장된 키는 창을 열 때) 과금 없는 조회만으로 확인: 키 상태 + **이 앱이 실제로 쓰는 모델 ID가 그 키로 열려 있는지**.
  - Google: `GET /v1beta/models`(목록, 다음 쪽까지) → 없으면 `models.get`으로 재확인
  - OpenAI: `GET /v1/models` → 없으면 `GET /v1/models/{id}`
  - xAI: `GET /v1/api-key`(차단·비활성·팀 차단) + `GET /v1/models`
  - HF: `GET /api/whoami-v2`(계정·PRO·ZeroGPU 할당량) + fine-grained 토큰의 'Make calls to Inference Providers' 권한 + 라우터의 언어 모델 서비스 상태 + Qwen·MiniMax Space 실행 상태
  - MiniMax: 구독 키(`token_plan/remains`, HTTP 200 + status_code 0) · API 키(`count_tokens`)
- 실측(2026-11-24, 실제 네트워크):
  - xAI(연결된 키): 키 유효, `grok-imagine-image-2.0` · `grok-imagine-image` · `grok-4.7` 3/3 사용 가능
  - OpenAI(이 환경의 키): HTTP 401 `expired_secret_key` → "키가 만료됐습니다"로 정확히 안내
  - Google·HF·MiniMax(일부러 틀린 키): 각각 400 `API key not valid`·401·401을 "키가 맞지 않거나 폐기됐습니다"로 안내
  - HF 공개 정보: `google/gemma-4-31B-it`(12곳)·`MiniMaxAI/MiniMax-M3.1-Flash`·`MiniMaxAI/MiniMax-M3` 서비스 중, `coder3101/gemma-4-31B-it-heretic`는 featherless-ai live, Qwen 2.1 Turbo·Qwen 2.1·MiniMax H3 Space 모두 RUNNING(zero-a10g)
- 공식 문서 대조(2026-11-24): Google 모델 코드 `gemini-nano-banana-2.1`·`gemini-3.1-flash-image`·`gemini-3.1-flash-lite-image`·`gemini-3-pro-image`·`gemini-2.5-flash-image`(종료 예정 가장 이른 날 2027-03-15)·`gemini-4-carbon`·`gemini-3.5-flash-lite`, `generateContent`·`models.list` 문서화 유지 / OpenAI `gpt-image-2.6-sunburst`·`2.6-flare`·`2.5-sunburst`·`2.5-flare`·`gpt-image-2`(Images API 모델 목록)·`gpt-6.2-astra`, 편집 JSON `images[].image_url`(데이터 URL)·최대 16장·`moderation` low/auto, Responses `reasoning.mode: "pro"`·`json_schema` / MiniMax `MiniMax-H3-Image(-Highspeed)`·`MiniMax-M3(.1-Flash)`, `api.minimax.io/v1`, Bearer.
- 호환성 수정: OpenAI 품질 `xhigh`·`max`는 공식 레퍼런스에 2.5 모델만 명시 → 다른 모델이 거부(400, 과금 없음)하면 `high`로 한 번 다시 보냄.
- 확인한 사실(변경 없음): MiniMax 응답의 CORS 허용 헤더에 `Authorization`은 있고 `x-api-key`는 없음 → 브라우저에서는 앱의 Bearer 방식만 가능.

## 확인하지 못한 것(사실대로)
- Google·OpenAI 실제 생성 호출: 이 환경에 Google 키가 없고 OpenAI 키는 만료. 생성 흐름은 응답을 흉내 낸 서버로 검증했고(요청 내용 전부 확인), 키 검증은 실제 서버의 오류 응답으로 확인.
- 실제 이미지 품질(모델이 지시를 얼마나 잘 따르는지)은 실제 키로 생성해 봐야 알 수 있음.
- OpenAI 2.6 모델의 `xhigh`·`max` 지원 여부, Google Batch(`batchGenerateContent`) 문서 위치는 공식 문서에서 확정하지 못함(앱은 거부 시 안내·재시도).
