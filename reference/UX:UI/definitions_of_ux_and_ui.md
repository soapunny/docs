# Definitions of UX and UI

## UX (User Experience)

UX is the **overall experience** a user has while using a product or service—from start to finish.

Examples of UX outcomes:

- “Easy to find” / “Confusing”
- “Fast” / “Frustrating”
- “Trustworthy” / “Uncertain”
- “I want to use it again” / “I never want to use it again”

## UI (User Interface)

UI is the **visual and interactive layer** users directly see and touch on the screen.

Examples of UI elements:

- Buttons, input fields
- Colors, typography (fonts)
- Icons, layout, spacing
- Animations, component design

**In one line:**

- UX = “Is the experience well-designed?”
- UI = “Is the screen clear and easy to interact with?”

UI is a part of UX (**UX ⊃ UI**).

---

# UX Fundamentals

## 1. Problem Definition

- Clearly define the user’s pain points and goals.
- Example: “I want to finish price comparison within 30 seconds.”

## 2. User Understanding

- Identify persona (who), context (when/where), motivation, and anxiety points.
- Validate with interviews, surveys, and data (bounce rate, conversion rate, etc.).

## 3. Information Architecture (IA)

- Make sure menus/categories/tabs feel intuitive.
- Example: “Deals / Gas / Grocery / Profile”

## 4. User Flow

- Ensure the path to the goal is short and natural.
- Example: Home → Search → Detail → Save (or Report)

## 5. Wireframes & Prototypes

- Wireframes = screen structure (skeleton).
- Prototypes = clickable mockups for testing.

## 6. Usability

- Easy to learn, prevents mistakes, clear feedback, undo possible.
- Key question: “Can a first-time user succeed immediately?”

## 7. Validation (Testing)

- Even 5 users can reveal major usability issues.
- Observe real scenarios: “Where do users get stuck?”

---

# UI Fundamentals

## 1. Layout & Visual Hierarchy

- Make important things stand out first using size, weight, color, and spacing.

## 2. Typography

- Improve readability with font size, line height, weight, and contrast.

## 3. Color & Contrast

- Use meaningful colors (success/warning/error) and ensure accessibility contrast.

## 4. Component Consistency

- Standardize rules for buttons, inputs, cards, etc.
- Design systems (component-based systems like **shadcn/ui**) help a lot here.

## 5. State Design

- Design all states: default, hover, pressed, disabled, loading, error.
- When UI “talks back” with clear states, UX improves dramatically.

---

# 6 Core Principles Where UX and UI Meet

- **Clarity:** Make it obvious what to do right now.
- **Consistency:** Same action → same result and look.
- **Feedback:** Show responses (loading, toast, state changes).
- **Error Prevention:** Make mistakes harder (format rules, previews, confirmations).
- **Efficiency:** Minimize steps to reach the goal.
- **Accessibility:** Consider diverse needs (keyboard, contrast, readable fonts).

---

# Quick Examples

## When UI looks good but UX is bad

- The screen is pretty, but users can’t find the “Report a price” button → bad experience.

## When UX is good but UI is weak

- The flow is great, but the text is too small and contrast is poor → tiring to use, so the experience becomes bad.

# UX / UI 쉽게 이해하기 (중학생 버전)

## 1) UX랑 UI 한 문장으로

### UI (User Interface) = “화면 생김새 + 조작하는 버튼들”

- 버튼, 글씨, 색, 아이콘, 메뉴, 입력칸, 카드, 여백, 애니메이션 등
- **눈에 보이고 손으로 누르는 것들**

### UX (User Experience) = “쓰면서 느끼는 전체 경험”

- “쉽다/어렵다”, “빠르다/느리다”, “편하다/짜증난다”, “믿음 간다/불안하다”
- **사용하면서 생기는 기분 + 효율**

✅ **비유로 이해하기**

- UI = 자동차의 **운전대/버튼/계기판**
- UX = 자동차를 운전할 때 느끼는 **편함/안전함/스트레스**

> UI가 예뻐도 UX가 나쁠 수 있고, UX가 좋아도 UI가 별로면 쓰기 힘들어질 수 있어요.

---

## 2) UX가 왜 중요할까? (예시)

### 예시 A: 편의점 키오스크

- UI는 깔끔하고 예쁜데
- “취소” 버튼이 너무 작고 구석에 숨어 있음  
  → 사용자가 당황하고 짜증남  
  → **UX 나쁨**

### 예시 B: 배달앱

- 주소 입력 과정이 너무 복잡해서 단계가 많음  
  → “귀찮아” 하고 앱을 꺼버림  
  → **UX 나쁨(이탈)**

---

## 3) UX의 기초 구성요소 7가지 (쉽게)

### 1) 문제 정의 (무슨 문제를 풀 건지)

- 사용자가 어떤 불편을 겪는지, 목표가 뭔지 정하는 단계

**예시**

- “마트 가격 비교를 하려면 카톡방/전단지/말로 듣기 등 너무 번거롭다”
- 목표: “30초 안에 최저가를 찾게 해주자”

---

### 2) 사용자 이해 (누가 쓰는지 알기)

- 사용자(누가), 상황(언제/어디서), 동기/불안 요소를 파악하기

