# Modern Web Development: 6-Week Intensive Learning Plan

## Document Purpose

This document serves as:
1. **Structured Curriculum** - Complete 6-week learning roadmap
2. **Teaching Guidelines** - Instructions for Claude when providing guidance
3. **Progress Tracking** - Daily/weekly milestone checkpoints
4. **Reference Guide** - Resources, comparisons, and best practices

Last Updated: 2025-11-04

---

## Learner Profile

**Background & Experience:**
- **Languages:** Proficient in Rust and Python
- **Mobile:** Experience with Flutter/Dart
- **Architecture:** Built backend, middleware, and mobile applications
- **APIs:** Extensive experience with gRPC APIs, REST, and third-party API integration (text generation, image generation, audio)
- **Databases:** Strong PostgreSQL and SQL knowledge
- **DevOps:** Experience with Docker, Kubernetes, DigitalOcean managed services, S3-compatible storage

**Learning Style:**
- **Project-based learning** - Jump into building, learn theory as needed
- **Quick learner** - Can dedicate intensive time and effort
- **Hands-on experimentation** - Prefer doing over reading

**Time Commitment:**
- **4-6 hours per day** (intensive schedule)
- **30-40 hours per week**
- **180-240 total hours over 6 weeks**

**Development Environment:**
- **Editor:** VS Code
- **OS:** macOS
- **Tools:** Git, Docker, command-line proficiency

**Goals:**
- Build full-stack web applications
- Deploy production-ready applications
- Master modern web development stack (2025 best practices)
- Create desktop and mobile-capable web apps

---

## Technology Stack

### Primary Stack

**Frontend:**
- **HTML5** - Semantic structure
- **CSS3** - Via Tailwind CSS (utility-first approach)
- **TypeScript** - Type-safe JavaScript
- **React 18+** - Component-based UI library
- **React Router** - Client-side routing
- **React Hook Form + Zod** - Form handling and validation
- **Vite** - Build tool and dev server

**Backend:**
- **Rust** - Systems programming language
- **Axum** - Modern async web framework
- **PostgreSQL** - Relational database
- **sqlx** - Async SQL toolkit with compile-time query checking
- **Tower** - Middleware and service abstractions
- **serde** - Serialization/deserialization

**Real-Time:**
- **WebSockets** - Axum WebSocket support + React client
- **Real-time state synchronization** - Custom implementation

**Authentication:**
- **Supabase Auth** - Built-in authentication with social providers
- **JWT** - Token-based authentication (handled by Supabase)
- **Row Level Security (RLS)** - PostgreSQL-native access control

**Deployment:**
- **Vercel** - Frontend hosting (React apps)
- **Railway** or **Fly.io** - Backend hosting (Rust services)
- **Supabase** - Managed PostgreSQL + Auth + Storage
- **Cloudflare R2** - S3-compatible object storage (alternative)

**Development Tools:**
- **npm/pnpm** - Package management
- **cargo** - Rust package manager
- **Git** - Version control
- **Docker** - Containerization
- **VS Code Extensions** - ESLint, Prettier, rust-analyzer, Tailwind IntelliSense

### Why This Stack?

**Leverages Existing Skills:**
- Rust expertise → high-performance backend
- Python/backend experience → faster API development understanding
- Flutter component model → easier React transition
- SQL knowledge → PostgreSQL mastery

**Modern & Marketable (2025):**
- React is industry standard (used by Meta, Netflix, Airbnb)
- TypeScript adoption at 92%+ in JavaScript ecosystem
- Rust web development is growing rapidly
- Full-stack capability in high demand

**Unique Differentiator:**
- Rust + Web is rare and valuable
- Performance-critical web applications
- Type safety across entire stack
- Can build desktop apps with Tauri (Rust + Web)

---

## Capstone Project: Collaborative Worldbuilding Platform

### Vision

An application that allows multiple participants to collaborate in real-time on creating imaginary worlds, then generate and experience stories together.

**Dream Use Case:**
A group of friends at a gathering collaborates to define a universe (cyberpunk, fantasy, post-apocalyptic), create characters and relationships, develop plots, then play a game by creating a collaborative story. The system narrates the story with AI-generated text, illustrations, and text-to-speech.

### Core Features (6-Week MVP)

**1. User Management**
- Authentication via Supabase Auth (Google/Apple/GitHub login)
- User profiles
- Access control and permissions

**2. Universe Creation**
- Define universe settings (genre, magic system, technology level, societal rules)
- Add themes, rules, and world-building elements
- Rich text descriptions with collaborative editing

**3. Character Management**
- Create characters with attributes (name, description, role, background)
- Define character relationships (family, friends, rivals, etc.)
- Relationship visualization (graph/tree)
- Character illustrations (AI-generated)

**4. Plot Development**
- Create plot outlines and story arcs
- Link characters to plots
- Collaborative plot editing

