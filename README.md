<!-- styled:v2 -->
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1d1726,50:167dfe,100:9533fa&height=180&section=header&text=AI%20Legal%20Chatbot%20with%20RAG&fontSize=38&fontColor=ffffff&fontAlignY=36&desc=n8n%20%E2%80%A2%20OpenAI%20%E2%80%A2%20Supabase&descAlignY=58&descSize=16&animation=fadeIn" width="100%" alt="AI Legal Chatbot with RAG" />

**An n8n chatbot for law firm websites that answers client questions from the firm's own legal knowledge base, using retrieval-augmented generation (RAG).**

<p>
  <img src="https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white" alt="n8n" />
  <img src="https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white" alt="OpenAI" />
  <img src="https://img.shields.io/badge/Supabase%20Vector-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white" alt="Supabase" />
  <img src="https://img.shields.io/badge/Google%20Drive-4285F4?style=for-the-badge&logo=googledrive&logoColor=white" alt="Google Drive" />
  <img src="https://img.shields.io/badge/RAG-167dfe?style=for-the-badge" alt="RAG" />
</p>

<p>
  <a href="#overview">Overview</a> ·
  <a href="#how-it-works">How it works</a> ·
  <a href="#key-features">Key features</a> ·
  <a href="#tech-stack">Tech stack</a>
</p>

</div>

---

## Overview

Law firms answer the same questions again and again, and a static website can't reply in real time. This chatbot sits on the firm's website and answers from the firm's own documents, so replies stay accurate, consistent and on-brand, 24 hours a day.

## The challenge

Repetitive client questions take up staff time, replies are slow and inconsistent, and website visitors leave before anyone responds.

## How it works

```mermaid
flowchart LR
    subgraph ING[" 📥 Knowledge base "]
        GD[Google Drive<br/>legal documents] --> L[Document loader]
        L --> E[OpenAI<br/>embeddings]
        E --> V[(Supabase<br/>vector store)]
    end
    subgraph CHAT[" 💬 Chat "]
        Q([Website visitor]) --> A[AI agent<br/>OpenAI chat model]
        A <--> MEM[Conversation<br/>memory]
        A <--> V
        A --> R([Answer from<br/>firm knowledge])
    end

    classDef box fill:#1d1726,stroke:#167dfe,color:#e5e7eb
    classDef ends fill:#2e1065,stroke:#9533fa,color:#ffffff
    class GD,L,E,A,MEM box
    class V,Q,R ends
```

1. **Documents loaded.** Legal documents from Google Drive are split, embedded with OpenAI and stored in a Supabase vector store.
2. **Question received.** A visitor asks a question in the website chat.
3. **Knowledge retrieved.** The AI agent searches the vector store for the most relevant passages and keeps the conversation in memory.
4. **Answer sent.** It replies in a professional tone using the firm's own information.

## Key features

- RAG answers grounded in the firm's knowledge base
- Covers criminal, civil, FIA, intellectual property, tort and defamation questions
- Conversation memory for follow-up questions
- Available 24/7 on the firm's website
- Knowledge base refreshed by re-running the Google Drive ingestion

## Use cases

- Law firm websites
- Legal consultation platforms
- AI client intake and support

## Tech stack

![n8n](https://img.shields.io/badge/n8n-1d1726?style=for-the-badge) ![OpenAI](https://img.shields.io/badge/OpenAI-1d1726?style=for-the-badge) ![Supabase](https://img.shields.io/badge/Supabase-1d1726?style=for-the-badge) ![Google Drive](https://img.shields.io/badge/Google%20Drive-1d1726?style=for-the-badge) ![LangChain nodes](https://img.shields.io/badge/LangChain%20nodes-1d1726?style=for-the-badge)

## Files

| File | Contents |
|:--|:--|
| `legal chatbot (2).json` | The n8n workflow: import it into n8n and add your own credentials |
| `AI-Powered Legal Chatbot for Law Firm Website.docx` | Project write-up |

## Demo

▶️ [Watch the demo video](https://drive.google.com/file/d/1fqKHOb_AOZ-gb79qFqd6NwznNGMe_k2R/view?usp=sharing)

> The chatbot gives general legal information only and does not replace professional legal advice.

---

<div align="center">

**Built by [Ch Muhammad Samiullah](https://github.com/samiullah156-creator)** · AI Automation Engineer and Full-Stack Developer at [Lexvaxa](https://lexvaxa.com)

<a href="https://github.com/samiullah156-creator"><img src="https://img.shields.io/badge/More%20projects-181717?style=for-the-badge&logo=github&logoColor=white" alt="More projects" /></a>
<a href="https://lexvaxa.com/contact"><img src="https://img.shields.io/badge/Work%20with%20me-167dfe?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Work with me" /></a>
<a href="https://www.linkedin.com/in/sami-lexvaxa/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>

<sub>⭐ Star this repo if you found it useful</sub>

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:9533fa,50:167dfe,100:1d1726&height=110&section=footer" width="100%" alt="" />
