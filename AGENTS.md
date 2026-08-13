# Beyond Diet Legal Docs Guide

- 회사 서비스의 공개 privacy policy, terms, account-deletion 안내를 관리하는 정적 법적 문서 저장소다.
- 요청한 문서와 직접 연결된 문서만 읽는다. 정책 의미, service/contact identity, effective date, 실제 앱·backend의 data lifecycle을 서로 일치시킨다.
- 법률 검토를 받지 않은 내용을 법률 자문이나 확정된 준수 사실로 표현하지 않는다. 번역은 의무·권리·삭제 범위를 바꾸지 않는다.
- 정책 변경에는 관련 link와 정적 문서 형식만 확인한다. 앱·backend 구현 검증이 없으면 실제 data deletion이 구현됐다고 주장하지 않는다.
- 관련 없는 기존 변경을 보존하고 company credential·개인정보를 문서에 넣지 않는다. 유료 법률·번역 서비스는 별도 승인받는다.

# Product Design review gate

- 사용자에게 보이는 화면·기능·흐름을 만들거나 바꾸기 전에는 `@product-design`으로 기획과 목표 화면 검수를 제품 코드보다 먼저 수행한다.
- 검수 작업대는 실제 제품과 분리된 한 페이지로 만들고 `목차 | 만들어갈 UI | 실제 제품 UI | 기획 의도`를 동시에 보여 준다. 전체 목차를 처음부터 제공하되 화면은 하나씩 검토·승인하며, 목록만 만든 항목을 완성으로 보고하지 않는다.
- 비교 근거는 실제 제품 캡처나 검증된 렌더만 사용한다. 목표 시각물이 없으면 Product Design의 내장 Image Gen(`GPT Image 2`)으로 독립된 후보 세 개를 만들어 작업대 안에서 선택하게 하며, 이미지 링크나 문서만 전달하고 끝내지 않는다. 개인 이메일 계정이나 별도 API key를 요구하지 않는다.
- 만들어갈 UI와 실제 제품 UI frame은 창 너비에 따라 늘어나지 않게 하고 원본 viewport와 종횡비를 유지한다. `contain` 방식으로 전체를 보여 주며 crop·cover·늘어짐·잘림을 허용하지 않는다.
- 우측 기획 의도는 실제 텍스트로 제공하고 핵심 제목 21px, 주 설명 16px, 세부 본문 15px, 보조 설명 14px 이상을 기본으로 한다. 화면에 맞추기 위해 핵심 문장을 작은 글자로 줄이지 않는다.
- frontend와 backend가 별도 Git이면 각 Git 루트에 이 계약을 둔다. frontend는 검수 작업대를 production bundle과 분리하고, backend는 사용자에게 보이는 계약을 구현하기 전에 연결된 검수 화면의 승인 상태를 확인한다.
- 검수 작업대의 목차·비교 frame·기획 의도 패널은 실제 제품 UI에 포함하지 않는다. 사용자가 선택한 목표 화면과 필요한 제품 동작만 구현한다.