**5. Real-Time Collaboration**
- Multiple users editing simultaneously
- Live presence indicators (who's online)
- Real-time synchronization of changes
- WebSocket-based communication

**6. Story Generation**
- AI-powered story creation using universe context
- Integration with text generation APIs (OpenAI/Anthropic)
- Context-aware prompts (universe + characters + plots)

**7. Illustration Generation**
- AI-powered image generation for characters and scenes
- Integration with image generation APIs (Stable Diffusion/DALL-E)
- Asset storage and management

**8. Story Playback**
- Automated story narration with Text-to-Speech
- Synchronized illustration display
- Playback controls (play, pause, speed adjustment)

**9. Data Persistence**
- PostgreSQL database with complex relationships
- Asset storage (images, generated content)
- Version history (optional stretch goal)

### Technical Architecture

```
Frontend (React + TypeScript)
├── Authentication (Supabase Auth SDK)
├── UI Components (Tailwind CSS)
├── State Management (Context API + hooks)
├── Real-time Client (WebSocket)
├── API Client (fetch/axios)
└── Rich Text Editor (Lexical/Tiptap)

Backend (Rust + Axum)
├── REST API Endpoints
├── WebSocket Server
├── Database Layer (sqlx + PostgreSQL)
├── Authentication Middleware (JWT validation)
├── External API Integration (AI services)
└── Asset Management

Infrastructure
├── Database: Supabase PostgreSQL
├── Storage: Cloudflare R2 / Supabase Storage
├── Frontend Deploy: Vercel
└── Backend Deploy: Railway / Fly.io
```

### Database Schema (High-Level)

```sql
users (id, email, name, created_at)
universes (id, user_id, name, description, settings, created_at)
universe_collaborators (universe_id, user_id, permission_level)
characters (id, universe_id, name, description, attributes, created_at)
character_relationships (id, character_a_id, character_b_id, relationship_type, description)
plots (id, universe_id, title, description, created_at)
plot_characters (plot_id, character_id, role)
stories (id, universe_id, content, generated_at)
assets (id, universe_id, type, url, metadata, created_at)
```

---

## 6-Week Curriculum

### Overview

| Week | Focus | Key Deliverable |
|------|-------|-----------------|
| Week 1 | Web Fundamentals | Interactive UI with forms |
| Week 2 | React Deep Dive | Multi-page app with routing |
| Week 3 | Rust Backend | Full-stack CRUD application |
| Week 4 | Real-Time Collaboration | Collaborative editor |
| Week 5 | Capstone Part 1 | Core platform features |
| Week 6 | Capstone Part 2 + Deploy | Production MVP |

---

## Week 1: Web Foundations (Days 1-7)

**Learning Objectives:**
- [ ] Understand HTML5 semantic structure
- [ ] Master CSS layout via Tailwind CSS (Flexbox, Grid, responsive design)
- [ ] Learn JavaScript ES6+ essentials (types, functions, async/await)
- [ ] Grasp TypeScript fundamentals (types, interfaces, generics)
- [ ] Build React components with JSX
- [ ] Understand React state with useState hook
- [ ] Handle events and forms in React

**Concepts to Master:**
- HTML semantic elements (header, nav, main, section, article, footer)
- CSS Box Model
- Flexbox and Grid layouts
- Responsive design (mobile-first)
- JavaScript closures and scope
- Promises and async/await
- TypeScript type system
- React component lifecycle
- Virtual DOM concept

---

### Day 1: Environment Setup + HTML/Tailwind (4-6 hours)

**Learning Goals:**
- Set up development environment
- Understand HTML semantic structure
- Learn Tailwind CSS utility classes
- Build responsive layouts

**Tasks:**

**1. Environment Setup (1 hour)**
```bash
# Install Node.js 20+ LTS (via homebrew or official installer)
brew install node

# Verify installation
node --version  # Should be 20+
npm --version

# Install VS Code extensions
# - ESLint
# - Prettier - Code formatter
# - Tailwind CSS IntelliSense
# - TypeScript and JavaScript Language Features
# - Thunder Client (API testing)
```

**2. HTML Fundamentals (1.5 hours)**

Create a simple HTML page to understand structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Worldbuilding Platform</title>
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#universes">Universes</a></li>
                <li><a href="#characters">Characters</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section>
            <h1>Create Your World</h1>
            <p>Collaborate with friends to build imaginary universes.</p>
        </section>

        <article>
            <h2>Featured Universe</h2>
            <p>A cyberpunk dystopia where AI has achieved consciousness...</p>
        </article>
    </main>

    <footer>
        <p>&copy; 2025 Worldbuilding Platform</p>
    </footer>
</body>
</html>
```

**Compare to Flutter:**
- `<header>` is like a `AppBar` widget
- `<section>` is like a `Container` with semantic meaning
- `<nav>` is like a `NavigationBar`
- HTML structure is like widget tree structure

**3. Tailwind CSS Introduction (2 hours)**

Create a Vite project with Tailwind:

```bash
npm create vite@latest worldbuilding-frontend -- --template vanilla
cd worldbuilding-frontend
npm install
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Configure Tailwind in `tailwind.config.js`:

```js
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Add to `src/style.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

**Build: Responsive Landing Page**

Create `index.html` with Tailwind classes:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Worldbuilding Platform</title>
    <link rel="stylesheet" href="/src/style.css">
</head>
<body class="bg-gray-900 text-white">
    <!-- Header with navigation -->
    <header class="bg-gray-800 shadow-lg">
        <nav class="container mx-auto px-6 py-4">
            <div class="flex items-center justify-between">
                <h1 class="text-2xl font-bold">Worldbuilding</h1>
                <ul class="flex space-x-6">
                    <li><a href="#" class="hover:text-blue-400">Home</a></li>
                    <li><a href="#" class="hover:text-blue-400">Universes</a></li>
                    <li><a href="#" class="hover:text-blue-400">Characters</a></li>
                </ul>
            </div>
        </nav>
    </header>

    <!-- Hero section -->
    <main class="container mx-auto px-6 py-16">
        <section class="text-center mb-16">
            <h2 class="text-5xl font-bold mb-4">Create Your World</h2>
            <p class="text-xl text-gray-300 mb-8">
                Collaborate with friends to build imaginary universes
            </p>
            <button class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-8 rounded-lg transition">
                Get Started
            </button>
        </section>

        <!-- Features grid -->
        <section class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div class="bg-gray-800 p-6 rounded-lg">
                <h3 class="text-xl font-bold mb-3">Real-Time Collaboration</h3>
                <p class="text-gray-300">Work together with friends to build your universe</p>
            </div>
            <div class="bg-gray-800 p-6 rounded-lg">
                <h3 class="text-xl font-bold mb-3">AI-Powered Stories</h3>
                <p class="text-gray-300">Generate stories and illustrations automatically</p>
            </div>
            <div class="bg-gray-800 p-6 rounded-lg">
                <h3 class="text-xl font-bold mb-3">Rich Characters</h3>
                <p class="text-gray-300">Create complex characters with relationships</p>
            </div>
        </section>
    </main>

    <footer class="bg-gray-800 mt-16">
        <div class="container mx-auto px-6 py-4 text-center text-gray-400">
            <p>&copy; 2025 Worldbuilding Platform</p>
        </div>
    </footer>
</body>
</html>
```

**Run the dev server:**
```bash
npm run dev
```

**Learning Points:**

1. **Tailwind Utilities:**
   - `container mx-auto` - Centered responsive container
   - `px-6 py-4` - Padding (x-axis: 1.5rem, y-axis: 1rem)
   - `flex items-center justify-between` - Flexbox layout
   - `grid grid-cols-1 md:grid-cols-3` - Responsive grid
   - `hover:bg-blue-700` - Hover state
   - `bg-gray-900 text-white` - Colors

2. **Responsive Design:**
   - Mobile-first approach
   - `md:grid-cols-3` - 3 columns on medium screens and up
   - `sm:`, `md:`, `lg:`, `xl:`, `2xl:` - Breakpoints

3. **Compare to CSS:**
   - Tailwind: `flex items-center`
   - CSS: `display: flex; align-items: center;`

**Day 1 Checkpoint:**
- [x] Development environment set up
- [x] Understand HTML semantic structure
- [x] Can use Tailwind utilities for layout
- [x] Built responsive landing page
- [x] Comfortable with Flexbox and Grid via Tailwind

**Date Completed:** November 4, 2025
**Projects:**
- worldbuilding-frontend landing page
- flexbox-demo.html interactive playground

**Resources:**
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [MDN HTML Elements Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

---

### Day 2: CSS Layout Deep Dive (4-6 hours)

**Learning Goals:**
- Master Flexbox for one-dimensional layouts
- Master Grid for two-dimensional layouts
- Understand responsive design patterns
- Build complex layouts with Tailwind

**Tasks:**

**1. Flexbox Mastery (2 hours)**

Flexbox is perfect for navigation bars, button groups, and one-dimensional layouts.

**Key Concepts:**
- `flex` - Creates flex container
- `flex-row` / `flex-col` - Direction
- `justify-` - Main axis alignment
- `items-` - Cross axis alignment
- `flex-wrap` - Wrapping behavior
- `flex-grow`, `flex-shrink`, `flex-basis` - Item sizing

**Build: Navigation Component**

```html
<!-- Flexible navigation that adapts to content -->
<nav class="flex items-center justify-between p-4 bg-gray-800">
    <div class="flex items-center space-x-2">
        <img src="/logo.svg" alt="Logo" class="w-8 h-8">
        <span class="text-xl font-bold">Worldbuilding</span>
    </div>

    <ul class="flex space-x-6">
        <li><a href="#" class="hover:text-blue-400">Universes</a></li>
        <li><a href="#" class="hover:text-blue-400">Characters</a></li>
        <li><a href="#" class="hover:text-blue-400">Stories</a></li>
    </ul>

    <div class="flex items-center space-x-4">
        <button class="px-4 py-2 bg-blue-600 rounded hover:bg-blue-700">Login</button>
    </div>
</nav>

<!-- Vertical flex layout -->
<div class="flex flex-col space-y-4">
    <div class="p-4 bg-gray-800 rounded">Item 1</div>
    <div class="p-4 bg-gray-800 rounded">Item 2</div>
    <div class="p-4 bg-gray-800 rounded">Item 3</div>
</div>

<!-- Centered content -->
<div class="flex items-center justify-center h-screen">
    <div class="text-center">
        <h1 class="text-4xl font-bold mb-4">Welcome</h1>
        <p class="text-gray-400">Start building your universe</p>
    </div>
</div>
```

**Compare to Flutter:**
- `flex` = `Row` or `Column` widget
- `justify-between` = `MainAxisAlignment.spaceBetween`
- `items-center` = `CrossAxisAlignment.center`
- `space-x-4` = spacing between children

**2. Grid Mastery (2 hours)**

Grid is perfect for card layouts, dashboards, and two-dimensional layouts.

**Key Concepts:**
- `grid` - Creates grid container
- `grid-cols-{n}` - Number of columns
- `gap-{size}` - Space between items
- `col-span-{n}` - Item spans multiple columns
- `grid-rows-{n}` - Number of rows
- Responsive prefixes: `sm:`, `md:`, `lg:`

**Build: Universe Cards Grid**

```html
<div class="container mx-auto p-6">
    <h2 class="text-3xl font-bold mb-6">Your Universes</h2>

    <!-- Responsive grid: 1 col mobile, 2 cols tablet, 3 cols desktop -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <!-- Universe Card -->
        <div class="bg-gray-800 rounded-lg overflow-hidden hover:shadow-xl transition">
            <img src="/universe1.jpg" alt="Universe" class="w-full h-48 object-cover">
            <div class="p-6">
                <h3 class="text-xl font-bold mb-2">Cyberpunk 2199</h3>
                <p class="text-gray-400 mb-4">A dystopian future where AI rules...</p>
                <div class="flex justify-between items-center">
                    <span class="text-sm text-gray-500">12 characters</span>
                    <button class="text-blue-400 hover:text-blue-300">Edit</button>
                </div>
            </div>
        </div>

        <!-- Repeat for more cards... -->
        <div class="bg-gray-800 rounded-lg overflow-hidden hover:shadow-xl transition">
            <img src="/universe2.jpg" alt="Universe" class="w-full h-48 object-cover">
            <div class="p-6">
                <h3 class="text-xl font-bold mb-2">Fantasy Realm</h3>
                <p class="text-gray-400 mb-4">A world of magic and dragons...</p>
                <div class="flex justify-between items-center">
                    <span class="text-sm text-gray-500">8 characters</span>
                    <button class="text-blue-400 hover:text-blue-300">Edit</button>
                </div>
            </div>
        </div>

        <!-- Add more cards... -->
    </div>
</div>
```

**Advanced Grid Layout: Dashboard**

```html
<div class="grid grid-cols-12 gap-4 p-6">
    <!-- Sidebar (spans 3 columns) -->
    <aside class="col-span-3 bg-gray-800 rounded-lg p-4">
        <h3 class="font-bold mb-4">Navigation</h3>
        <ul class="space-y-2">
            <li><a href="#" class="block p-2 hover:bg-gray-700 rounded">Dashboard</a></li>
            <li><a href="#" class="block p-2 hover:bg-gray-700 rounded">Universes</a></li>
            <li><a href="#" class="block p-2 hover:bg-gray-700 rounded">Characters</a></li>
        </ul>
    </aside>

    <!-- Main content (spans 9 columns) -->
    <main class="col-span-9">
        <!-- Header row (full width) -->
        <div class="col-span-full bg-gray-800 rounded-lg p-6 mb-4">
            <h2 class="text-2xl font-bold">Dashboard</h2>
        </div>

        <!-- Stats grid (nested) -->
        <div class="grid grid-cols-3 gap-4 mb-4">
            <div class="bg-gray-800 rounded-lg p-4">
                <div class="text-3xl font-bold">12</div>
                <div class="text-gray-400">Universes</div>
            </div>
            <div class="bg-gray-800 rounded-lg p-4">
                <div class="text-3xl font-bold">45</div>
                <div class="text-gray-400">Characters</div>
            </div>
            <div class="bg-gray-800 rounded-lg p-4">
                <div class="text-3xl font-bold">23</div>
                <div class="text-gray-400">Stories</div>
            </div>
        </div>

        <!-- Content area -->
        <div class="bg-gray-800 rounded-lg p-6">
            <p>Main content here...</p>
        </div>
    </main>
</div>
```

**3. Responsive Design Practice (2 hours)**

**Build: Worldbuilding UI Mockup**

Create a complete responsive layout for the universe editor:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Universe Editor</title>
    <link rel="stylesheet" href="/src/style.css">
</head>
<body class="bg-gray-900 text-white">
    <!-- Top navigation -->
    <nav class="bg-gray-800 border-b border-gray-700 sticky top-0 z-50">
        <div class="container mx-auto px-4">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center space-x-8">
                    <h1 class="text-xl font-bold">Worldbuilding</h1>
                    <div class="hidden md:flex space-x-4">
                        <a href="#" class="px-3 py-2 rounded hover:bg-gray-700">Dashboard</a>
                        <a href="#" class="px-3 py-2 rounded hover:bg-gray-700">Universes</a>
                        <a href="#" class="px-3 py-2 rounded hover:bg-gray-700">Characters</a>
                    </div>
                </div>
                <button class="px-4 py-2 bg-blue-600 rounded hover:bg-blue-700">
                    New Universe
                </button>
            </div>
        </div>
    </nav>

    <!-- Main layout: sidebar + content -->
    <div class="flex h-[calc(100vh-4rem)]">
        <!-- Sidebar: hidden on mobile, visible on desktop -->
        <aside class="hidden lg:block w-64 bg-gray-800 border-r border-gray-700 overflow-y-auto">
            <div class="p-4">
                <h3 class="text-lg font-bold mb-4">Current Universe</h3>
                <div class="space-y-2">
                    <a href="#" class="block p-3 bg-gray-700 rounded">Overview</a>
                    <a href="#" class="block p-3 hover:bg-gray-700 rounded">Characters</a>
                    <a href="#" class="block p-3 hover:bg-gray-700 rounded">Plots</a>
                    <a href="#" class="block p-3 hover:bg-gray-700 rounded">Settings</a>
                </div>
            </div>
        </aside>

        <!-- Main content area -->
        <main class="flex-1 overflow-y-auto p-4 md:p-8">
            <div class="max-w-4xl mx-auto">
                <h2 class="text-3xl font-bold mb-6">Cyberpunk 2199</h2>

                <!-- Responsive grid -->
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mb-8">
                    <div class="lg:col-span-2 bg-gray-800 rounded-lg p-6">
                        <h3 class="text-xl font-bold mb-4">Description</h3>
                        <p class="text-gray-300">
                            A dystopian future where artificial intelligence has achieved
                            consciousness and now governs humanity...
                        </p>
                    </div>

                    <div class="bg-gray-800 rounded-lg p-6">
                        <h3 class="text-xl font-bold mb-4">Details</h3>
                        <dl class="space-y-2">
                            <div>
                                <dt class="text-sm text-gray-400">Genre</dt>
                                <dd class="font-medium">Cyberpunk</dd>
                            </div>
                            <div>
                                <dt class="text-sm text-gray-400">Created</dt>
                                <dd class="font-medium">Jan 15, 2025</dd>
                            </div>
                            <div>
                                <dt class="text-sm text-gray-400">Characters</dt>
                                <dd class="font-medium">12</dd>
                            </div>
                        </dl>
                    </div>
                </div>

                <!-- Character list -->
                <section>
                    <h3 class="text-2xl font-bold mb-4">Characters</h3>
                    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
                        <!-- Character card -->
                        <div class="bg-gray-800 rounded-lg p-4 hover:bg-gray-750 transition cursor-pointer">
                            <div class="flex items-center space-x-3">
                                <div class="w-12 h-12 bg-blue-600 rounded-full flex items-center justify-center font-bold">
                                    JD
                                </div>
                                <div>
                                    <h4 class="font-bold">John Doe</h4>
                                    <p class="text-sm text-gray-400">Hacker</p>
                                </div>
                            </div>
                        </div>

                        <!-- More character cards... -->
                    </div>
                </section>
            </div>
        </main>

        <!-- Right sidebar: online users (hidden on small screens) -->
        <aside class="hidden xl:block w-64 bg-gray-800 border-l border-gray-700 p-4">
            <h3 class="font-bold mb-4">Online Now</h3>
            <div class="space-y-3">
                <div class="flex items-center space-x-2">
                    <div class="w-2 h-2 bg-green-500 rounded-full"></div>
                    <span class="text-sm">Alice</span>
                </div>
                <div class="flex items-center space-x-2">
                    <div class="w-2 h-2 bg-green-500 rounded-full"></div>
                    <span class="text-sm">Bob</span>
                </div>
            </div>
        </aside>
    </div>
</body>
</html>
```

**Responsive Breakpoints:**
- `sm:` - 640px and up (mobile landscape, small tablets)
- `md:` - 768px and up (tablets)
- `lg:` - 1024px and up (desktops)
- `xl:` - 1280px and up (large desktops)
- `2xl:` - 1536px and up (very large screens)

**Day 2 Checkpoint:**
- [ ] Master Flexbox for one-dimensional layouts
- [ ] Master Grid for two-dimensional layouts
- [ ] Understand responsive design patterns
- [ ] Can build complex multi-column layouts
- [ ] Comfortable with Tailwind responsive utilities

**Resources:**
- [CSS Tricks: A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS Tricks: A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Tailwind Responsive Design](https://tailwindcss.com/docs/responsive-design)

---

### Day 3: JavaScript Essentials (4-6 hours)

**Learning Goals:**
- Understand JavaScript fundamentals
- Master ES6+ features
- Learn async programming (Promises, async/await)
- DOM manipulation basics

**Compare to Rust:**
- JavaScript is garbage-collected (no ownership/borrowing)
- Dynamic typing vs Rust's static typing (TypeScript fixes this)
- Prototype-based vs trait-based
- Single-threaded event loop vs Rust's threading model

**Compare to Python:**
- Similar syntax for loops, conditionals
- Both have first-class functions
- JavaScript is event-driven (callbacks, promises)
- Different module systems

**Tasks:**

**1. Variables and Types (1 hour)**

```javascript
// Variables
let name = "Alice";        // Mutable (like Python)
const age = 25;            // Immutable (like Rust's `let`)
var old = "avoid";         // Old style, avoid using

// Types (dynamic typing)
let string = "Hello";
let number = 42;
let boolean = true;
let nullValue = null;
let undefinedValue = undefined;
let array = [1, 2, 3, 4, 5];
let object = { name: "Alice", age: 25 };

// Type checking
console.log(typeof string);    // "string"
console.log(typeof number);    // "number"
console.log(typeof array);     // "object" (arrays are objects)
console.log(Array.isArray(array));  // true

// Template literals (like Python f-strings)
const greeting = `Hello, ${name}! You are ${age} years old.`;
console.log(greeting);

// Compare to Rust:
// Rust: let name: &str = "Alice";
// JS:   const name = "Alice";
//
// Rust: ownership prevents multiple mutable references
// JS:   garbage collection handles memory
```

**2. Functions (1 hour)**

```javascript
// Function declaration
function greet(name) {
    return `Hello, ${name}!`;
}

// Function expression
const greet2 = function(name) {
    return `Hello, ${name}!`;
};

// Arrow function (similar to Rust closures)
const greet3 = (name) => {
    return `Hello, ${name}!`;
};

// Concise arrow function (implicit return)
const greet4 = (name) => `Hello, ${name}!`;

// Multiple parameters
const add = (a, b) => a + b;

// No parameters
const getRandom = () => Math.random();

// Default parameters (like Rust)
const greetWithDefault = (name = "World") => `Hello, ${name}!`;

// Rest parameters (like Python *args)
const sum = (...numbers) => numbers.reduce((acc, n) => acc + n, 0);
console.log(sum(1, 2, 3, 4));  // 10

// Destructuring parameters
const printUser = ({ name, age }) => {
    console.log(`${name} is ${age} years old`);
};
printUser({ name: "Alice", age: 25 });

// Compare to Rust:
// Rust: fn greet(name: &str) -> String { format!("Hello, {}!", name) }
// JS:   const greet = (name) => `Hello, ${name}!`;
//
// Rust: |x| x + 1  (closure)
// JS:   (x) => x + 1  (arrow function)
```

**3. Arrays and Objects (1 hour)**

```javascript
// Arrays (like Python lists)
const numbers = [1, 2, 3, 4, 5];

// Array methods (functional programming style)
const doubled = numbers.map(n => n * 2);        // [2, 4, 6, 8, 10]
const evens = numbers.filter(n => n % 2 === 0); // [2, 4]
const sum = numbers.reduce((acc, n) => acc + n, 0); // 15

// Compare to Rust:
// Rust: numbers.iter().map(|n| n * 2).collect()
// JS:   numbers.map(n => n * 2)

// Array destructuring
const [first, second, ...rest] = numbers;
console.log(first);   // 1
console.log(rest);    // [3, 4, 5]

// Spread operator
const moreNumbers = [...numbers, 6, 7, 8];
const combined = [...numbers, ...moreNumbers];

// Objects (like Python dicts or Rust structs)
const user = {
    name: "Alice",
    age: 25,
    email: "alice@example.com",
    // Method
    greet() {
        return `Hello, I'm ${this.name}`;
    }
};

