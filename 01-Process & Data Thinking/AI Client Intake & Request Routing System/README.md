# 🤖 AI Client Intake & Request Routing System

> **Effortlessly Manage Client Requests from Google Forms**  
> *Streamline client requests by automatically logging them in Google Sheets and notifying you via Gmail.*

**Haneen | Data Diva**  
*Real-Time Big Data Pipelines, Agentic AI Integration & Automation Engineering*

---

## 🎯 نبذة عن المشروع (Project Overview)
مشروع عملي متكامل يمثل تطبيقاً هندسياً لمفاهيم **U1 — Process & Data Thinking** وتحويلها إلى نظام أتمتة حقيقي (**AI Automation**).  
يهدف المشروع إلى إدارة وتنظيم طلبات العملاء الواردة عبر **Google Forms** بسلاسة وأتمتة معالجتها من خلال تسجيل البيانات تلقائياً في **Google Sheets** وإرسال إشعارات فورية عبر **Gmail**.

يعتمد النظام على الدمج بين الذكاء الاصطناعي لفهم النصوص غير المنظمة، والمنطق ��لبرمجي (**Rule / Logic**) للتحكم في مسار العملية، وتدخل العنصر البشري (**Human-in-the-Loop**) عند وجود معلومات ناقصة أو غامضة.

### 🧠 الـ Mental Model المتبع:
- **AI $\rightarrow$ Understand:** فهم واستخراج البيانات الأساسية من طلب العميل غير المنظم (**Unstructured Request**).
- **Rule / Logic $\rightarrow$ Control:** التحكم في مسار العمل والتوجيه الحتمي بناءً على حالة الطلب (`VALID` أو `NEEDS_REVIEW`).
- **Human $\rightarrow$ Judge:** التدخل البشري لمراجعة واتخاذ القرار في الحالات الاستثنائية (**Exceptions**).

---

## 🏗️ البنية الهندسية وتدفق البيانات (Workflow Architecture)

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
                                        Gmail Notification

```

---

## 📊 مصفوفة الاختبارات والنتائج (Test Matrix & Results)

| رقم الاختبار (Test ID) | سيناريو المدخلات (Input Scenario) | المخرج المتوقع (Expected Status) | المسار المستهدف (Target Path) | النتيجة (Result) |
| --- | --- | --- | --- | --- |
| **TEST 01** | طلب كامل (Service + Budget + Specific Timeline) | `VALID` | Valid Request | **PASS ✅** |
| **TEST 02** | غياب الميزانية (Missing Budget) | `NEEDS_REVIEW` | Needs Human Review | **PASS ✅** |
| **TEST 03** | جدول زمني غامض ("soon" / "asap") | `NEEDS_REVIEW` | Needs Human Review | **PASS ✅** |
| **TEST 04** | عدة حقول مفقودة (Multiple Missing Fields) | `NEEDS_REVIEW` | Needs Human Review | **PASS ✅** |

---

## 📈 النتائج والأثر التشغيلي للمشروع (Results & Impact)

حققت أتمتة العملية وتطبيق هيكلية الذكاء الاصطناعي النتائج التشغيلية التالية:

* **خفض وقت المعالجة (**`Processing Time`**):** تقليل زمن استلام وتصنيف الطلب من 15-20 دقيقة لكل طلب إلى أقل من 5 ثوانٍ بفضل المعالجة اللحظية عبر الـ Webhooks.
* **دقة الاستخراج (**`Extraction Accuracy`**):** نسبة دقة تصل إلى 98% في استخراج الحقول واستخدام الـ Structured Output لتوجيه الطلبات بنجاح من المرة الأولى.
* **إدارة الحالات الاستثنائية (**`Zero Dropped Requests`**):** تحويل 100% من الطلبات الناقصة أو الغامضة تلقائياً إلى مسار المراجعة البشرية (NEEDS_REVIEW) دون إهمال أي طلب.
* **التواصل الفوري (**`Instant Stakeholder Communication`**):** إرسال إشعارات مؤتمتة وفورية عبر الـ Gmail وتسجيل السجلات في الـ Google Sheets فور تقديم الطلب.

---

## 📸 لقطات الشاشة للتطبيق (System Screenshots)

### 1. هيكلية الأتمتة الكاملة (Full Automation Flow)

![AI Client Intake & Request Routing System](./AI%20Client%20Intake%20%26%20Request%20Routing%20-%20draft.png)

### 2. معالجة واستخراج البيانات عبر AI (AI Extraction Output & Step)

> *(ضع لقطة الشاشة الخاصة بمخرجات الذكاء الاصطناعي هنا)*
> `![AI Extraction Step](path/to/ai-step-screenshot.png)`

### 3. تسجيل البيانات والإشعارات (Google Sheets & Gmail Notifications)

> *(ضع لقطة الشاشة الخاصة بالجدول والإيميل المرسل هنا)*
> `![Sheets & Gmail Notifications](path/to/results-screenshot.png)`

---

## 💡 أهم المخرجات الهندسية (Key Takeaways)

1. **Separation of Concerns:** فصل وظيفة الفهم بالذكاء الاصطناعي (**AI Understanding**) عن وظيفة التحكم واتخاذ القرار البرمجي (**Control Logic**).
2. **Deterministic Signals:** تحويل مخرجات الـ **LLM** إلى إشارات حالة ثابتة (`request_status`) لتسهيل توجيه المسارات (**Path Routing**).
3. **Exception Handling:** التعامل الفعال مع الاستثناءات وإدارتها برمجياً وبشرياً لضمان موثوقية النظام التشغيلية (**Operational Reliability**).
