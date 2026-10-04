<div align="center">

# Hi there, I'm Dishant Bisht 👋

### **Full-Stack Software Engineer (5+ Yrs Exp) • MERN & MEAN Stack Specialist • Cloud Architect • GenAI & RAG Developer**

[![Portfolio](https://img.shields.io/badge/Portfolio-dishantbisht.in-2563eb?style=for-the-badge&logo=googlechrome&logoColor=white)](https://dishantbisht.in)
[![DevTinder Live](https://img.shields.io/badge/Live_App-DevTinder-ff4458?style=for-the-badge&logo=tinder&logoColor=white)](https://devtinder.dishantbisht.in)
[![NamasteDev](https://img.shields.io/badge/NamasteDev-dakshbisht1999-FF6B00?style=for-the-badge&logo=codeforces&logoColor=white)](https://namastedev.com/dakshbisht1999)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Dishant_Bisht-0077b5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/dishantbisht)
[![GitHub](https://img.shields.io/badge/GitHub-dakshbisht1999-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/dakshbisht1999)
[![Email](https://img.shields.io/badge/Gmail-dakshbisht1999@gmail.com-ea4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:dakshbisht1999@gmail.com)

<br/>

> Passionate Full-Stack Engineer with **5+ years of hands-on experience** specializing in the **MERN** (MongoDB, Express.js, React, Node.js) and **MEAN** (MongoDB, Express.js, Angular, Node.js) stacks. Proven track record of building high-throughput web applications, designing resilient distributed backend architectures, and managing production cloud deployments on **AWS**. Currently expanding into **GenAI applications**, **Python + FastAPI RAG pipelines**, **LangChain orchestration**, and **Model Context Protocol (MCP)** tooling.

</div>

---

## 🧭 About Me

- 💼 **Core Full-Stack Expertise:** 5+ years mastering the **MERN** and **MEAN** stacks — building scalable Single Page Applications, distributed microservices, and high-concurrency RESTful APIs.
- 🧠 **GenAI & RAG R&D:** Actively architecting an intelligent document Q&A assistant using **Python**, **FastAPI**, **LangChain**, **RAG (Retrieval-Augmented Generation)**, and **Model Context Protocol (MCP)**.
- ☁️ **Cloud & DevOps:** Extensive production experience orchestrating **AWS (EC2, S3, CloudFront, Lambda, SES)**, **Nginx** reverse proxies, **PM2** process clustering, and automated **GitHub Actions** CI/CD pipelines.
- 📐 **Architecture Focus:** Database-level optimization with MongoDB aggregation pipelines, compound indexing, zero-downtime rolling deployments, and secure session management.
- 🎓 **Continuous Learning:** Active on [NamasteDev (@dakshbisht1999)](https://namastedev.com/dakshbisht1999), deep-diving into Node.js internals, event loop mechanics, system design, and advanced JavaScript patterns.

---

## 🚀 Featured & Active Projects

### 1. 🔥 [DevTinder](https://devtinder.dishantbisht.in) — Full-Stack Developer Matchmaking Platform
> An interactive matchmaking platform for software engineers to connect, collaborate, find mentors, and discover project partners.

```text
               +-------------------------------------------+
               |           Cloudflare DNS (DNS-Only)       |
               +-------------------------------------------+
                                     |
                                     v
                        +---------------------------+
                        |    Nginx (Port 80/443)    |
                        +---------------------------+
                         /                         \
                        v                           v
              Static Frontend SPA             Reverse Proxy (/api/)
              (React 19 / Vite)               (Express.js / PM2)
                                                    |
                                                    v
                                      +---------------------------+
                                      |  MongoDB Atlas & AWS SES  |
                                      +---------------------------+
```

The system is architected as two decoupled, production-grade repositories:

#### ⚙️ [DevTinder Backend (`devtinder-be`)](https://github.com/dakshbisht1999/devtinder-be)
- **Core Stack:** Node.js (v20 LTS), Express.js (v5), MongoDB Atlas, Mongoose (v9), AWS SES SDK v3, PM2, Nginx.
- **Session & Security:** HTTP-only JWT cookies with dynamic CORS origin whitelist, `bcrypt` password hashing, Google OAuth ID token verification via `google-auth-library`, and token versioning.
- **Smart Discovery Feed:** High-efficiency `$nin` exclusion query filtering out the user, past interactions (`interested`/`ignored`), and mutual connections with database-level pagination.
- **Data Integrity & Matchmaking:** State machine for connection lifecycles (`interested`, `ignored`, `accepted`, `rejected`), compound unique indexes (`{ fromUserId: 1, toUserId: 1 }`), and Mongoose `pre("save")` hooks preventing self-connections.
- **Aggregation Pipelines:** MongoDB aggregation pipeline (`$match`, `$addFields`, `$lookup`, `$unwind`) that computes resolved connection partner profiles directly in the database engine, eliminating in-memory server mapping.
- **Transactional Email:** Two-step OTP generation (`crypto.randomInt`), SHA-256 hashed storage, 5-minute expiry, and automated AWS SES delivery with sandbox mode detection.
- **DevOps & CI/CD:** Automated GitHub Actions pipeline (`deploy-be.yml`) that syncs code to AWS EC2 via SCP/SSH and executes zero-downtime PM2 process restarts.

#### 🖥️ [DevTinder Frontend (`devtinder-fe`)](https://github.com/dakshbisht1999/devtinder-fe)
- **Core Stack:** React 19, Vite, Tailwind CSS v4, DaisyUI v5, Redux Toolkit, React Router v7.
- **Interactive UI:** Smooth card-based discovery deck, real-time incoming connection requests dashboard, and mutual connections directory.
- **Rich Auth:** Standard credentials, Google One-Tap OAuth integration, and seamless session bootstrap (`AuthBootstrap`) preventing UI flashes on reload.
- **Theming & Resilience:** Automatic system Dark/Light mode synchronization, responsive layouts, and centralized toast error handling.

---

### 2. 🧠 Document Q&A RAG Chatbot (Active R&D)
> Intelligent document-grounded AI conversational assistant that ingests diverse files (PDFs, Markdown, Docs), indexes semantic chunks, and delivers context-accurate, zero-hallucination answers.

- **Core Tech Stack:** **Python**, **FastAPI**, **LangChain**, **RAG (Retrieval-Augmented Generation)**, **Model Context Protocol (MCP)**, **LLMs** (OpenAI / Claude / HuggingFace), **Vector Databases** (ChromaDB / MongoDB Atlas Vector Search).
- **Key Engineering Highlights:**
  - **Document Processing Pipeline:** Token-aware recursive text chunking and dense vector embedding generation.
  - **Contextual Semantic Retrieval:** Top-$k$ vector similarity search augmented with hybrid keyword scoring to ground LLM reasoning directly in user documents.
  - **FastAPI Asynchronous Streaming:** Ultra-low latency token delivery using Server-Sent Events (SSE) with `Transfer-Encoding: chunked`.
  - **Agentic Extensibility with MCP:** Leverages **Model Context Protocol (MCP)** tools and servers to enable the LLM to inspect local filesystem hierarchies, query document metadata, and chain multi-step retrieval actions via **LangChain**.

---

### 3. 🌐 [Personal Portfolio & Cloud Infrastructure (`portfolio`)](https://github.com/dakshbisht1999/portfolio)
> Modern, high-performance portfolio showcasing projects, technical runbooks, and multi-tier AWS hosting architecture.

- **Stack:** [React 19](https://react.dev/), [TypeScript 5](https://www.typescriptlang.org/), [Vite 8](https://vitejs.dev/), [Tailwind CSS](https://tailwindcss.com/).
- **Cloud Architecture & Resilience:**
  - Designed multi-strategy cloud hosting across **AWS S3 + CloudFront CDN** and an **AWS EC2 + Nginx reverse proxy** with **Certbot SSL** for custom domain routing (`dishantbisht.in`).
  - Integrated contact form communications with production backend APIs, protected by strict CORS origin policies.
  - Implemented **Dual CI/CD Workflows** via GitHub Actions for automated EC2 deployments and S3 bucket synchronization with cache invalidation.
- **Live Site:** [dishantbisht.in](https://dishantbisht.in)

---

## 🛠️ Technical Arsenal

### Core Stacks (MERN & MEAN)
![MERN Stack](https://img.shields.io/badge/MERN_Stack-MongoDB_|_Express_|_React_|_Node.js-005571?style=for-the-badge&logo=react&logoColor=61DAFB)
![MEAN Stack](https://img.shields.io/badge/MEAN_Stack-MongoDB_|_Express_|_Angular_|_Node.js-DD0031?style=for-the-badge&logo=angular&logoColor=white)

### GenAI, LLMs & Agentic Systems
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=chainlink&logoColor=white)
![RAG Architecture](https://img.shields.io/badge/RAG_Architecture-8A2BE2?style=for-the-badge&logo=openai&logoColor=white)
![Model Context Protocol](https://img.shields.io/badge/MCP_(Model_Context_Protocol)-FF5722?style=for-the-badge&logo=anthropic&logoColor=white)
![Vector Databases](https://img.shields.io/badge/Vector_DB_(Atlas_/_Chroma)-47A248?style=for-the-badge&logo=mongodb&logoColor=white)

### Languages & Frameworks
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![React 19](https://img.shields.io/badge/React_19-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

### Frontend Tools & State Management
![Redux Toolkit](https://img.shields.io/badge/Redux_Toolkit-764ABC?style=for-the-badge&logo=redux&logoColor=white)
![Tailwind CSS v4](https://img.shields.io/badge/Tailwind_CSS_v4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![DaisyUI](https://img.shields.io/badge/DaisyUI_v5-5A0EF8?style=for-the-badge&logo=daisyui&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge&logo=axios&logoColor=white)

### Databases & Caching
![MongoDB Atlas](https://img.shields.io/badge/MongoDB_Atlas-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Mongoose](https://img.shields.io/badge/Mongoose_ODM-880000?style=for-the-badge&logo=mongoose&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)

### Cloud, DevOps & Infrastructure
![AWS](https://img.shields.io/badge/AWS_(EC2_/_S3_/_CloudFront_/_SES_/_Lambda)-232F3E?style=for-the-badge&logo=amazonwebservices&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![PM2](https://img.shields.io/badge/PM2-2B037A?style=for-the-badge&logo=pm2&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux_Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)

### Architecture & Emerging Tech
![RESTful APIs](https://img.shields.io/badge/RESTful_APIs-005571?style=for-the-badge&logo=rest&logoColor=white)
![WebSockets](https://img.shields.io/badge/WebSockets_(Socket.io)-010101?style=for-the-badge&logo=socketdotio&logoColor=white)
![RAG & Vector Search](https://img.shields.io/badge/GenAI_RAG_&_Vector_Search-8A2BE2?style=for-the-badge&logo=openai&logoColor=white)
![OAuth 2.0](https://img.shields.io/badge/OAuth_2.0-EB5424?style=for-the-badge&logo=auth0&logoColor=white)

---

## 💡 Engineering Philosophy & Production Standards

```text
 ┌────────────────────────────────────────────────────────────────────────┐
 │                      ENGINEERING CORE PRINCIPLES                       │
 ├──────────────────────────┬─────────────────────────┬───────────────────┤
 │ ⚡ Performance First     │ 🔒 Zero-Trust Security  │ 🔄 CI/CD & DevOps │
 │ • Database Aggregations  │ • HTTP-Only JWT Cookies │ • Automated SSH   │
 │ • Compound Indexing      │ • SHA-256 Hashed OTPs   │ • Atomic Sync     │
 │ • Sub-Second Feed Queries│ • Strict CORS Isolation │ • PM2 Auto-Reload │
 └──────────────────────────┴─────────────────────────┴───────────────────┘
```

1. **Database-Level Compute Over In-Memory Processing:**
   Complex filtering and multi-table joins are offloaded directly to MongoDB aggregation pipelines and compound indexes rather than overburdening Node.js runtime memory.
2. **Resilience & Graceful Degradation:**
   Custom `AppError` operational error boundaries isolate third-party service hiccups (e.g., AWS SES sandbox limitations or upstream SSL issues) without impacting primary user flows.
3. **Decoupled Architecture & Fast Delivery:**
   Separating SPA frontends and stateless backend APIs allows independent scaling, isolated CI/CD deployments, and streamlined migration paths to containerized microservices.

---

## 📊 Unified Developer Hub & Activity

<div align="center">

<a href="https://namastedev.com/dakshbisht1999" target="_blank">
  <img src="https://img.shields.io/badge/NamasteDev_Unified_Hub-dakshbisht1999-FF6B00?style=for-the-badge&logo=codeforces&logoColor=white" alt="NamasteDev Profile" />
</a>

<br/><br/>

| 🌐 **Unified Activity Hub** | 🔗 **Connected Platforms** | 📈 **Active Tracking** |
|:---:|:---:|:---:|
| **[namastedev.com/dakshbisht1999](https://namastedev.com/dakshbisht1999)** | GitHub • LeetCode • LinkedIn | Full-Stack, Node.js & System Design Contributions |

> 💡 *NamasteDev acts as my single-pane developer dashboard — dynamically uniting my cross-platform problem-solving, GitHub commits, and deep-dive engineering journey.*

</div>

<br/>

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=dakshbisht1999&show_icons=true&theme=radical&hide_border=true&count_private=true" alt="Dishant Bisht's GitHub Stats" width="48%" />
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=dakshbisht1999&layout=compact&theme=radical&hide_border=true" alt="Top Languages" width="48%" />

</div>

<br/>

<div align="center">

[![Dishant's Streak](https://github-readme-streak-stats.herokuapp.com/?user=dakshbisht1999&theme=radical&hide_border=true)](https://git.io/streak-stats)

</div>

---

## 📫 Connect & Collaborate

I am always interested in discussing full-stack engineering, cloud architecture, system design, and GenAI possibilities. Feel free to reach out!

- 🌐 **Portfolio & Case Studies:** [dishantbisht.in](https://dishantbisht.in)
- 🎓 **NamasteDev Community:** [namastedev.com/dakshbisht1999](https://namastedev.com/dakshbisht1999)
- 💼 **LinkedIn:** [linkedin.com/in/dishantbisht](https://www.linkedin.com/in/dishantbisht)
- 🐙 **GitHub:** [@dakshbisht1999](https://github.com/dakshbisht1999)
- ✉️ **Direct Email:** [support@dishantbisht.in](mailto:support@dishantbisht.in)

---

<div align="center">
  <sub>Crafted with passion, modern cloud architecture, and clean engineering principles. © Dishant Bisht</sub>
</div>
