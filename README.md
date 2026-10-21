# 🚀 MadeCareer
### *Your AI-Powered Personal Career Intelligence Assistant*

**MadeCareer** is a full-stack SaaS platform designed to bridge the gap between academic learning and professional employment. By leveraging Artificial Intelligence, it provides a centralized ecosystem for students and early professionals to track, analyze, and improve their job readiness in real-time.

---

## 🌟 Core Features

- **📊 Dynamic Job Readiness Score:** A global metric that updates in real-time based on your resume strength, skill acquisitions, and mock interview performance.
- **🔍 Smart Resume Analyzer & ATS Scorer:** Instant feedback on formatting, keyword density, and compatibility with industry-standard Applicant Tracking Systems.
- **🛤 AI-Generated Roadmaps:** Personalized, step-by-step career pathways tailored to your target roles.
- **🤖 AI Career Coach & Interview Simulator:** 24/7 interactive guidance and a simulator to practice role-specific technical and behavioral questions.
- **🧩 Skill Gap Analysis:** Compare your current profile against specific Job Descriptions (JD) to identify missing competencies.

---

## 🛠 Tech Stack

- **Frontend:** React.js, Tailwind CSS, Framer Motion
- **Backend:** Node.js, Express.js
- **Database:** MongoDB / PostgreSQL
- **AI/ML:** OpenAI API, LangChain, Python
- **Tools:** Figma, Git, Vercel/Render

### Frontend

- React 18+ — Modern React with hooks and concurrent features
- TypeScript 5 — Full type safety across the application
- Vite 5 — Fast build tool and dev server with HMR
- Tailwind CSS 3 — Utility-first CSS framework
- shadcn/ui — Beautiful, accessible component library
- React Router DOM — Client-side routing
- Framer Motion — Smooth animations and transitions

### Backend

- Node.js API — Simple health check and utilities
- TypeScript — Type-safe backend development

### Development Tools

- ESLint 9 — Code linting
- Prettier — Code formatting
- Vitest — Fast unit testing
- TypeScript ESLint — TypeScript-specific linting

> **Note:** SSR support with vite-plugin-ssr has been temporarily removed due to compatibility issues with the directory structure. This can be re-added later when the plugin is updated or replaced with a more stable alternative.

---

## 📁 Project Structure

```text
v8-app-template/
├── src/
│   ├── components/
│   │   ├── ui/
│   │   └── Spinner.tsx
│   ├── layouts/
│   │   ├── RootLayout.tsx
│   │   ├── Website.tsx
│   │   ├── Dashboard.tsx
│   │   ├── RootLayout.md
│   │   ├── Website.md
│   │   └── parts/
│   │       ├── Header.tsx
│   │       └── Footer.tsx
│   ├── pages/
│   │   ├── index.tsx
│   │   └── _404.tsx
│   ├── lib/
│   │   ├── utils.ts
│   │   └── api-client.ts
│   ├── api/
│   │   └── health.ts
│   ├── styles/
│   │   └── globals.css
│   ├── test/
│   │   └── setup.ts
│   ├── App.tsx
│   ├── main.tsx
│   ├── router.ts
│   └── routes.tsx
├── dev-tools/
├── source-mapper/
├── public/
└── scripts/
```

---

## 📜 Available Scripts

- `npm run dev` — Start development server with hot reload
- `npm run build` — Build for production
- `npm run preview` — Preview production build locally
- `npm run test` — Run Vitest unit tests
- `npm run lint` — Run ESLint code linting
- `npm run type-check` — Run TypeScript type checking
- `npm run setup` — Initialize project with dependencies

---

## 🎨 UI Components

This template includes shadcn/ui components that are:

- **Accessible** — Built with Radix UI primitives
- **Customizable** — Easy to modify and extend
- **Consistent** — Design system with CSS variables
- **Copy-paste friendly** — Own your components

The template includes 40+ pre-configured shadcn/ui components:

- **Layout:** Card, Separator, Tabs, Sheet, Dialog
- **Forms:** Button, Input, Textarea, Select, Checkbox, Switch
- **Navigation:** Navigation Menu, Breadcrumb, Pagination
- **Feedback:** Alert, Badge, Progress, Skeleton, Sonner
- **Data Display:** Table, Avatar, Calendar, Hover Card
- **Overlays:** Popover, Tooltip, Alert Dialog, Drawer
- **Interactive:** Accordion, Collapsible, Command, Context Menu