// Access properties
console.log(user.name);      // "Alice"
console.log(user["name"]);   // "Alice"

// Object destructuring
const { name, age } = user;
console.log(name, age);

// Spread operator for objects
const updatedUser = {
    ...user,
    age: 26,
    city: "New York"
};

// Object shorthand
const name2 = "Bob";
const age2 = 30;
const user2 = { name: name2, age: age2 };  // Verbose
const user3 = { name2, age2 };              // Shorthand

// Computed property names
const key = "email";
const user4 = {
    [key]: "bob@example.com"
};
```

**4. Async Programming (2 hours)**

This is crucial for web development!

```javascript
// Callbacks (old style, causes "callback hell")
setTimeout(() => {
    console.log("This runs after 1 second");
}, 1000);

// Promises (modern async)
const fetchUser = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const user = { name: "Alice", age: 25 };
            resolve(user);  // Success
            // reject(new Error("Failed"));  // Error
        }, 1000);
    });
};

// Using promises with .then()
fetchUser()
    .then(user => console.log(user))
    .catch(error => console.error(error));

// Async/await (cleanest syntax, like Rust async)
async function getUser() {
    try {
        const user = await fetchUser();
        console.log(user);
        return user;
    } catch (error) {
        console.error(error);
    }
}

// Compare to Rust:
// Rust: async fn get_user() -> Result<User, Error> { ... }
// JS:   async function getUser() { ... }
//
// Rust: let user = fetch_user().await?;
// JS:   const user = await fetchUser();

// Multiple async operations
async function getAllData() {
    // Sequential (slower)
    const user = await fetchUser();
    const posts = await fetchPosts(user.id);

    // Parallel (faster)
    const [user2, posts2] = await Promise.all([
        fetchUser(),
        fetchPosts()
    ]);
}

// Fetch API (browser built-in for HTTP requests)
async function fetchFromAPI() {
    try {
        const response = await fetch('https://api.example.com/users');
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        const data = await response.json();
        return data;
    } catch (error) {
        console.error('Fetch error:', error);
    }
}
```

**5. DOM Manipulation (1 hour)**

Understanding the DOM is important even though React will handle most of this:

```javascript
// Select elements
const heading = document.querySelector('h1');
const allParagraphs = document.querySelectorAll('p');
const byId = document.getElementById('myId');

// Modify content
heading.textContent = 'New Heading';
heading.innerHTML = '<span>New Heading with HTML</span>';

// Modify attributes
heading.setAttribute('class', 'text-3xl font-bold');
heading.classList.add('text-blue-600');
heading.classList.remove('text-black');
heading.classList.toggle('hidden');

// Create elements
const newDiv = document.createElement('div');
newDiv.textContent = 'New content';
newDiv.className = 'bg-gray-800 p-4 rounded';
document.body.appendChild(newDiv);

// Event listeners
const button = document.querySelector('button');
button.addEventListener('click', (event) => {
    console.log('Button clicked!', event);
});

// Event delegation (efficient for many elements)
document.addEventListener('click', (event) => {
    if (event.target.matches('.character-card')) {
        console.log('Character card clicked');
    }
});
```

**Build: Interactive Universe Creator (Vanilla JS)**

Create a simple interactive form without React to understand the fundamentals:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Universe Creator</title>
    <link rel="stylesheet" href="/src/style.css">
</head>
<body class="bg-gray-900 text-white p-8">
    <div class="max-w-2xl mx-auto">
        <h1 class="text-3xl font-bold mb-6">Create Your Universe</h1>

        <form id="universeForm" class="space-y-4">
            <div>
                <label for="name" class="block text-sm font-medium mb-2">Universe Name</label>
                <input type="text" id="name" name="name"
                       class="w-full px-4 py-2 bg-gray-800 border border-gray-700 rounded focus:outline-none focus:border-blue-500"
                       required>
            </div>

            <div>
                <label for="genre" class="block text-sm font-medium mb-2">Genre</label>
                <select id="genre" name="genre"
                        class="w-full px-4 py-2 bg-gray-800 border border-gray-700 rounded focus:outline-none focus:border-blue-500">
                    <option value="fantasy">Fantasy</option>
                    <option value="scifi">Science Fiction</option>
                    <option value="cyberpunk">Cyberpunk</option>
                    <option value="postapocalyptic">Post-Apocalyptic</option>
                </select>
            </div>

            <div>
                <label for="description" class="block text-sm font-medium mb-2">Description</label>
                <textarea id="description" name="description" rows="4"
                          class="w-full px-4 py-2 bg-gray-800 border border-gray-700 rounded focus:outline-none focus:border-blue-500"
                          required></textarea>
            </div>

            <button type="submit" class="w-full py-3 bg-blue-600 hover:bg-blue-700 rounded font-bold transition">
                Create Universe
            </button>
        </form>

        <div id="result" class="mt-8"></div>

        <div id="universeList" class="mt-8 space-y-4"></div>
    </div>

    <script type="module" src="/src/main.js"></script>
</body>
</html>
```

Create `src/main.js`:

```javascript
// State management (simple array)
let universes = [];

// Load from localStorage on page load
const loadUniverses = () => {
    const stored = localStorage.getItem('universes');
    if (stored) {
        universes = JSON.parse(stored);
        renderUniverses();
    }
};

// Save to localStorage
const saveUniverses = () => {
    localStorage.setItem('universes', JSON.stringify(universes));
};

// Create universe
const createUniverse = (formData) => {
    const universe = {
        id: Date.now(),
        name: formData.name,
        genre: formData.genre,
        description: formData.description,
        createdAt: new Date().toISOString()
    };

    universes.push(universe);
    saveUniverses();
    return universe;
};

// Delete universe
const deleteUniverse = (id) => {
    universes = universes.filter(u => u.id !== id);
    saveUniverses();
    renderUniverses();
};

// Render universes list
const renderUniverses = () => {
    const container = document.getElementById('universeList');

    if (universes.length === 0) {
        container.innerHTML = '<p class="text-gray-400">No universes created yet.</p>';
        return;
    }

    container.innerHTML = universes.map(universe => `
        <div class="bg-gray-800 rounded-lg p-6">
            <div class="flex justify-between items-start mb-3">
                <h3 class="text-xl font-bold">${universe.name}</h3>
                <button onclick="deleteUniverse(${universe.id})"
                        class="text-red-400 hover:text-red-300">Delete</button>
            </div>
            <div class="inline-block px-3 py-1 bg-blue-600 rounded text-sm mb-3">
                ${universe.genre}
            </div>
            <p class="text-gray-300">${universe.description}</p>
            <p class="text-sm text-gray-500 mt-3">
                Created: ${new Date(universe.createdAt).toLocaleDateString()}
            </p>
        </div>
    `).join('');
};

// Make deleteUniverse available globally for onclick
window.deleteUniverse = deleteUniverse;

// Form submission handler
const form = document.getElementById('universeForm');
form.addEventListener('submit', async (event) => {
    event.preventDefault();

    // Get form data
    const formData = {
        name: form.name.value,
        genre: form.genre.value,
        description: form.description.value
    };

    // Create universe
    const universe = createUniverse(formData);

    // Show success message
    const result = document.getElementById('result');
    result.innerHTML = `
        <div class="bg-green-900/50 border border-green-700 rounded-lg p-4">
            <p class="text-green-300">Universe "${universe.name}" created successfully!</p>
        </div>
    `;

    // Clear the message after 3 seconds
    setTimeout(() => {
        result.innerHTML = '';
    }, 3000);

    // Reset form
    form.reset();

    // Re-render list
    renderUniverses();
});

// Load existing universes on page load
loadUniverses();
```

**Day 3 Checkpoint:**
- [ ] Understand JavaScript variables and types
- [ ] Master arrow functions and array methods
- [ ] Can work with objects and destructuring
- [ ] Understand Promises and async/await
- [ ] Can manipulate DOM and handle events
- [ ] Built interactive form with vanilla JavaScript

