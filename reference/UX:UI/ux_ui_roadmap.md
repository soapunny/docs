# Learning Preparation – Design Tools and Research

1. Design tools – Use collaboration-friendly tools like Figma, Sketch, and Adobe XD to build wireframes and prototypes.
2. User research – Gather requirements and pain points through interviews, surveys, and user journey mapping.
3. Inspiration and references – Analyze other designers’ work on sites like Behance, Dribbble, and Awwwards.

## <br/><br/>

# Web Development Skills Learning

### Step 1 – Basics of HTML/CSS and JavaScript

- HTML & CSS – Learn fundamentals like semantic tags, the box model, and layouts using Flexbox/Grid.
- JavaScript – Learn variables, functions, objects, arrays, and asynchronous programming basics.

### Step 2 – TypeScript

- TypeScript adds static typing to JavaScript, improving safety and maintainability. Strapi’s tech blog explains these benefits [oai_citation:0‡strapi.io](https://strapi.io/blog/benefits-of-typescript#:~:text=TypeScript%27s%20static%20typing%20helps%20teams,large%20projects%20involving%20multiple%20developers):
  - Static typing reduces unexpected bugs and makes code more predictable [oai_citation:1‡strapi.io](https://strapi.io/blog/benefits-of-typescript#:~:text=TypeScript%27s%20static%20typing%20helps%20teams,large%20projects%20involving%20multiple%20developers).
  - Enhanced IntelliSense improves productivity, and object‑oriented features help structure code [oai_citation:2‡strapi.io](https://strapi.io/blog/benefits-of-typescript#:~:text=TypeScript%27s%20static%20typing%20helps%20teams,scalable%20application%2C%20especially%20for%20large).
  - You can gradually introduce it into an existing JavaScript codebase [oai_citation:3‡strapi.io](https://strapi.io/blog/benefits-of-typescript#:~:text=TypeScript%27s%20static%20typing%20helps%20teams,large%20projects%20involving%20multiple%20developers).

### Step 3 – React Basics

- Understand React’s component structure, state management (useState, useEffect), and prop passing. Composition is key to building reusable UI components.

### Step 4 – Next.js

- Next.js boosts productivity with server-side rendering, static site generation, and file-based routing. In 2025, the App Router is the default and follows these best practices [oai_citation:4‡medium.com](https://medium.com/@GoutamSingha/next-js-best-practices-in-2025-build-faster-cleaner-scalable-apps-7efbad2c3820#:~:text=1.%20Use%20the%20,App%20Router%20FTW):
  - Use the `/app` directory – leverage server components by default and organize layouts, loading, and error handling in folders.
  - Separate folders – put reusable UI in `/components`, utilities in `/lib`, custom hooks in `/hooks`, and API logic in `/services` [oai_citation:5‡medium.com](https://medium.com/@GoutamSingha/next-js-best-practices-in-2025-build-faster-cleaner-scalable-apps-7efbad2c3820#:~:text=2,Structure).
  - Optimize performance – use the `next/image` component, dynamic imports, and choose appropriate rendering strategies (SSG, ISR, SSR) [oai_citation:6‡medium.com](https://medium.com/@GoutamSingha/next-js-best-practices-in-2025-build-faster-cleaner-scalable-apps-7efbad2c3820#:~:text=Next,tips%20go%20a%20long%20way).

### Step 5 – Tailwind CSS

- Tailwind is a utility‑class‑based CSS framework. The Next.js documentation describes how to use it [oai_citation:7‡nextjs.org](https://nextjs.org/docs/app/getting-started/css#:~:text=Tailwind%20CSS):

  1. Install – run `pnpm add -D tailwindcss @tailwindcss/postcss` to install Tailwind and the PostCSS plugin [oai_citation:8‡nextjs.org](https://nextjs.org/docs/app/getting-started/css#:~:text=Tailwind%20CSS).
  2. Configure PostCSS – register `@tailwindcss/postcss` in your `postcss.config.mjs` [oai_citation:9‡nextjs.org](https://nextjs.org/docs/app/getting-started/css#:~:text=Add%20the%20PostCSS%20plugin%20to,file).
  3. Import Tailwind in global CSS – add `@import 'tailwindcss';` to `app/globals.css` and import it in the root layout [oai_citation:10‡nextjs.org](https://nextjs.org/docs/app/getting-started/css#:~:text=Import%20Tailwind%20in%20your%20global,CSS%20file).
  4. Then you can style components using classes like `className="flex min-h-screen items-center …"` [oai_citation:11‡nextjs.org](https://nextjs.org/docs/app/getting-started/css#:~:text=Now%20you%20can%20start%20using,utility%20classes%20in%20your%20application).

- Next.js docs recommend using global styles only for base styles (the Tailwind reset) and using Tailwind utilities on components while applying CSS Modules for fine-grained styles when necessary [oai_citation:12‡nextjs.org](https://nextjs.org/docs/app/getting-started/css#:~:text=,custom%20scoped%20CSS%20when%20needed).

### Step 6 – Project Practice

- Gain experience through real projects:
  - Portfolio website – Build a personal site with Next.js, Tailwind, and TypeScript.
  - Blog/news site – Build a Markdown-based blog to experience static generation and design list and detail pages with clear hierarchy [oai_citation:13‡codeparrot.ai](https://codeparrot.ai/blogs/nextjs-and-tailwind-css-2025-guide-setup-tips-and-best-practices#:~:text=Step%205%3A%20Verifying%20the%20Setup).
  - Dashboard/admin panel – Practice building complex UIs with charts, tables, filters, etc.

### Additional Tips for Building Expertise

- User testing and feedback – Show prototypes to real users early to identify issues [oai_citation:14‡generalassemb.ly](https://generalassemb.ly/blog/ux-design-process-5-steps/#:~:text=Step%205%3A%20Test%20and%20learn).
- Accessibility and internationalization – Follow WCAG guidelines and design UIs that support multiple languages [oai_citation:15‡figma.com](https://www.figma.com/resource-library/ui-design-principles/#:~:text=Principle%205%3A%20Accessibility).
- Learning materials – Use courses from Interaction Design Foundation, General Assembly, Figma Academy, etc.
- Community participation – Share experiences on Reddit, GitHub, and open-source projects.

## <br/><br/>

# 학습 준비 – 디자인 도구와 리서치

1. 디자인 도구 – Figma, Sketch, Adobe XD 등 협업 가능한 도구를 이용해 와이어프레임과 프로토타입을 제작한다.
2. 사용자 리서치 – 인터뷰, 설문, 사용자 여정을 통해 요구 사항과 문제점을 수집한다.
3. 영감과 레퍼런스 – Behance, Dribbble, Awwwards 같은 사이트에서 다른 디자이너의 작품을 분석한다.

## <br/><br/>

# 웹 개발 기술 학습

### 1 단계 – HTML/CSS, JavaScript 기초

- HTML & CSS – 시맨틱 태그와 박스 모델, Flexbox/Grid 레이아웃 등 기본을 학습한다.
- JavaScript – 변수, 함수, 객체, 배열, 비동기 프로그래밍 등 기본 문법을 익힌다.

### 2 단계 – TypeScript

- TypeScript는 JavaScript에 정적 타입을 추가하여 안정성과 유지보수성을 높여준다. Strapi의 기술 블로그는 TypeScript의 장점을 다음과 같이 설명한다 ￼:
  - 정적 타이핑으로 예상하지 못한 버그를 줄이고 코드를 더 예측 가능하게 만든다.
  - IntelliSense 기능이 강화되어 개발 생산성을 높이고, 객체 지향적 기능은 코드 구조를 개선한다 ￼.
  - 기존 JavaScript 코드베이스에 점진적으로 도입할 수 있다 ￼.

### 3 단계 – React 기본

- React의 컴포넌트 구조, 상태 관리(useState, useEffect), props 전달 등을 이해한다. 컴포지션 모델은 재사용 가능한 UI 구성 요소를 만드는 데 중요하다.

### 4 단계 – Next.js

- Next.js는 서버 사이드 렌더링과 정적 생성, 파일 기반 라우팅 등 생산성을 높여준다. 2025년 현재는 App Router가 기본이며 다음과 같은 베스트 프랙티스를 따른다 ￼:
  - /app 디렉터리 사용 – 서버 컴포넌트를 기본으로 사용하며 레이아웃, 로딩, 에러 처리 등을 폴더 구조로 구성한다.
  - 폴더 구조 분리 – /components에는 재사용 UI, /lib에는 유틸리티, /hooks에는 커스텀 훅, /services에는 API 호출 로직을 분리해 유지보수성을 높인다 ￼.
  - 성능 최적화 – next/image 컴포넌트로 이미지 최적화하고, 동적 import와 적절한 렌더링 전략(SSG, ISR, SSR)을 선택한다 ￼.

### 5 단계 – Tailwind CSS

- Tailwind는 유틸리티 클래스 기반의 CSS 프레임워크다. Next.js 공식 문서는 Tailwind 사용을 다음과 같이 설명한다 ￼:

  1. 설치 – pnpm add -D tailwindcss @tailwindcss/postcss로 Tailwind와 PostCSS 플러그인을 설치한다 ￼.
  2. PostCSS 구성 – postcss.config.mjs에 @tailwindcss/postcss 플러그인을 등록한다 ￼.
  3. 글로벌 CSS에 Tailwind 가져오기 – app/globals.css에서 @import 'tailwindcss';를 추가하고 루트 레이아웃에서 불러온다 ￼.
  4. 그 후에는 className="flex min-h-screen items-center …"처럼 Tailwind 클래스를 사용해 스타일링할 수 있다 ￼.

- Next.js 문서는 전역 스타일은 베이스 스타일(Tailwind reset)에만 사용하고, 구성 요소마다 Tailwind 유틸리티를 사용하되 필요할 때 CSS Modules로 세밀한 스타일을 적용하라고 권장한다 ￼.

### 6 단계 – 프로젝트 실습

- 실제 프로젝트를 통해 경험을 쌓아야 한다.
  - 포트폴리오 웹사이트 – 자신의 소개와 프로젝트를 보여주는 사이트를 Next.js + Tailwind + TypeScript로 구현한다.
  - 블로그/뉴스 사이트 – 마크다운 기반 블로그를 만들어 정적 생성을 경험하고, 글 목록과 상세 페이지의 시각적 계층을 설계해 본다 ￼.
  - 대시보드/관리자 패널 – 차트, 테이블, 필터 등 복잡한 UI를 구성하는 연습을 한다.

### 전문성을 높이는 추가 팁

- 사용자 테스트와 피드백 – 초기에 간단한 프로토타입이라도 실제 사용자에게 보여주고 문제점을 발견해야 한다 ￼.
- 접근성과 국제화 – WCAG 지침을 준수하고 다국어를 지원하는 UI를 설계한다 ￼.
- 학습 자료 – Interaction Design Foundation, General Assembly의 강의, Figma Academy 등을 활용해 이론과 실습을 병행한다.
- 커뮤니티 참여 – Reddit, GitHub, 오픈 소스 프로젝트에 기여하여 경험을 공유한다.