**예시**

- 유학생/이민자: 영어가 부담될 수 있음 → 쉬운 단어, 한글 지원
- 바쁜 사람: 단계가 많으면 중간에 나감 → 핵심 기능을 빨리 접근하게

---

### 3) 정보 구조(IA) (메뉴/탭 정리)

- 앱을 “책장”이라고 생각하면, IA는 “책을 어디에 꽂을지” 정하는 것

**좋은 예**

- Deals / Gas / Grocery / Profile  
  → 딱 보면 “어디에 뭐가 있는지” 감이 옴

**나쁜 예**

- 생활정보 / 정보공유 / 꿀팁 / 생활꿀팁 / 도움  
  → 비슷한 메뉴가 많아서 “어디 들어가야 하지?” 혼란

---

### 4) 사용자 흐름(User Flow) (목표까지 가는 길)

- 사용자가 목표를 이루는 길이 **짧고 자연스러운지** 확인하기

**예시: “가격 확인” 흐름**

- 홈 → 카테고리(마트) → 품목 검색(계란) → 최저가 보기

**나쁜 흐름 예**

- 홈 → 로그인 강제 → 약관 동의 여러 번 → 프로필 설정 → 검색 가능  
  → 중간에 사람들이 많이 나감

---

### 5) 와이어프레임 & 프로토타입 (스케치 → 눌러보는 시제품)

- 와이어프레임: 화면을 “연필로 그린 설계도”
- 프로토타입: 실제처럼 “눌러지는 시제품”

**예시**

- 버튼 위치/메뉴 구조를 먼저 대충 잡아보고
- 사람들이 헤매면 빠르게 수정

---

### 6) 사용성(Usability) (처음 써도 쉬운가?)

- 처음 쓰는 사람도 바로 할 수 있어야 함

**좋은 예**

- 회원가입 없이도 둘러보기 가능
- 입력 실수하면 친절하게 안내
  - “가격은 숫자만 입력해주세요”

---

### 7) 검증(테스트) (실제로 써보게 해서 문제 찾기)

- 만든 사람은 “당연히 보이는데?”라고 생각하지만
- 다른 사람은 “어디 있는지 모르겠는데?”라고 느낄 수 있음

**예시**

- 5명만 테스트해도 “막히는 지점”이 많이 나옴
- 진짜 사용 상황에서 관찰: “어디서 멈추는지”

---

## 4) UI의 기초 구성요소 5가지 (쉽게)

### 1) 레이아웃 & 우선순위(Visual Hierarchy)

- 중요한 게 먼저 보이게 만드는 것 (크기/굵기/색/여백)

**예시**

- “최저가 보기”가 가장 중요하면  
  → 버튼을 크게, 눈에 띄는 위치에

**나쁜 예**

- 중요한 버튼이 작고 회색이고 아래 구석에 있음  
  → 사람들이 못 봄

---

### 2) 글씨(타이포그래피)

- 글씨가 읽기 편해야 함

**예시**

- 글씨가 너무 작으면 눈이 아픔
- 줄 간격이 너무 좁으면 답답함

---

### 3) 색과 대비

- 색은 예쁘기만 한 게 아니라 “의미”를 전달함

**예시**

- 빨강: 삭제/위험/오류
- 초록: 성공/완료
- 회색: 비활성(지금 못 누름)

**나쁜 예**

- 버튼 색이 배경과 비슷해서 안 보임

---

### 4) 컴포넌트 일관성 (규칙 통일)

- 버튼/입력창/카드가 화면마다 다르면 사용자 혼란

**좋은 예**

- “저장” 버튼은 어디서든 같은 모양/색/크기  
  → 사용자가 빨리 익힘

**나쁜 예**

- A화면 저장 버튼은 파랑
- B화면 저장 버튼은 초록
- C화면 저장 버튼은 테두리만 있음  
  → “이게 같은 기능 맞아?” 혼란

---

### 5) 상태 디자인 (눌림/로딩/에러 등)

- 눌렀는데 반응이 없으면 사용자는 불안해함  
  → 다시 누름(연타) → 오류/중복 결제/중복 요청 위험

**좋은 예**

- 버튼 누르면 로딩 표시
- 완료되면 “저장 완료!” 메시지
- 실패하면 “네트워크 오류. 다시 시도해주세요.”

---

## 5) UX + UI가 만나는 핵심 원칙 6개 (쉬운 말)

- **명확성:** 지금 뭘 해야 하는지 한눈에
- **일관성:** 같은 행동이면 항상 같은 결과/모양
- **피드백:** 눌렀으면 반응(로딩, 토스트, 상태 변화)
- **오류 예방:** 실수하기 어렵게(숫자만 입력, 미리보기, 확인)
- **효율:** 목표까지 단계 줄이기
- **접근성:** 누구나 보기/누르기 편하게(글씨 크기, 대비, 키보드 사용 등)

---

## 6) 초간단 정리

- **UI = 보이는 것(디자인 부품)**
- **UX = 사용해보고 느끼는 전체 경험**
- 좋은 UI는 좋은 UX를 돕고,
- 좋은 UX는 “다시 쓰고 싶다”를 만들어요.
