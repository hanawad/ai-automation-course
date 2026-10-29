<div align="center">

# 🤖 AI Client Intake & Request Routing System

> **Haneen | Data Diva**  
> *Real-Time Big Data Pipelines, Agentic AI Integration & Automation Engineering*

🌐 **Select Language / اختر اللغة:**

[**العربية**](#arabic) | [**English**](#english)

---

</div>

<span id="arabic"></span>
## 🇵🇸 العربية

### 🎯 نبذة عن المشروع
مشروع عملي لتطبيق مفاهيم **U1 — Process & Data Thinking** وتحويلها إلى نظام أتمتة حقيقي (**AI Automation**).  
يقوم النظام بأتمتة استقبال وتطوير طلبات العملاء الواردة عبر **Google Forms**، من خلال دمج الذكاء الاصطناعي لفهم النصوص غير المنظمة، والمنطق البرمجي (**Rule / Logic**) للتحكم في مسار العملية، وتعديل العنصر البشري (**Human-in-the-Loop**) عند وجود معلومات ناقصة أو غامضة.

#### 🧠 الـ Mental Model المتبع:
- **AI $\rightarrow$ Understand:** فهم الطلب غير المنظم واستخراج البيانات الأساسية.
- **Rule / Logic $\rightarrow$ Control:** التحكم في مسار العملية والتوجيه الحتمي بناءً على حالة الطلب (`VALID` أو `NEEDS_REVIEW`).
- **Human $\rightarrow$ Judge:** التدخل البشري لمعالجة الحالات الاستثنائية (Exceptions).

---

### 🏗️ البنية الهندسية وتدفق البيانات (Workflow)

```text
Client ──► Google Forms ──► Trigger ──► Unstructured Request
                                                │
                                                ▼
                                         AI Engine / LLM
                                                │
                                                ▼
                                        Structured Output
                                                │
                                                ▼
                                       Paths (Decision Logic)
                                       ┌────────┴────────┐
                                     VALID          NEEDS_REVIEW
                                       │                 │
                                       ▼                 ▼
                                   Web Team            Human
                                       │                 │
                                       └────────┬────────┘
                                                ▼
                                          Google Sheets
                                                │
                                                ▼
                                           Email Notification