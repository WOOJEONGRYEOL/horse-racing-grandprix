# 경마 그랑프리 — 수익화 가이드

코드에는 이미 수익화 인프라가 준비되어 있습니다. `index.html`의 `MONETIZE` 설정에
값만 채우면 활성화됩니다 (비워두면 게임에 아무것도 표시되지 않음).

```js
const MONETIZE={
  adsenseClient:'',   // 'ca-pub-XXXXXXXXXXXXXXXX'
  adSlot:'',          // 광고 단위 슬롯 ID
  supportUrl:'',      // 'https://ko-fi.com/yourname' 등
};
```

## 현실적인 수익 경로 (추천 순)

### 1. 웹게임 포털 제출 — 가장 현실적 ★
직접 트래픽을 모으는 것보다, 이미 유저가 있는 포털에 게임을 올리는 것이
웹게임 수익의 정석입니다. 광고 수익을 포털과 나누는 구조.

| 포털 | 특징 | 제출 |
|---|---|---|
| **CrazyGames** | 심사 통과 시 광고 수익 셰어. 규모 큼 | developer.crazygames.com |
| **Poki** | 품질 기준 높음, 수익도 좋음 | developers.poki.com |
| **itch.io** | 심사 없음, 즉시 업로드. 후원/유료 판매 설정 가능 | itch.io → Upload new project |
| **GameDistribution** | 여러 사이트에 배포되는 네트워크 | gamedistribution.com |

- 제출용 zip: `horse-racing-grandprix.zip` (이 폴더에 생성됨, index.html이 루트)
- itch.io 설정: HTML 게임 → "This file will be played in the browser" 체크,
  Viewport 1160×780, Mobile friendly 체크
- 소개문 (복사해서 사용):
  - KR: "배당률을 읽고 마권을 사세요! 실시간 중계, 낙마 변수, 사진판독까지 —
    레트로 아케이드 경마 베팅 게임. 1인/2인, 한국어/English 지원."
  - EN: "Read the odds, buy your ticket! Retro arcade horse racing with live
    broadcast, photo finishes and upsets. 1–2 players, EN/KR."
- 참고: CrazyGames/Poki는 자체 광고 SDK 연동을 요구할 수 있음 (통과 후 안내됨.
  연동 작업이 필요하면 그때 코드 수정을 도와드릴 수 있음)

### 2. Google AdSense — 조건부
- **github.io 서브도메인은 AdSense 사이트로 등록 불가** → 커스텀 도메인 필요
  (연 1~2만원, 예: Cloudflare/가비아에서 구매 후 GitHub Pages에 연결)
- 절차: 도메인 구매 → Pages에 커스텀 도메인 설정 → adsense.google.com 가입 →
  사이트 등록·심사 → 승인 후 게시자 ID(ca-pub-…)와 광고 단위 슬롯 ID 발급 →
  `MONETIZE`에 입력 → 커밋/푸시하면 끝 (결과 화면 하단에 반응형 광고 표시)
- **주의**: 이 게임은 "모의 도박(simulated gambling)" 콘텐츠로 분류될 수 있어
  일부 지역에서 광고 제한이 걸리거나 심사가 까다로울 수 있음.

### 3. 후원 버튼 — 즉시 가능
- Ko-fi(ko-fi.com) 또는 Buy Me a Coffee(buymeacoffee.com) 가입 (무료, 5분)
- 받은 페이지 주소를 `MONETIZE.supportUrl`에 입력하면
  시작 화면과 결과 화면에 "☕ 개발자 후원" 버튼이 자동 표시됨

## 시작하기 전에 확인할 것
- **오디오 라이선스**: 함성/팡파르/종소리는 유튜브 "저작권 무료" 영상에서
  추출했음. 수익화(상업적 이용) 시에는 해당 영상의 라이선스가 상업적 이용을
  허용하는지 한 번 더 확인 권장. 문제 소지가 있으면 freesound.org(CC0),
  pixabay.com/sound-effects 등에서 확실한 CC0 음원으로 교체 가능.
- **사진**: hero.jpg는 Pexels 사진 — Pexels 라이선스는 상업적 이용 허용.

## 다음 단계
계정 가입·도메인 구매·포털 제출은 본인 계정으로 직접 해야 합니다.
완료 후 발급받은 ID/URL을 알려주면 코드 연동을 마무리해 드립니다.