To add new components:

```bash
npx shadcn-ui@latest add component-name
```

---

## 🧠 AI Integration

### Component Introspection

The custom source-mapper plugin adds metadata to components in development:

```html
<div
  data-source-file="/src/components/Button.tsx"
  data-source-line="15"
  data-source-component="Button"
>
  Click Me
</div>
```

### Development Mode Integration

The dev-tools package provides:

- **Element selection:** Click to identify components
- **Live editing:** Modify component props in real-time
- **Source mapping:** Navigate directly to component source
- **AI integration:** Enhanced context for AI development tools

### AI-Friendly Patterns

- **Consistent naming:** PascalCase components, camelCase hooks
- **Clear file structure:** Logical separation of concerns
- **Type-first approach:** Comprehensive TypeScript types
- **Standard patterns:** CRUD operations, form handling, error boundaries

---

## 🗃️ API & Layouts

### API Routes

The template includes:

- `GET /api/health` — Health check endpoint
- Extensible API client setup in `src/lib/api-client.ts`

### Layout System

**RootLayout Pattern (Recommended for multi-page sites)**

Configure header and footer once in `App.tsx`, applying them to all pages:

```tsx
const headerConfig = {
  logo: { text: "MadeCareer" },
  navItems: [
    { href: "/", label: "Home" },
    { href: "/about", label: "About" },
  ],
};
```

Pages become simple content components:

```tsx
export default function HomePage() {
  return <div>Your content here</div>;
}
```

**Available Layouts:**

- **RootLayout** (`src/layouts/RootLayout.tsx`) — Centralized header/footer wrapper
- **Website** (`src/layouts/Website.tsx`) — Structural container used by RootLayout
- **Dashboard** (`src/layouts/Dashboard.tsx`) — Admin panels and dashboards

See `src/layouts/*.md` for detailed usage documentation.

---

## 🧪 Testing

Run tests with:

```bash
npm run test
```

The template includes:

- **Vitest** — Fast unit testing framework
- **React Testing Library** — Component testing utilities
- **Jest DOM** — Custom Jest matchers

---

## 📦 Deployment

### Build for production

```bash
npm run build
```

### Deploy options

- **Vercel/Netlify** — Frontend deployment
- **Railway/Render** — Full-stack deployment
- **Docker** — Containerized deployment

---

## 🔧 Configuration

### Environment Variables

Copy `env.example` to `.env` and configure:

```env
VITE_APP_NAME=MadeCareer
VITE_API_URL=http://localhost:5173/api
NODE_ENV=development
PORT=5173
```

---

## 🔌 Custom Plugins

- **Source Mapper Plugin:** Adds component introspection for AI tools.
- **Dev Tools Plugin:** Enables development mode enhancements.
- **Fullstory Integration:** Optional user analytics, configurable as needed.

Configure in `vite.config.ts`:

```typescript
import { defineConfig } from "vite";
import { sourceMapperPlugin } from "./source-mapper";
import { devToolsPlugin } from "./dev-tools";

export default defineConfig({
  plugins: [sourceMapperPlugin(), devToolsPlugin()],
});
```

---

## 🎯 Best Practices

### Component Architecture

- Keep components small and focused
- Use composition over inheritance
- Extract reusable logic into hooks
- Prefer function components with hooks

### State Management

- Keep local state in components with useState/useReducer
- Use React Context for app-wide state, such as theme and authentication
- Consider Zustand or Redux Toolkit for complex state
- Leverage layout props for shared configuration

### Layout Usage

- Use RootLayout for multi-page sites
- Configure header and footer once
- Keep pages focused on content
- Follow layout documentation
- Avoid duplicating header/footer configuration

---

## 🤝 Contributing

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Add tests if needed.
5. Run linting and tests.
6. Submit a pull request.

---

## 📄 License

MIT License — refer to the project's license file for details.

## 🙏 Acknowledgments

Built with amazing open-source tools:

- [Vite](https://vitejs.dev/)
- [React](https://react.dev/)
- [shadcn/ui](https://ui.shadcn.com/)
- [Tailwind CSS](https://tailwindcss.com/)
- [TypeScript](https://www.typescriptlang.org/)
- [Framer Motion](https://www.framer.com/motion/)
- [Vitest](https://vitest.dev/)

---

**Welcome to MadeCareer — Build skills. Shape your career. 🚀**
