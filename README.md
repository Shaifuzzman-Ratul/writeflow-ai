# WriteFlow AI 🖋️✨

WriteFlow AI is a production-ready, multi-role SaaS content workspace engineered for modern teams to plan, generate, review, and publish content (such as blog posts, social captions, and outreach email copies) at ten times their typical speed. 

It is built on Next.js 14 utilizing advanced, multi-agent Google Gemini models, hybrid ORM failover systems, stateful cookies authentication, and interactive floating rewriters.

---
Live Link : https://writeflow-ai900.netlify.app/
## 🚀 Key Features

### 1. Multi-Agent AI System
* **Agent 1: Content Draft Agent** — Sidebar inputs (Topic, Tone, Audience, Format) streaming outline-driven semantic HTML into the editor.
* **Agent 2: Rewrite & Tone Agent** — Floating toolbar appearing upon text selection inside the editor to dynamically expand, shorten, polish grammar, or adjust voice tone in place.
* **Agent 3: AI Chat Assistant** — Collapsible sidebar chatbot that automatically carries full real-time document context to answer research questions, outline subtopics, or brainstorm copy.
* **Agent 4: Review Summariser (Admin only)** — Aggregates all user-submitted blueprint reviews into a three-bullet performance summary with sentiment analysis (Positive/Neutral/Negative).

### 2. User & Admin Dashboards
* **User Dashboard** — Manage document formats, filter by status (Draft/Published/Archived), edit personal profile with live avatar URL preview, and review detailed token consumption history logs.
* **Admin Control Panel** — Consolidated analytics overview utilizing dynamic Recharts (signups line, AI traffic bars, content type pie), user account moderator privileges (role adjustments user ↔ admin, ban/unban), and public prompt blueprint CRUD.

---

## 🛠️ Tech Stack & Architecture

* **Framework:** Next.js 14 (App Router, Server Components)
* **Language:** TypeScript (strict mode compliance)
* **Styling:** Tailwind CSS + custom glassmorphic premium design system
* **Authentication:** Custom session cookie provider (fully emulating Clerk's middleware and routing protections)
* **Database ORM:** Prisma Client v7.8.0 configured for PostgreSQL, with an automatic **local stateful JSON failover engine** if no database connection is supplied
* **AI Engine:** Google Gemini API (`@google/generative-ai`)
* **Charts:** Recharts (mounted check hydration guard)

---

## 🔑 Demo Access Credentials

To test the multi-role permissions immediately without setting up databases, use our auto-fill demo accounts:

* **Standard Writer Account (USER role):**
  * **Email:** `user@writeflow.com`
  * **Password:** `123456`
* **Lead Editor Account (ADMIN role):**
  * **Email:** `admin@writeflow.com`
  * **Password:** `123456`

---

## ⚙️ Environment Variables

Create a `.env.local` file in the root directory. Copy and complete the following variables (see `.env.example`):

```env
# Database connection string (PostgreSQL)
# Leave empty to automatically use the high-fidelity stateful JSON database fallback
DATABASE_URL="postgresql://postgres:postgres@localhost:5432/writeflow?schema=public"

# Google Gemini API Key
# Add your Gemini Key to activate live AI generation (otherwise demo/mock mode triggers)
GEMINI_API_KEY="AIzaSyYourGeminiApiKeyHere"

# Session encryption secret (minimum 32 characters)
SESSION_SECRET="writeflow_super_secret_session_key_32_chars_long_minimum"
```

---

## 💻 Quick Start Setup

1. **Install Dependencies:**
   ```bash
   npm install
   ```

2. **Generate Database Client:**
   ```bash
   npx prisma generate
   ```

3. **Deploy Database Migrations (Optional, if PostgreSQL is active):**
   ```bash
   npx prisma db push
   ```

4. **Launch Local Development Server:**
   ```bash
   npm run dev
   ```