**Resources:**
- [JavaScript.info](https://javascript.info/) - Comprehensive JavaScript guide
- [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
- [Eloquent JavaScript](https://eloquentjavascript.net/) - Free online book

---

### Day 4: TypeScript Foundation (4-6 hours)

**Learning Goals:**
- Understand TypeScript's type system
- Learn to define interfaces and types
- Master generics and advanced types
- Set up TypeScript in a project

**Why TypeScript for Rust Developers:**
- Compile-time type checking (like Rust!)
- Prevents entire classes of runtime errors
- Excellent IDE support (autocomplete, refactoring)
- 92% of JavaScript developers use TypeScript in 2025
- Similar to Python type hints but enforced at compile-time

**Compare to Rust:**
- Both have strong static typing
- TypeScript: structural typing (shape matters)
- Rust: nominal typing (name matters)
- TypeScript: gradual typing (can opt-out)
- Rust: ownership system (TypeScript doesn't have this)

**Tasks:**

**1. TypeScript Setup (30 minutes)**

```bash
# Create new Vite project with TypeScript
npm create vite@latest universe-app -- --template react-ts
cd universe-app
npm install
npm run dev
```

TypeScript configuration (`tsconfig.json`):

```json
{
  "compilerOptions": {
    "target": "ES2020",
    "useDefineForClassFields": true,
    "lib": ["ES2020", "DOM", "DOM.Iterable"],
    "module": "ESNext",
    "skipLibCheck": true,

    /* Bundler mode */
    "moduleResolution": "bundler",
    "allowImportingTsExtensions": true,
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx",

    /* Linting */
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noFallthroughCasesInSwitch": true
  },
  "include": ["src"],
  "references": [{ "path": "./tsconfig.node.json" }]
}
```

**2. Basic Types (1 hour)**

```typescript
// Primitive types
let name: string = "Alice";
let age: number = 25;
let isActive: boolean = true;
let nothing: null = null;
let notDefined: undefined = undefined;

// Arrays
let numbers: number[] = [1, 2, 3, 4, 5];
let strings: Array<string> = ["a", "b", "c"];

// Tuple (like Rust tuple)
let person: [string, number] = ["Alice", 25];

// Enum (like Rust enum, but simpler)
enum Genre {
    Fantasy = "FANTASY",
    SciFi = "SCIFI",
    Cyberpunk = "CYBERPUNK",
    PostApocalyptic = "POST_APOCALYPTIC"
}

let genre: Genre = Genre.Fantasy;

// Any (avoid if possible)
let anything: any = "can be anything";
anything = 42;
anything = true;

// Unknown (safer than any)
let something: unknown = "string";
if (typeof something === "string") {
    console.log(something.toUpperCase());  // TypeScript knows it's a string
}

// Void (function returns nothing)
function logMessage(message: string): void {
    console.log(message);
}

// Never (function never returns)
function throwError(message: string): never {
    throw new Error(message);
}
```

**3. Interfaces and Types (1.5 hours)**

```typescript
// Interface (like Rust struct)
interface Universe {
    id: number;
    name: string;
    genre: Genre;
    description: string;
    createdAt: Date;
}

// Type alias (similar to interface, more flexible)
type Character = {
    id: number;
    name: string;
    role: string;
    universeId: number;
};

// Optional properties
interface User {
    id: number;
    name: string;
    email: string;
    avatar?: string;  // Optional (like Rust's Option<T>)
}

// Readonly properties (like Rust's immutability)
interface Config {
    readonly apiUrl: string;
    readonly timeout: number;
}

// Index signature (dynamic keys)
interface Dictionary {
    [key: string]: string;
}

const translations: Dictionary = {
    hello: "Hola",
    goodbye: "Adiós"
};

// Function types
interface GreetingFunction {
    (name: string): string;
}

const greet: GreetingFunction = (name) => `Hello, ${name}!`;

// Type alias for function
type MathOperation = (a: number, b: number) => number;

const add: MathOperation = (a, b) => a + b;
const subtract: MathOperation = (a, b) => a - b;

// Union types (like Rust's enum)
type Status = "pending" | "loading" | "success" | "error";

let status: Status = "pending";
// status = "invalid";  // Error!

type StringOrNumber = string | number;

function printId(id: StringOrNumber) {
    if (typeof id === "string") {
        console.log(id.toUpperCase());
    } else {
        console.log(id.toFixed(2));
    }
}

// Intersection types
interface Nameable {
    name: string;
}

interface Ageable {
    age: number;
}

type Person = Nameable & Ageable;

const person: Person = {
    name: "Alice",
    age: 25
};

// Extending interfaces (like Rust traits)
interface Entity {
    id: number;
    createdAt: Date;
}

interface Universe extends Entity {
    name: string;
    genre: Genre;
}

// Compare to Rust:
// Rust: struct Universe { id: u32, name: String, genre: Genre }
// TS:   interface Universe { id: number; name: string; genre: Genre }
```

**4. Generics (1.5 hours)**

```typescript
// Generic function (like Rust generics)
function identity<T>(value: T): T {
    return value;
}

const str = identity<string>("hello");
const num = identity<number>(42);
const inferred = identity("hello");  // Type inferred

// Generic array function
function firstElement<T>(arr: T[]): T | undefined {
    return arr[0];
}

const firstNumber = firstElement([1, 2, 3]);  // number | undefined
const firstName = firstElement(["a", "b"]);   // string | undefined

// Generic interface
interface ApiResponse<T> {
    data: T;
    status: number;
    message: string;
}

interface User {
    id: number;
    name: string;
}

const userResponse: ApiResponse<User> = {
    data: { id: 1, name: "Alice" },
    status: 200,
    message: "Success"
};

const usersResponse: ApiResponse<User[]> = {
    data: [
        { id: 1, name: "Alice" },
        { id: 2, name: "Bob" }
    ],
    status: 200,
    message: "Success"
};

// Generic constraints
interface HasId {
    id: number;
}

function findById<T extends HasId>(items: T[], id: number): T | undefined {
    return items.find(item => item.id === id);
}

// Compare to Rust:
// Rust: fn find_by_id<T: HasId>(items: &[T], id: u32) -> Option<&T>
// TS:   function findById<T extends HasId>(items: T[], id: number): T | undefined

// Generic class
class DataStore<T> {
    private items: T[] = [];

    add(item: T): void {
        this.items.push(item);
    }

    getAll(): T[] {
        return this.items;
    }

    findById<K extends keyof T>(key: K, value: T[K]): T | undefined {
        return this.items.find(item => item[key] === value);
    }
}

const universeStore = new DataStore<Universe>();
universeStore.add({
    id: 1,
    name: "Cyberpunk 2199",
    genre: Genre.Cyberpunk,
    description: "A dystopian future...",
    createdAt: new Date()
});
```

**5. Advanced Types (1.5 hours)**

```typescript
// Utility types

// Partial<T> - Makes all properties optional
interface Todo {
    title: string;
    description: string;
    completed: boolean;
}

function updateTodo(todo: Todo, updates: Partial<Todo>): Todo {
    return { ...todo, ...updates };
}

// Required<T> - Makes all properties required
type RequiredTodo = Required<Partial<Todo>>;

// Readonly<T> - Makes all properties readonly
const todo: Readonly<Todo> = {
    title: "Learn TypeScript",
    description: "Master the type system",
    completed: false
};
// todo.completed = true;  // Error!

// Pick<T, K> - Pick specific properties
type TodoPreview = Pick<Todo, "title" | "completed">;

// Omit<T, K> - Omit specific properties
type TodoInfo = Omit<Todo, "completed">;

// Record<K, T> - Create object type with specific keys
type PageInfo = Record<"home" | "about" | "contact", { title: string; url: string }>;

const pages: PageInfo = {
    home: { title: "Home", url: "/" },
    about: { title: "About", url: "/about" },
    contact: { title: "Contact", url: "/contact" }
};

// Mapped types
type Readonly2<T> = {
    readonly [P in keyof T]: T[P];
};

type Optional<T> = {
    [P in keyof T]?: T[P];
};

// Conditional types
type IsString<T> = T extends string ? "yes" : "no";

type A = IsString<string>;   // "yes"
type B = IsString<number>;   // "no"

// Type inference with ReturnType
function createUser() {
    return {
        id: 1,
        name: "Alice",
        email: "alice@example.com"
    };
}

type User = ReturnType<typeof createUser>;

// Type guards
function isString(value: unknown): value is string {
    return typeof value === "string";
}

function processValue(value: unknown) {
    if (isString(value)) {
        console.log(value.toUpperCase());  // TypeScript knows it's a string
    }
}

// Discriminated unions (like Rust enums!)
type Success<T> = {
    type: "success";
    data: T;
};

type Error = {
    type: "error";
    error: string;
};

type Result<T> = Success<T> | Error;

function handleResult<T>(result: Result<T>) {
    if (result.type === "success") {
        console.log(result.data);  // TypeScript knows it's Success
    } else {
        console.error(result.error);  // TypeScript knows it's Error
    }
}

// Compare to Rust:
// Rust: enum Result<T, E> { Ok(T), Err(E) }
// TS:   type Result<T> = Success<T> | Error
```

**6. Practical TypeScript: Type-Safe Universe App (1 hour)**

Create type-safe models for the worldbuilding app:

```typescript
// src/types/index.ts

// Enums
export enum Genre {
    Fantasy = "FANTASY",
    SciFi = "SCIFI",
    Cyberpunk = "CYBERPUNK",
    PostApocalyptic = "POST_APOCALYPTIC",
    Horror = "HORROR",
    Historical = "HISTORICAL"
}

export enum RelationshipType {
    Parent = "PARENT",
    Child = "CHILD",
    Sibling = "SIBLING",
    Friend = "FRIEND",
    Rival = "RIVAL",
    Enemy = "ENEMY",
    Ally = "ALLY",
    Romantic = "ROMANTIC"
}

export enum PermissionLevel {
    Read = "READ",
    Write = "WRITE",
    Admin = "ADMIN"
}

// Base entity interface
export interface Entity {
    id: number;
    createdAt: Date;
    updatedAt: Date;
}

// User
export interface User extends Entity {
    email: string;
    name: string;
    avatar?: string;
}

// Universe
export interface Universe extends Entity {
    name: string;
    genre: Genre;
    description: string;
    ownerId: number;
    settings: UniverseSettings;
}

export interface UniverseSettings {
    hasMagic: boolean;
    technologyLevel: number;  // 1-10
    themes: string[];
    rules: string[];
}

// Collaborators
export interface UniverseCollaborator {
    universeId: number;
    userId: number;
    permissionLevel: PermissionLevel;
    addedAt: Date;
}

// Character
export interface Character extends Entity {
    universeId: number;
    name: string;
    role: string;
    description: string;
    attributes: CharacterAttributes;
    imageUrl?: string;
}

export interface CharacterAttributes {
    age?: number;
    species?: string;
    occupation?: string;
    skills: string[];
    personality: string[];
    background: string;
}

// Character Relationship
export interface CharacterRelationship extends Entity {
    characterAId: number;
    characterBId: number;
    relationshipType: RelationshipType;
    description: string;
}

// Plot
export interface Plot extends Entity {
    universeId: number;
    title: string;
    description: string;
    outline: string;
}

export interface PlotCharacter {
    plotId: number;
    characterId: number;
    role: string;
}

// Story
export interface Story extends Entity {
    universeId: number;
    title: string;
    content: string;
    generatedBy: "AI" | "USER";
    metadata: StoryMetadata;
}

export interface StoryMetadata {
    wordCount: number;
    characterIds: number[];
    plotIds: number[];
    genre: Genre;
}

// Asset (images, etc.)
export interface Asset extends Entity {
    universeId: number;
    type: "CHARACTER_IMAGE" | "SCENE_IMAGE" | "ICON" | "OTHER";
    url: string;
    metadata: AssetMetadata;
}

export interface AssetMetadata {
    fileName: string;
    mimeType: string;
    sizeBytes: number;
    width?: number;
    height?: number;
    generatedBy?: "AI" | "USER";
}

// API Response types
export interface ApiResponse<T> {
    data: T;
    status: number;
    message: string;
}

export interface ApiError {
    status: number;
    message: string;
    errors?: Record<string, string[]>;
}

// Form types (for creating/updating)
export type CreateUniverseInput = Omit<Universe, "id" | "createdAt" | "updatedAt" | "ownerId">;
export type UpdateUniverseInput = Partial<CreateUniverseInput>;

export type CreateCharacterInput = Omit<Character, "id" | "createdAt" | "updatedAt">;
export type UpdateCharacterInput = Partial<CreateCharacterInput>;

// Utility types
export type WithoutId<T extends { id: number }> = Omit<T, "id">;
export type WithoutTimestamps<T extends Entity> = Omit<T, "createdAt" | "updatedAt">;
```

Create a typed API client:

```typescript
// src/api/client.ts

import type {
    Universe,
    Character,
    CreateUniverseInput,
    UpdateUniverseInput,
    CreateCharacterInput,
    UpdateCharacterInput,
    ApiResponse,
    ApiError
} from "../types";

const API_BASE_URL = import.meta.env.VITE_API_URL || "http://localhost:3000/api";

class ApiClient {
    private async request<T>(
        endpoint: string,
        options: RequestInit = {}
    ): Promise<T> {
        const response = await fetch(`${API_BASE_URL}${endpoint}`, {
            ...options,
            headers: {
                "Content-Type": "application/json",
                ...options.headers
            }
        });

        if (!response.ok) {
            const error: ApiError = await response.json();
            throw new Error(error.message);
        }

        const data: ApiResponse<T> = await response.json();
        return data.data;
    }

    // Universes
    async getUniverses(): Promise<Universe[]> {
        return this.request<Universe[]>("/universes");
    }

    async getUniverse(id: number): Promise<Universe> {
        return this.request<Universe>(`/universes/${id}`);
    }

    async createUniverse(input: CreateUniverseInput): Promise<Universe> {
        return this.request<Universe>("/universes", {
            method: "POST",
            body: JSON.stringify(input)
        });
    }

    async updateUniverse(id: number, input: UpdateUniverseInput): Promise<Universe> {
        return this.request<Universe>(`/universes/${id}`, {
            method: "PUT",
            body: JSON.stringify(input)
        });
    }

    async deleteUniverse(id: number): Promise<void> {
        return this.request<void>(`/universes/${id}`, {
            method: "DELETE"
        });
    }

    // Characters
    async getCharacters(universeId: number): Promise<Character[]> {
        return this.request<Character[]>(`/universes/${universeId}/characters`);
    }

    async createCharacter(input: CreateCharacterInput): Promise<Character> {
        return this.request<Character>("/characters", {
            method: "POST",
            body: JSON.stringify(input)
        });
    }

    async updateCharacter(id: number, input: UpdateCharacterInput): Promise<Character> {
        return this.request<Character>(`/characters/${id}`, {
            method: "PUT",
            body: JSON.stringify(input)
        });
    }
}

export const apiClient = new ApiClient();
```

**Day 4 Checkpoint:**
- [ ] Understand TypeScript's type system
- [ ] Can define interfaces and type aliases
- [ ] Master generics for reusable code
- [ ] Understand utility types (Partial, Pick, Omit, etc.)
- [ ] Can create discriminated unions (like Rust enums)
- [ ] Built type-safe API client
- [ ] Comfortable with TypeScript for React

**Resources:**
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [TypeScript Deep Dive](https://basarat.gitbook.io/typescript/)
- [Total TypeScript](https://www.totaltypescript.com/) - Excellent tutorials

---

### Day 5: React Basics - Components (4-6 hours)

**Learning Goals:**
- Understand React component model
- Master JSX syntax
- Learn props and component composition
- Build reusable components

**Compare to Flutter:**
- React components = Flutter widgets
- JSX = Flutter widget tree in declarative syntax
- Props = widget constructor parameters
- Component composition = widget nesting

**Tasks:**

**1. React Setup Review (30 minutes)**

You already have a Vite + React + TypeScript project from Day 4. Let's explore the structure:

```
universe-app/
├── public/             # Static assets
├── src/
│   ├── App.tsx         # Main app component
│   ├── main.tsx        # Entry point
│   ├── App.css
│   └── index.css
├── index.html          # HTML template
├── package.json
├── tsconfig.json
└── vite.config.ts
```

**Entry point** (`src/main.tsx`):

```typescript
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.tsx'
import './index.css'

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
)
```

**2. JSX Fundamentals (1 hour)**

JSX is JavaScript XML - it looks like HTML but it's actually JavaScript:

```typescript
// src/App.tsx

import './App.css'

function App() {
    // JavaScript variables
    const title = "Worldbuilding Platform";
    const isLoggedIn = false;
    const user = { name: "Alice", age: 25 };

    // JSX expressions (inside curly braces)
    return (
        <div className="app">
            {/* This is a comment in JSX */}

            {/* Variables */}
            <h1>{title}</h1>

            {/* Expressions */}
            <p>2 + 2 = {2 + 2}</p>
            <p>{user.name} is {user.age} years old</p>

            {/* Conditional rendering */}
            {isLoggedIn ? (
                <p>Welcome back!</p>
            ) : (
                <p>Please log in</p>
            )}

            {/* Short-circuit evaluation */}
            {isLoggedIn && <p>You are logged in</p>}

            {/* Arrays (automatic rendering) */}
            <ul>
                {[1, 2, 3, 4, 5].map(num => (
                    <li key={num}>Number: {num}</li>
                ))}
            </ul>

            {/* Styles (inline) */}
            <p style={{ color: 'blue', fontSize: '20px' }}>
                Styled text
            </p>

            {/* className instead of class */}
            <div className="bg-gray-800 p-4 rounded">
                Tailwind classes work!
            </div>
        </div>
    );
}

export default App;

// Compare to Flutter:
// Flutter: Text('Hello ${name}')
// React:  <p>Hello {name}</p>
//
// Flutter: if (isLoggedIn) Text('Welcome')
// React:  {isLoggedIn && <p>Welcome</p>}
//
// Flutter: ListView(children: items.map((item) => Text(item)).toList())
// React:  <ul>{items.map(item => <li key={item}>{item}</li>)}</ul>
```

**JSX Rules:**
1. Must return single root element (or use Fragment `<>...</>`)
2. All tags must be closed (`<img />`, `<input />`)
3. Use `className` instead of `class`
4. Use `htmlFor` instead of `for`
5. Use camelCase for attributes (`onClick`, not `onclick`)
6. Always provide `key` prop when rendering arrays

**3. Functional Components (1.5 hours)**

Modern React uses functional components (not class components):

```typescript
// src/components/Button.tsx

import React from 'react';

// Basic component
function Button() {
    return (
        <button className="px-4 py-2 bg-blue-600 rounded hover:bg-blue-700">
            Click me
        </button>
    );
}

export default Button;

// Component with props
interface ButtonProps {
    text: string;
    variant?: 'primary' | 'secondary' | 'danger';
    onClick?: () => void;
}

function Button({ text, variant = 'primary', onClick }: ButtonProps) {
    const variantClasses = {
        primary: 'bg-blue-600 hover:bg-blue-700',
        secondary: 'bg-gray-600 hover:bg-gray-700',
        danger: 'bg-red-600 hover:bg-red-700'
    };

    return (
        <button
            className={`px-4 py-2 rounded font-bold text-white transition ${variantClasses[variant]}`}
            onClick={onClick}
        >
            {text}
        </button>
    );
}

// Usage:
// <Button text="Save" variant="primary" onClick={() => console.log('Saved')} />
```

**Component with children:**

```typescript
// src/components/Card.tsx

interface CardProps {
    children: React.ReactNode;
    title?: string;
}

function Card({ children, title }: CardProps) {
    return (
        <div className="bg-gray-800 rounded-lg p-6">
            {title && <h3 className="text-xl font-bold mb-4">{title}</h3>}
            <div>{children}</div>
        </div>
    );
}

export default Card;

// Usage:
// <Card title="Universe Details">
//     <p>This is the content</p>
//     <Button text="Edit" />
// </Card>

// Compare to Flutter:
// Flutter: Container(child: Text('Hello'))
// React:  <div>Hello</div>
//
// Flutter: Widget build(BuildContext context) { return Container(...); }
// React:  function Component() { return <div>...</div>; }
```

**4. Props and Composition (2 hours)**

Build reusable components with props:

```typescript
// src/components/UniverseCard.tsx

import { Genre } from '../types';

interface UniverseCardProps {
    id: number;
    name: string;
    genre: Genre;
    description: string;
    characterCount: number;
    onEdit: (id: number) => void;
    onDelete: (id: number) => void;
}

function UniverseCard({
    id,
    name,
    genre,
    description,
    characterCount,
    onEdit,
    onDelete
}: UniverseCardProps) {
    const genreColors: Record<Genre, string> = {
        [Genre.Fantasy]: 'bg-purple-600',
        [Genre.SciFi]: 'bg-blue-600',
        [Genre.Cyberpunk]: 'bg-cyan-600',
        [Genre.PostApocalyptic]: 'bg-orange-600',
        [Genre.Horror]: 'bg-red-600',
        [Genre.Historical]: 'bg-yellow-600'
    };

    return (
        <div className="bg-gray-800 rounded-lg overflow-hidden hover:shadow-xl transition">
            <div className="h-48 bg-gradient-to-br from-gray-700 to-gray-900 flex items-center justify-center">
                <span className="text-6xl">🌌</span>
            </div>

            <div className="p-6">
                <div className="flex justify-between items-start mb-3">
                    <h3 className="text-xl font-bold">{name}</h3>
                    <span className={`px-3 py-1 ${genreColors[genre]} rounded text-sm`}>
                        {genre}
                    </span>
                </div>

                <p className="text-gray-300 mb-4 line-clamp-3">
                    {description}
                </p>

                <div className="flex justify-between items-center">
                    <span className="text-sm text-gray-400">
                        {characterCount} characters
                    </span>

                    <div className="space-x-2">
                        <button
                            onClick={() => onEdit(id)}
                            className="px-3 py-1 text-blue-400 hover:text-blue-300"
                        >
                            Edit
                        </button>
                        <button
                            onClick={() => onDelete(id)}
                            className="px-3 py-1 text-red-400 hover:text-red-300"
                        >
                            Delete
                        </button>
                    </div>
                </div>
            </div>
        </div>
    );
}

export default UniverseCard;
```

**Composition example:**

```typescript
// src/components/Layout.tsx

import React from 'react';

interface LayoutProps {
    children: React.ReactNode;
}

function Layout({ children }: LayoutProps) {
    return (
        <div className="min-h-screen bg-gray-900 text-white">
            <Header />
            <main className="container mx-auto px-4 py-8">
                {children}
            </main>
            <Footer />
        </div>
    );
}

function Header() {
    return (
        <header className="bg-gray-800 border-b border-gray-700">
            <nav className="container mx-auto px-4 py-4">
                <div className="flex items-center justify-between">
                    <h1 className="text-2xl font-bold">Worldbuilding</h1>
                    <div className="space-x-4">
                        <a href="#" className="hover:text-blue-400">Universes</a>
                        <a href="#" className="hover:text-blue-400">Characters</a>
                        <button className="px-4 py-2 bg-blue-600 rounded hover:bg-blue-700">
                            New Universe
                        </button>
                    </div>
                </div>
            </nav>
        </header>
    );
}

function Footer() {
    return (
        <footer className="bg-gray-800 border-t border-gray-700 mt-16">
            <div className="container mx-auto px-4 py-6 text-center text-gray-400">
                <p>&copy; 2025 Worldbuilding Platform</p>
            </div>
        </footer>
    );
}

export default Layout;

// Usage:
// <Layout>
//     <h1>Welcome</h1>
//     <p>Content goes here</p>
// </Layout>
```

**5. Build Component Library (1 hour)**

Create reusable components for the worldbuilding app:

```typescript
// src/components/Input.tsx

interface InputProps {
    label: string;
    type?: 'text' | 'email' | 'password' | 'number';
    placeholder?: string;
    value: string;
    onChange: (value: string) => void;
    error?: string;
    required?: boolean;
}

function Input({
    label,
    type = 'text',
    placeholder,
    value,
    onChange,
    error,
    required
}: InputProps) {
    return (
        <div className="mb-4">
            <label className="block text-sm font-medium mb-2">
                {label}
                {required && <span className="text-red-400 ml-1">*</span>}
            </label>
            <input
                type={type}
                placeholder={placeholder}
                value={value}
                onChange={(e) => onChange(e.target.value)}
                className={`w-full px-4 py-2 bg-gray-800 border rounded focus:outline-none focus:border-blue-500 ${
                    error ? 'border-red-500' : 'border-gray-700'
                }`}
            />
            {error && <p className="text-red-400 text-sm mt-1">{error}</p>}
        </div>
    );
}

export default Input;
```

```typescript
// src/components/Select.tsx

interface SelectProps {
    label: string;
    value: string;
    onChange: (value: string) => void;
    options: { value: string; label: string }[];
}

function Select({ label, value, onChange, options }: SelectProps) {
    return (
        <div className="mb-4">
            <label className="block text-sm font-medium mb-2">{label}</label>
            <select
                value={value}
                onChange={(e) => onChange(e.target.value)}
                className="w-full px-4 py-2 bg-gray-800 border border-gray-700 rounded focus:outline-none focus:border-blue-500"
            >
                {options.map((option) => (
                    <option key={option.value} value={option.value}>
                        {option.label}
                    </option>
                ))}
            </select>
        </div>
    );
}

export default Select;
```

```typescript
// src/components/Textarea.tsx

interface TextareaProps {
    label: string;
    value: string;
    onChange: (value: string) => void;
    placeholder?: string;
    rows?: number;
}

function Textarea({ label, value, onChange, placeholder, rows = 4 }: TextareaProps) {
    return (
        <div className="mb-4">
            <label className="block text-sm font-medium mb-2">{label}</label>
            <textarea
                value={value}
                onChange={(e) => onChange(e.target.value)}
                placeholder={placeholder}
                rows={rows}
                className="w-full px-4 py-2 bg-gray-800 border border-gray-700 rounded focus:outline-none focus:border-blue-500 resize-none"
            />
        </div>
    );
}

export default Textarea;
```

**Day 5 Checkpoint:**
- [ ] Understand React component model
- [ ] Master JSX syntax and rules
- [ ] Can create functional components with TypeScript
- [ ] Understand props and prop types
- [ ] Can compose components effectively
- [ ] Built reusable component library

**Resources:**
- [React Documentation](https://react.dev) - Official docs (excellent!)
- [React TypeScript Cheatsheet](https://react-typescript-cheatsheet.netlify.app/)

---

### Day 6: React State & Events (4-6 hours)

**Learning Goals:**
- Master useState hook
- Handle events in React
- Understand controlled components
- Build interactive forms

**Compare to Flutter:**
- useState = setState in StatefulWidget
- Event handlers = onPressed callbacks
- Controlled components = TextEditingController

**Tasks:**

**1. useState Hook (1.5 hours)**

The `useState` hook lets components have state:

```typescript
import { useState } from 'react';

function Counter() {
    // Declare state variable
    const [count, setCount] = useState(0);
    //     ^^^^^ current value
    //            ^^^^^^^^ function to update
    //                             ^ initial value

    return (
        <div>
            <p>Count: {count}</p>
            <button onClick={() => setCount(count + 1)}>
                Increment
            </button>
            <button onClick={() => setCount(count - 1)}>
                Decrement
            </button>
            <button onClick={() => setCount(0)}>
                Reset
            </button>
        </div>
    );
}

// Compare to Flutter:
// Flutter:
//   int count = 0;
//   setState(() { count++; });
//
// React:
//   const [count, setCount] = useState(0);
//   setCount(count + 1);
```

**Multiple state variables:**

```typescript
function UserProfile() {
    const [name, setName] = useState("");
    const [age, setAge] = useState(0);
    const [email, setEmail] = useState("");

    return (
        <div>
            <input value={name} onChange={(e) => setName(e.target.value)} />
            <input value={age} onChange={(e) => setAge(Number(e.target.value))} type="number" />
            <input value={email} onChange={(e) => setEmail(e.target.value)} type="email" />
        </div>
    );
}
```

**State with objects:**

```typescript
interface User {
    name: string;
    email: string;
    age: number;
}

function UserForm() {
    const [user, setUser] = useState<User>({
        name: "",
        email: "",
        age: 0
    });

    // Update single property (must spread rest of object!)
    const updateName = (name: string) => {
        setUser({ ...user, name });
        // Or: setUser(prev => ({ ...prev, name }));
    };

    const updateEmail = (email: string) => {
        setUser(prev => ({ ...prev, email }));
    };

    return (
        <div>
            <input
                value={user.name}
                onChange={(e) => updateName(e.target.value)}
            />
            <input
                value={user.email}
                onChange={(e) => updateEmail(e.target.value)}
                type="email"
            />
            <p>User: {JSON.stringify(user)}</p>
        </div>
    );
}
```

**State with arrays:**

```typescript
function TodoList() {
    const [todos, setTodos] = useState<string[]>([]);
    const [input, setInput] = useState("");

    const addTodo = () => {
        if (input.trim()) {
            setTodos([...todos, input]);
            setInput("");
        }
    };

    const removeTodo = (index: number) => {
        setTodos(todos.filter((_, i) => i !== index));
    };

    return (
        <div>
            <input
                value={input}
                onChange={(e) => setInput(e.target.value)}
                onKeyPress={(e) => e.key === 'Enter' && addTodo()}
            />
            <button onClick={addTodo}>Add</button>

            <ul>
                {todos.map((todo, index) => (
                    <li key={index}>
                        {todo}
                        <button onClick={() => removeTodo(index)}>Delete</button>
                    </li>
                ))}
            </ul>
        </div>
    );
}
```

**2. Event Handling (1 hour)**

React events are camelCase (onClick, onChange, onSubmit):

```typescript
function EventExamples() {
    // Click events
    const handleClick = () => {
        console.log('Clicked!');
    };

    // Click with parameter
    const handleClickWithParam = (id: number) => {
        console.log(`Clicked item ${id}`);
    };

    // Mouse events
    const handleMouseEnter = () => console.log('Mouse entered');
    const handleMouseLeave = () => console.log('Mouse left');

    // Keyboard events
    const handleKeyDown = (e: React.KeyboardEvent) => {
        if (e.key === 'Enter') {
            console.log('Enter pressed');
        }
    };

    // Form events
    const handleSubmit = (e: React.FormEvent) => {
        e.preventDefault();  // Prevent page reload
        console.log('Form submitted');
    };

    // Input events
    const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
        console.log('Input changed:', e.target.value);
    };

    return (
        <div>
            <button onClick={handleClick}>Click me</button>

            <button onClick={() => handleClickWithParam(42)}>
                Click with param
            </button>

            <div
                onMouseEnter={handleMouseEnter}
                onMouseLeave={handleMouseLeave}
                className="p-4 bg-gray-800"
            >
                Hover me
            </div>

            <input
                onKeyDown={handleKeyDown}
                onChange={handleChange}
                placeholder="Type something"
            />

            <form onSubmit={handleSubmit}>
                <button type="submit">Submit</button>
            </form>
        </div>
    );
}
```

**3. Controlled Components (1.5 hours)**

In React, form inputs are "controlled" by state:

```typescript
// src/components/UniverseForm.tsx

import { useState } from 'react';
import { Genre } from '../types';
import Input from './Input';
import Select from './Select';
import Textarea from './Textarea';

interface UniverseFormData {
    name: string;
    genre: Genre;
    description: string;
    hasMagic: boolean;
    technologyLevel: number;
}

interface UniverseFormProps {
    onSubmit: (data: UniverseFormData) => void;
    onCancel: () => void;
}

function UniverseForm({ onSubmit, onCancel }: UniverseFormProps) {
    const [formData, setFormData] = useState<UniverseFormData>({
        name: "",
        genre: Genre.Fantasy,
        description: "",
        hasMagic: false,
        technologyLevel: 5
    });

    const [errors, setErrors] = useState<Partial<Record<keyof UniverseFormData, string>>>({});

    // Generic update function
    const updateField = <K extends keyof UniverseFormData>(
        field: K,
        value: UniverseFormData[K]
    ) => {
        setFormData(prev => ({ ...prev, [field]: value }));
        // Clear error when field is updated
        if (errors[field]) {
            setErrors(prev => ({ ...prev, [field]: undefined }));
        }
    };

    const validate = (): boolean => {
        const newErrors: Partial<Record<keyof UniverseFormData, string>> = {};

        if (!formData.name.trim()) {
            newErrors.name = "Name is required";
        }

        if (!formData.description.trim()) {
            newErrors.description = "Description is required";
        }

        if (formData.description.length < 20) {
            newErrors.description = "Description must be at least 20 characters";
        }

        setErrors(newErrors);
        return Object.keys(newErrors).length === 0;
    };

    const handleSubmit = (e: React.FormEvent) => {
        e.preventDefault();

        if (validate()) {
            onSubmit(formData);
        }
    };

    return (
        <form onSubmit={handleSubmit} className="max-w-2xl mx-auto">
            <h2 className="text-2xl font-bold mb-6">Create New Universe</h2>

            <Input
                label="Universe Name"
                value={formData.name}
                onChange={(value) => updateField('name', value)}
                placeholder="e.g., Cyberpunk 2199"
                error={errors.name}
                required
            />

            <Select
                label="Genre"
                value={formData.genre}
                onChange={(value) => updateField('genre', value as Genre)}
                options={Object.values(Genre).map(genre => ({
                    value: genre,
                    label: genre
                }))}
            />

            <Textarea
                label="Description"
                value={formData.description}
                onChange={(value) => updateField('description', value)}
                placeholder="Describe your universe..."
                rows={6}
            />
            {errors.description && (
                <p className="text-red-400 text-sm -mt-3 mb-4">{errors.description}</p>
            )}

            <div className="mb-4">
                <label className="flex items-center space-x-2 cursor-pointer">
                    <input
                        type="checkbox"
                        checked={formData.hasMagic}
                        onChange={(e) => updateField('hasMagic', e.target.checked)}
                        className="w-4 h-4"
                    />
                    <span>This universe has magic</span>
                </label>
            </div>

            <div className="mb-6">
                <label className="block text-sm font-medium mb-2">
                    Technology Level: {formData.technologyLevel}
                </label>
                <input
                    type="range"
                    min="1"
                    max="10"
                    value={formData.technologyLevel}
                    onChange={(e) => updateField('technologyLevel', Number(e.target.value))}
                    className="w-full"
                />
                <div className="flex justify-between text-xs text-gray-400 mt-1">
                    <span>Primitive</span>
                    <span>Advanced</span>
                </div>
            </div>

            <div className="flex space-x-4">
                <button
                    type="submit"
                    className="flex-1 py-3 bg-blue-600 hover:bg-blue-700 rounded font-bold transition"
                >
                    Create Universe
                </button>
                <button
                    type="button"
                    onClick={onCancel}
                    className="flex-1 py-3 bg-gray-700 hover:bg-gray-600 rounded font-bold transition"
                >
                    Cancel
                </button>
            </div>
        </form>
    );
}

export default UniverseForm;
```

**4. Build Interactive Universe Creator (2 hours)**

Put it all together in the main App:

```typescript
// src/App.tsx

import { useState } from 'react';
import Layout from './components/Layout';
import UniverseCard from './components/UniverseCard';
import UniverseForm from './components/UniverseForm';
import { Genre, Universe } from './types';

function App() {
    const [universes, setUniverses] = useState<Universe[]>([]);
    const [showForm, setShowForm] = useState(false);

    const handleCreateUniverse = (formData: any) => {
        const newUniverse: Universe = {
            id: Date.now(),
            ...formData,
            ownerId: 1,  // Mock user ID
            settings: {
                hasMagic: formData.hasMagic,
                technologyLevel: formData.technologyLevel,
                themes: [],
                rules: []
            },
            createdAt: new Date(),
            updatedAt: new Date()
        };

        setUniverses([...universes, newUniverse]);
        setShowForm(false);
    };

    const handleEditUniverse = (id: number) => {
        console.log('Edit universe:', id);
        // TODO: Implement edit
    };

    const handleDeleteUniverse = (id: number) => {
        if (confirm('Are you sure you want to delete this universe?')) {
            setUniverses(universes.filter(u => u.id !== id));
        }
    };

    return (
        <Layout>
            {showForm ? (
                <UniverseForm
                    onSubmit={handleCreateUniverse}
                    onCancel={() => setShowForm(false)}
                />
            ) : (
                <>
                    <div className="flex justify-between items-center mb-8">
                        <h1 className="text-3xl font-bold">Your Universes</h1>
                        <button
                            onClick={() => setShowForm(true)}
                            className="px-6 py-3 bg-blue-600 hover:bg-blue-700 rounded font-bold transition"
                        >
                            + New Universe
                        </button>
                    </div>

                    {universes.length === 0 ? (
                        <div className="text-center py-16">
                            <p className="text-xl text-gray-400 mb-4">
                                No universes created yet
                            </p>
                            <button
                                onClick={() => setShowForm(true)}
                                className="px-6 py-3 bg-blue-600 hover:bg-blue-700 rounded font-bold transition"
                            >
                                Create Your First Universe
                            </button>
                        </div>
                    ) : (
                        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                            {universes.map(universe => (
                                <UniverseCard
                                    key={universe.id}
                                    id={universe.id}
                                    name={universe.name}
                                    genre={universe.genre}
                                    description={universe.description}
                                    characterCount={0}  // TODO: Calculate
                                    onEdit={handleEditUniverse}
                                    onDelete={handleDeleteUniverse}
                                />
                            ))}
                        </div>
                    )}
                </>
            )}
        </Layout>
    );
}

export default App;
```

**Day 6 Checkpoint:**
- [ ] Master useState hook
- [ ] Handle events in React
- [ ] Understand controlled components
- [ ] Can build complex interactive forms
- [ ] Built universe creator with validation
- [ ] Understand state management patterns

---

### Day 7: Week 1 Project (4-6 hours)

**Project Goal:**
Build a complete "Universe Creator" UI with:
- Multi-page navigation
- Universe creation and management
- Character creation (basic)
- LocalStorage persistence
- Responsive design

This consolidates everything from Week 1!

**Tasks:**

**1. Project Structure (30 minutes)**

Organize your components:

```
src/
├── components/
│   ├── common/
│   │   ├── Button.tsx
│   │   ├── Card.tsx
│   │   ├── Input.tsx
│   │   ├── Select.tsx
│   │   └── Textarea.tsx
│   ├── layout/
│   │   ├── Layout.tsx
│   │   ├── Header.tsx
│   │   └── Footer.tsx
│   ├── universe/
│   │   ├── UniverseCard.tsx
│   │   ├── UniverseForm.tsx
│   │   └── UniverseList.tsx
│   └── character/
│       ├── CharacterCard.tsx
│       └── CharacterForm.tsx
├── hooks/
│   └── useLocalStorage.ts
├── types/
│   └── index.ts
├── utils/
│   └── storage.ts
├── App.tsx
└── main.tsx
```

**2. LocalStorage Hook (1 hour)**

Create a reusable hook for persistent state:

```typescript
// src/hooks/useLocalStorage.ts

import { useState, useEffect } from 'react';

export function useLocalStorage<T>(key: string, initialValue: T) {
    // Get initial value from localStorage or use provided default
    const [storedValue, setStoredValue] = useState<T>(() => {
        try {
            const item = window.localStorage.getItem(key);
            return item ? JSON.parse(item) : initialValue;
        } catch (error) {
            console.error(`Error loading ${key} from localStorage:`, error);
            return initialValue;
        }
    });

    // Update localStorage when value changes
    useEffect(() => {
        try {
            window.localStorage.setItem(key, JSON.stringify(storedValue));
        } catch (error) {
            console.error(`Error saving ${key} to localStorage:`, error);
        }
    }, [key, storedValue]);

    return [storedValue, setStoredValue] as const;
}
```

**3. Character Management (2 hours)**

Add character creation to the app:

```typescript
// src/components/character/CharacterForm.tsx

import { useState } from 'react';
import { Character, CreateCharacterInput } from '../../types';
import Input from '../common/Input';
import Textarea from '../common/Textarea';

interface CharacterFormProps {
    universeId: number;
    onSubmit: (data: CreateCharacterInput) => void;
    onCancel: () => void;
}

function CharacterForm({ universeId, onSubmit, onCancel }: CharacterFormProps) {
    const [formData, setFormData] = useState({
        name: "",
        role: "",
        description: "",
        age: undefined as number | undefined,
        species: "",
        occupation: ""
    });

    const handleSubmit = (e: React.FormEvent) => {
        e.preventDefault();

        const characterData: CreateCharacterInput = {
            universeId,
            name: formData.name,
            role: formData.role,
            description: formData.description,
            attributes: {
                age: formData.age,
                species: formData.species,
                occupation: formData.occupation,
                skills: [],
                personality: [],
                background: formData.description
            }
        };

        onSubmit(characterData);
    };

    return (
        <form onSubmit={handleSubmit} className="max-w-2xl mx-auto">
            <h2 className="text-2xl font-bold mb-6">Create Character</h2>

            <Input
                label="Character Name"
                value={formData.name}
                onChange={(value) => setFormData({ ...formData, name: value })}
                placeholder="e.g., John Doe"
                required
            />

            <Input
                label="Role"
                value={formData.role}
                onChange={(value) => setFormData({ ...formData, role: value })}
                placeholder="e.g., Protagonist, Antagonist, Supporting"
                required
            />

            <div className="grid grid-cols-1 md:grid-cols-3 gap-4 mb-4">
                <Input
                    label="Age"
                    type="number"
                    value={formData.age?.toString() || ""}
                    onChange={(value) => setFormData({ ...formData, age: Number(value) || undefined })}
                    placeholder="25"
                />

                <Input
                    label="Species"
                    value={formData.species}
                    onChange={(value) => setFormData({ ...formData, species: value })}
                    placeholder="Human"
                />

                <Input
                    label="Occupation"
                    value={formData.occupation}
                    onChange={(value) => setFormData({ ...formData, occupation: value })}
                    placeholder="Hacker"
                />
            </div>

            <Textarea
                label="Description"
                value={formData.description}
                onChange={(value) => setFormData({ ...formData, description: value })}
                placeholder="Describe your character..."
                rows={6}
            />

            <div className="flex space-x-4">
                <button
                    type="submit"
                    className="flex-1 py-3 bg-blue-600 hover:bg-blue-700 rounded font-bold transition"
                >
                    Create Character
                </button>
                <button
                    type="button"
                    onClick={onCancel}
                    className="flex-1 py-3 bg-gray-700 hover:bg-gray-600 rounded font-bold transition"
                >
                    Cancel
                </button>
            </div>
        </form>
    );
}

export default CharacterForm;
```

**4. Enhanced App with Navigation (2.5 hours)**

Add simple client-side routing (without React Router for now):

```typescript
// src/App.tsx

import { useState } from 'react';
import { useLocalStorage } from './hooks/useLocalStorage';
import Layout from './components/layout/Layout';
import UniverseCard from './components/universe/UniverseCard';
import UniverseForm from './components/universe/UniverseForm';
import CharacterForm from './components/character/CharacterForm';
import { Universe, Character, CreateCharacterInput } from './types';

type View = 'list' | 'create-universe' | 'universe-detail' | 'create-character';

function App() {
    const [universes, setUniverses] = useLocalStorage<Universe[]>('universes', []);
    const [characters, setCharacters] = useLocalStorage<Character[]>('characters', []);
    const [currentView, setCurrentView] = useState<View>('list');
    const [selectedUniverseId, setSelectedUniverseId] = useState<number | null>(null);

    const selectedUniverse = universes.find(u => u.id === selectedUniverseId);
    const universeCharacters = characters.filter(c => c.universeId === selectedUniverseId);

    const handleCreateUniverse = (formData: any) => {
        const newUniverse: Universe = {
            id: Date.now(),
            ...formData,
            ownerId: 1,
            settings: {
                hasMagic: formData.hasMagic,
                technologyLevel: formData.technologyLevel,
                themes: [],
                rules: []
            },
            createdAt: new Date(),
            updatedAt: new Date()
        };

        setUniverses([...universes, newUniverse]);
        setCurrentView('list');
    };

    const handleDeleteUniverse = (id: number) => {
        if (confirm('Delete this universe? This will also delete all characters.')) {
            setUniverses(universes.filter(u => u.id !== id));
            setCharacters(characters.filter(c => c.universeId !== id));
        }
    };

    const handleViewUniverse = (id: number) => {
        setSelectedUniverseId(id);
        setCurrentView('universe-detail');
    };

    const handleCreateCharacter = (data: CreateCharacterInput) => {
        const newCharacter: Character = {
            id: Date.now(),
            ...data,
            createdAt: new Date(),
            updatedAt: new Date()
        };

        setCharacters([...characters, newCharacter]);
        setCurrentView('universe-detail');
    };

    const handleDeleteCharacter = (id: number) => {
        if (confirm('Delete this character?')) {
            setCharacters(characters.filter(c => c.id !== id));
        }
    };

    return (
        <Layout>
            {/* Navigation breadcrumb */}
            <div className="mb-6 text-sm text-gray-400">
                <button onClick={() => setCurrentView('list')} className="hover:text-blue-400">
                    Home
                </button>
                {selectedUniverse && (
                    <>
                        <span className="mx-2">/</span>
                        <span>{selectedUniverse.name}</span>
                    </>
                )}
            </div>

            {currentView === 'list' && (
                <>
                    <div className="flex justify-between items-center mb-8">
                        <h1 className="text-3xl font-bold">Your Universes</h1>
                        <button
                            onClick={() => setCurrentView('create-universe')}
                            className="px-6 py-3 bg-blue-600 hover:bg-blue-700 rounded font-bold transition"
                        >
                            + New Universe
                        </button>
                    </div>

                    {universes.length === 0 ? (
                        <div className="text-center py-16">
                            <p className="text-xl text-gray-400 mb-4">
                                No universes created yet
                            </p>
                            <button
                                onClick={() => setCurrentView('create-universe')}
                                className="px-6 py-3 bg-blue-600 hover:bg-blue-700 rounded font-bold transition"
                            >
                                Create Your First Universe
                            </button>
                        </div>
                    ) : (
                        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                            {universes.map(universe => (
                                <div key={universe.id} onClick={() => handleViewUniverse(universe.id)} className="cursor-pointer">
                                    <UniverseCard
                                        id={universe.id}
                                        name={universe.name}
                                        genre={universe.genre}
                                        description={universe.description}
                                        characterCount={characters.filter(c => c.universeId === universe.id).length}
                                        onEdit={() => {}}
                                        onDelete={handleDeleteUniverse}
                                    />
                                </div>
                            ))}
                        </div>
                    )}
                </>
            )}

            {currentView === 'create-universe' && (
                <UniverseForm
                    onSubmit={handleCreateUniverse}
                    onCancel={() => setCurrentView('list')}
                />
            )}

            {currentView === 'universe-detail' && selectedUniverse && (
                <>
                    <div className="mb-8">
                        <div className="flex justify-between items-start mb-4">
                            <div>
                                <h1 className="text-3xl font-bold mb-2">{selectedUniverse.name}</h1>
                                <span className="inline-block px-3 py-1 bg-blue-600 rounded text-sm">
                                    {selectedUniverse.genre}
                                </span>
                            </div>
                            <button
                                onClick={() => setCurrentView('create-character')}
                                className="px-6 py-3 bg-blue-600 hover:bg-blue-700 rounded font-bold transition"
                            >
                                + Add Character
                            </button>
                        </div>
                        <p className="text-gray-300 text-lg">{selectedUniverse.description}</p>

                        <div className="grid grid-cols-2 md:grid-cols-4 gap-4 mt-6">
                            <div className="bg-gray-800 rounded-lg p-4">
                                <div className="text-2xl font-bold">{universeCharacters.length}</div>
                                <div className="text-sm text-gray-400">Characters</div>
                            </div>
                            <div className="bg-gray-800 rounded-lg p-4">
                                <div className="text-2xl font-bold">{selectedUniverse.settings.technologyLevel}</div>
                                <div className="text-sm text-gray-400">Tech Level</div>
                            </div>
                            <div className="bg-gray-800 rounded-lg p-4">
                                <div className="text-2xl font-bold">{selectedUniverse.settings.hasMagic ? 'Yes' : 'No'}</div>
                                <div className="text-sm text-gray-400">Magic</div>
                            </div>
                            <div className="bg-gray-800 rounded-lg p-4">
                                <div className="text-2xl font-bold">0</div>
                                <div className="text-sm text-gray-400">Stories</div>
                            </div>
                        </div>
                    </div>

                    <h2 className="text-2xl font-bold mb-4">Characters</h2>
                    {universeCharacters.length === 0 ? (
                        <div className="text-center py-8 bg-gray-800 rounded-lg">
                            <p className="text-gray-400 mb-4">No characters yet</p>
                            <button
                                onClick={() => setCurrentView('create-character')}
                                className="px-6 py-3 bg-blue-600 hover:bg-blue-700 rounded font-bold transition"
                            >
                                Create First Character
                            </button>
                        </div>
                    ) : (
                        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                            {universeCharacters.map(character => (
                                <div key={character.id} className="bg-gray-800 rounded-lg p-4">
                                    <div className="flex justify-between items-start mb-2">
                                        <h3 className="text-lg font-bold">{character.name}</h3>
                                        <button
                                            onClick={() => handleDeleteCharacter(character.id)}
                                            className="text-red-400 hover:text-red-300 text-sm"
                                        >
                                            Delete
                                        </button>
                                    </div>
                                    <p className="text-sm text-blue-400 mb-2">{character.role}</p>
                                    <p className="text-sm text-gray-300 line-clamp-3">{character.description}</p>
                                    {character.attributes.age && (
                                        <p className="text-xs text-gray-400 mt-2">Age: {character.attributes.age}</p>
                                    )}
                                </div>
                            ))}
                        </div>
                    )}
                </>
            )}

            {currentView === 'create-character' && selectedUniverseId && (
                <CharacterForm
                    universeId={selectedUniverseId}
                    onSubmit={handleCreateCharacter}
                    onCancel={() => setCurrentView('universe-detail')}
                />
            )}
        </Layout>
    );
}

export default App;
```

**Week 1 Final Checkpoint:**
- [ ] Complete universe creation and management
- [ ] Character creation and listing
- [ ] LocalStorage persistence (data survives page refresh)
- [ ] Simple navigation between views
- [ ] Responsive design works on mobile and desktop
- [ ] Comfortable with React fundamentals
- [ ] Can build interactive UIs with forms

**Celebrate!** You've completed Week 1 and built a functional React application!

---

## Week 1 Summary & Review

**What You've Learned:**
✓ HTML5 semantic structure
✓ CSS layouts with Tailwind CSS (Flexbox, Grid, responsive design)
✓ JavaScript ES6+ (async/await, destructuring, array methods)
✓ TypeScript type system (interfaces, generics, utility types)
✓ React fundamentals (components, JSX, props, state, events)
✓ Building reusable component libraries
✓ Form handling and validation
✓ LocalStorage for persistence

**Project Completed:**
✓ Universe Creator application with:
  - Create/delete universes
  - Create/delete characters
  - Multiple views with navigation
  - Persistent storage
  - Responsive design

**Next Week Preview:**
Week 2 will dive deeper into React with:
- useEffect for side effects
- React Router for proper routing
- Context API for state management
- React Hook Form for advanced forms
- Custom hooks
- Performance optimization

---

## Teaching Guidelines for Claude (Week 1)

### Core Teaching Principles

**1. Explain Before Implementing**
- NEVER write code without explaining what each component does first
- Break down every file, command, and concept step-by-step
- Use visual diagrams and comparisons to existing knowledge (Rust/Python/Flutter)
- Answer "What is this?" and "Why do we need this?" before showing code

**2. Interactive Learning Approach**
- After explaining concepts, create working examples
- Provide interactive playgrounds for experimentation (like flexbox-demo.html)
- Encourage the learner to modify code and observe results
- Use browser DevTools for live exploration

**3. Challenge-Based Practice**
- After each major concept, provide coding challenges
- Start with guided challenges (fill in the blanks)
- Progress to open-ended challenges (build X feature)
- Include solutions with detailed explanations

**4. Verify Understanding**
- Ask questions to test comprehension before moving on
- Examples: "What does npm install do?", "What's the difference between flex and grid?"
- Don't proceed until core concepts are solid
- Encourage learner to explain concepts back in their own words

**5. Build Progressively**
- Start with simplest possible examples
- Add complexity incrementally
- Each new feature builds on previous knowledge
- Regular checkpoints: "Can you do X without looking?"

### Example Teaching Flow

**Bad Approach (Don't do this):**
```
Claude: Let me create the project for you.
[Runs 10 commands]
[Creates 5 files]
Claude: Done! Your app is ready.
```

**Good Approach (Do this):**
```
Claude: We're going to create a web project. First, let me explain what each tool does:

1. Node.js - This is like Rust's runtime, it runs JavaScript on your computer...
2. npm - This is like cargo, it manages packages...
3. Vite - This is a build tool that...

Now let's run the first command: npm create vite...
[Explains what the command does]
[Shows the output]
[Explains what files were created and why]

Here's what package.json does (like Cargo.toml in Rust)...
[Shows file contents]
[Explains each section]

Now let's look at the HTML we created...
[Breaks down each element]
[Explains Tailwind classes one by one]

Challenge: Can you add another section to the page?
```

### Comparisons to Leverage

**Always relate new concepts to existing knowledge:**

| New Concept | Compare To |
|-------------|------------|
| npm | cargo (Rust), pip (Python) |
| package.json | Cargo.toml (Rust), pubspec.yaml (Flutter) |
| React components | Flutter widgets, Rust structs |
| Props | Flutter widget parameters, function arguments |
| useState | Flutter setState, mutable variables |
| JSX | Flutter widget tree, HTML-like syntax |
| TypeScript types | Rust type system, Python type hints |
| JavaScript async | Rust async/await, Python asyncio |
| Flexbox row | Flutter Row widget |
| Tailwind classes | Flutter widget properties |

### Challenge Templates

**After Explaining Flexbox:**
```markdown
Challenge 1 (Easy): Create a navigation bar with logo on left, links on right
Challenge 2 (Medium): Create a card with header, content, and footer
Challenge 3 (Hard): Build a responsive sidebar layout

Provide hints, then solutions with explanations.
```

**After Explaining Tailwind:**
```markdown
Challenge 1: Change the color scheme from blue to green
Challenge 2: Make the hero section taller
Challenge 3: Add a new feature card with hover effects

Show before/after code with class explanations.
```

### Common Pitfalls to Watch For

**Technical:**
1. **Forgetting keys in lists** - Always add `key` prop when mapping arrays
2. **Mutating state directly** - Must use setState, not `state.x = y`
3. **Not using previous state** - Use `setState(prev => ...)` for state that depends on previous value
4. **== vs ===** - Always use === in JavaScript
5. **Async setState** - setState is async, don't rely on immediate updates
6. **CSS class naming** - It's `className` not `class` in JSX
7. **Closing tags** - All tags must be closed in JSX: `<img />`, `<input />`

**Learning Process:**
1. **Moving too fast** - Stop and verify understanding frequently
2. **Skipping explanations** - Never assume knowledge, always explain
3. **No practice** - Code without practice is forgotten quickly
4. **No debugging practice** - Teach how to debug, not just how to write code

### Debugging Teaching

**When errors occur:**
1. Show the error message
2. Explain what it means in plain English
3. Compare to similar errors in Rust/Python if applicable
4. Walk through debugging steps
5. Explain the solution
6. Show how to prevent it in future

**Example:**
```
Error: "Cannot read property 'map' of undefined"

This is like a NullPointerException in other languages.
In Rust, you'd have Option<Vec<T>> and the compiler would force you to handle None.
In JavaScript, undefined propagates and fails at usage time.

Solution: Check if the array exists first:
{items && items.map(...)}
or
{items?.map(...)}  // Optional chaining
```

### Encouragement & Motivation

- **Week 1 is foundation** - It gets more fun from here!
- **Building real features** (real-time collab) comes in weeks 3-4
- **The learning curve is steepest** in week 1-2, then accelerates
- **Every expert started here** - Confusion is part of learning
- **Hands-on practice** beats reading every time
- **Make mistakes** - They're the best teachers

### Progress Checkpoints

**End of Day 1:**
- Can explain what Node.js, npm, Vite, and Tailwind do
- Understands HTML semantic elements
- Can use basic Tailwind classes
- Understands Flexbox layout
- Can modify existing HTML/CSS code

**End of Week 1:**
- Can build responsive layouts from scratch
- Comfortable with JavaScript ES6+ syntax
- Understands TypeScript types
- Can create React components
- Understands state and events
- Has built multiple small projects

### Interactive Elements to Include

1. **Live Demos** - Create playground files (like flexbox-demo.html)
2. **Before/After Comparisons** - Show code evolution
3. **Visual Diagrams** - ASCII art for layouts, data flow
4. **Code Annotations** - Inline comments explaining every line
5. **Quiz Questions** - Test understanding before moving on
6. **Debugging Exercises** - Provide broken code to fix

### Resources to Reference

**When teaching concepts, point to:**
- Official documentation (MDN, React.dev, etc.)
- Specific sections to read for deeper understanding
- Visual guides and tutorials
- Comparison articles (e.g., "Flexbox vs Grid")

**Create custom resources:**
- Cheatsheets for common patterns
- Quick reference guides
- Annotated example code
- Practice challenges with solutions

---

# Weeks 2-6 Content Continues...

(The document continues with detailed day-by-day breakdowns for Weeks 2-6, following the same structure. Each week builds on the previous, progressively adding features to the capstone project while teaching new concepts.)

---

## Progress Tracking

### Daily Progress Log

| Day | Date | Topics Covered | Projects Built | Hours | Notes |
|-----|------|----------------|----------------|-------|-------|
| 1   | Nov 4, 2025 | HTML5, CSS/Tailwind, Flexbox, Vite setup | Landing page, Flexbox demo | 4-6 | Complete ✅ |
| 2   |      |                |                |       |       |
| ... |      |                |                |       |       |

### Weekly Milestones

- [ ] Week 1: Interactive UI with forms ✓
- [ ] Week 2: Multi-page app with routing
- [ ] Week 3: Full-stack CRUD application
- [ ] Week 4: Real-time collaborative editor
- [ ] Week 5: Core platform features complete
- [ ] Week 6: Production MVP deployed

### Skills Checklist

**Frontend:**
- [x] HTML/CSS proficiency
- [ ] JavaScript/TypeScript fluency
- [ ] React component development
- [ ] State management
- [ ] Routing
- [ ] Forms and validation
- [ ] Real-time UI updates

**Backend:**
- [ ] Rust/Axum API development
- [ ] PostgreSQL and SQL
- [ ] WebSocket implementation
- [ ] Authentication integration
- [ ] API design

**DevOps:**
- [ ] Docker containerization
- [ ] Deployment to cloud platforms
- [ ] Environment configuration
- [ ] CI/CD basics

---

## Resources

### Documentation
- [MDN Web Docs](https://developer.mozilla.org) - HTML/CSS/JS reference
- [React.dev](https://react.dev) - Official React documentation
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [Tailwind CSS](https://tailwindcss.com/docs)
- [Axum Documentation](https://docs.rs/axum/latest/axum/)

### Tools
- [VS Code](https://code.visualstudio.com/)
- [Node.js](https://nodejs.org/)
- [Rust](https://www.rust-lang.org/)
- [PostgreSQL](https://www.postgresql.org/)

### Community
- [React Discord](https://discord.gg/react)
- [Rust Discord](https://discord.gg/rust-lang)
- [Stack Overflow](https://stackoverflow.com/)

---

## Appendix: Concept Mappings

### Rust → TypeScript

| Rust | TypeScript |
|------|------------|
| `struct User { name: String }` | `interface User { name: string }` |
| `enum Result<T, E>` | `type Result<T> = Success<T> \| Error` |
| `Option<T>` | `T \| undefined` or `T \| null` |
| `fn foo(x: i32) -> i32` | `function foo(x: number): number` |
| `impl Trait for Type` | `interface Type extends Trait` |
| Ownership/borrowing | Garbage collection (no equivalent) |
| `.await` | `await` |
| `match` | `switch` or `if/else` |

### Python → JavaScript

| Python | JavaScript |
|--------|------------|
| `def foo(x):` | `function foo(x) {` or `const foo = (x) =>` |
| `x = 5` | `let x = 5` or `const x = 5` |
| `[x for x in list]` | `list.map(x => x)` |
| `if x in list:` | `if (list.includes(x))` |
| `with open(...) as f:` | `try/finally` or async with streams |
| `import module` | `import module from 'module'` |

### Flutter → React

| Flutter | React |
|---------|-------|
| `Widget build(BuildContext context)` | `function Component() { return <div>...</div> }` |
| `StatefulWidget` + `setState()` | `useState()` hook |
| `Text('Hello ${name}')` | `<p>Hello {name}</p>` |
| `Container(child: ...)` | `<div>...</div>` |
| `ListView(children: [...])` | `<ul>{items.map(...)}</ul>` |
| `TextEditingController` | Controlled components with `value`/`onChange` |
| `Provider` | Context API or state management |

---

**End of claude.md**

This document will be continuously updated as you progress through the curriculum.
