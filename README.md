# AURAFLOW AI

> **"Intelligent Workflow Orchestration Platform"**  
> *From repetitive work to autonomous operations.*  
> *Capture. Understand. Decide. Automate. Measure.*

---

## 1. Product Concept & Vision

**AuraFlow AI** is an intelligent workflow orchestration platform built for modern organizations. Instead of employees manually moving work from one person to another through endless emails, chat messages, and spreadsheets, **AuraFlow AI understands incoming requests (via natural language text, real-time voice dictation, or document OCR) and automatically orchestrates them through the correct workflow**.

### The Core Automation Process:
```
REQUEST 
  → MULTI-MODAL CAPTURE (Text / Voice / OCR)
  → AI CLASSIFICATION & INTENT EXTRACTION
  → 5-VECTOR RISK EVALUATION (SLA, Financial, Complexity, Anomaly, Load)
  → PROACTIVE MISSING INFO VALIDATION
  → DUPLICATE & REPETITION DETECTION
  → PRESCRIPTIVE NEXT BEST ACTION (NBA)
  → AUTONOMOUS ORCHESTRATION & WATCHDOG SLA MONITORING
  → MEASURE & CONTINUOUS PROCESS MINING
```

---

## 2. System Architecture & Requested Directory Structure

```
AURAFLOW AI/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── AIRiskRadar.jsx            # 5-Vector interactive risk radar visualization (Recharts)
│   │   │   ├── ProcessHealth.jsx          # Live operational health score & stage latency monitor
│   │   │   ├── BottleneckDetector.jsx     # Friction point detection with 1-click AI resolutions
│   │   │   ├── NextBestAction.jsx         # Prescriptive guidance card with instant step execution
│   │   │   ├── MissingInfo.jsx            # Proactive form validation & missing field guard
│   │   │   ├── EscalationTimeline.jsx     # Multi-milestone SLA watchdog progression tracker
│   │   │   ├── VoiceRequestRecorder.jsx   # Real-time microphone audio speech-to-text dictation
│   │   │   ├── AiAgentsMatrixModal.jsx    # Live autonomous AI agents matrix telemetry
│   │   │   ├── SlaCountdown.jsx           # Real-time countdown timer with breach alerts
│   │   │   ├── WorkflowTimeline.jsx       # Dynamic visual step execution pipeline
│   │   │   └── AiAnalysisCard.jsx         # Structured AI intent & confidence metrics card
│   │   ├── pages/
│   │   │   ├── DashboardPage.jsx          # Operations Command Center with integrated Risk & Health
│   │   │   ├── CreateRequestPage.jsx      # Voice + OCR + Missing Info Smart Request Composer
│   │   │   ├── RequestDetailPage.jsx      # Next Best Action + Risk Radar + Escalation Timeline
│   │   │   ├── ApprovalsPage.jsx          # Managerial decision center with AI policy audit
│   │   │   ├── TasksPage.jsx              # Kanban board and task lifecycle tracker
│   │   │   ├── AutomationRunsPage.jsx     # Live execution simulator and telemetry traces
│   │   │   ├── AnalyticsPage.jsx          # Executive ROI, throughput, and impact metrics
│   │   │   ├── WorkflowBuilderPage.jsx    # Interactive canvas node workflow designer
│   │   │   ├── AiAssistantPage.jsx        # "Ask AuraFlow" conversational intelligence chat
│   │   │   ├── AiReportsPage.jsx          # Gemini-generated executive operations synthesis
│   │   │   ├── TeamPage.jsx               # Team roster & 1-click persona switcher
│   │   │   └── SettingsPage.jsx           # AI thresholds & watchdog configuration
│   │   ├── services/
│   │   │   └── intelligenceService.js     # Unified API client for AuraFlow intelligence engines
│   │   ├── utils/
│   │   │   └── api.js                     # Axios HTTP client with JWT auth interceptors
│   │   ├── context/
│   │   │   ├── AuthContext.jsx            # Multi-persona authentication & demo session state
│   │   │   └── ThemeContext.jsx           # Dark / Light mode toggle persistence
│   │   └── App.jsx                        # Declarative React Router routing hierarchy
│   └── package.json
│
├── backend/
│   ├── src/
│   │   ├── services/
│   │   │   ├── geminiService.js           # Google Gemini 1.5 Flash multimodal SDK integration
│   │   │   ├── riskEngine.js              # 5-vector risk computation (SLA, financial, anomaly)
│   │   │   ├── escalationEngine.js        # SLA watchdog milestone evaluator (50%, 80%, 100%)
│   │   │   ├── bottleneckEngine.js        # Process mining engine for queue latency & saturation
│   │   │   ├── duplicateDetector.js       # Tokenized Jaccard similarity & double-spend prevention
│   │   │   ├── nextActionEngine.js        # Prescriptive AI decision-making & time saved scoring
│   │   │   ├── ruleEngine.js              # Business rule evaluation against organizational policy
│   │   │   └── workflowEngine.js          # State machine orchestrator for multi-step workflows
│   │   ├── models/
│   │   │   ├── Request.js                 # Unified schema with AI telemetry, SLA, and audit trail
│   │   │   ├── Workflow.js                # Dynamic multi-step workflow pipeline schema
│   │   │   ├── Task.js                    # Kanban task schema with assignees and due dates
│   │   │   ├── Approval.js                # Multi-level approval decision & comment records
│   │   │   ├── User.js                    # User persona & role-based access control
│   │   │   ├── Notification.js            # In-app alert dispatch records
│   │   │   └── AuditLog.js                # Tamper-evident operational audit logs
│   │   ├── routes/
│   │   │   ├── intelligenceRoutes.js      # Endpoints for Risk, Health, NBA, Escalation & Bottlenecks
│   │   │   ├── requestRoutes.js           # CRUD & AI document intake endpoints
│   │   │   ├── aiRoutes.js                # Direct Gemini classification & assistant chat
│   │   │   ├── workflowRoutes.js          # Workflow template management
│   │   │   ├── taskRoutes.js              # Kanban state management
│   │   │   ├── approvalRoutes.js          # Approval decision endpoints
│   │   │   ├── analyticsRoutes.js         # Aggregated throughput & savings statistics
│   │   │   └── authRoutes.js              # JWT login, registration & seed utilities
│   │   ├── controllers/
│   │   │   ├── intelligenceController.js  # Controller handlers for all 5 intelligence engines
│   │   │   ├── requestController.js       # Request orchestration lifecycle handlers
│   │   │   └── aiController.js            # Gemini prompt orchestration handlers
│   │   ├── middleware/
│   │   │   ├── authMiddleware.js          # JWT verification & role authorization
│   │   │   └── errorHandler.js            # Unified JSON error handler
│   │   ├── app.js                         # Express application setup, CORS, Helmet, and routing
│   │   └── server.js                      # HTTP server startup & MongoDB connection
│   └── package.json
│
└── README.md
```

---

## 3. Deep-Dive: AuraFlow AI Intelligence Engines

### 1. `riskEngine.js` (5-Vector Risk Analysis)
Calculates a multi-dimensional risk index (0–100) across 5 vectors:
- **SLA Exposure Vector**: Compares elapsed time vs. SLA deadline; triggers elevated risk at 50% and 80% milestones.
- **Financial Exposure Vector**: Evaluates requested budget against department approval thresholds (₹25,000 / ₹50,000 / ₹2,00,000).
- **Process Complexity Vector**: Scores multi-tier approvals, cross-department dependencies, and compliance checks.
- **Anomaly Detection Vector**: Flags policy divergences (e.g. non-standard vendors, urgent flags for routine purchases).
- **Resource Load Vector**: Assesses current queue depth and reviewer saturation.

### 2. `escalationEngine.js` (SLA Watchdog)
- Evaluates active tickets continuously against SLA milestones:
  - **50% Mid-Point**: Soft in-app reminder dispatched to the assigned reviewer.
  - **80% Critical Threshold**: High-priority alert sent to Team Lead; priority bumped automatically.
  - **100% SLA Breach**: Auto-escalates to Department VP and activates emergency bypass rules.

### 3. `bottleneckEngine.js` (Process Mining & Friction Detection)
- Analyzes stage dwell times across departments (Finance, HR, IT, Procurement).
- Calculates queue delay multipliers against industry SLA benchmarks (e.g., 2.8x standard dwell time in Finance for invoices > ₹50,000).
- Formulates autonomous 1-click remediation actions (e.g., auto-proxy delegation, ERP webhook synchronization).

### 4. `duplicateDetector.js` (Double-Spending & Redundancy Prevention)
- Uses tokenized Jaccard similarity and fuzzy matching across title, description, category, and requested amount.
- Prevents employees from submitting duplicate expense receipts, dual purchase orders, or conflicting leave requests.

### 5. `nextActionEngine.js` (Prescriptive Guidance)
- Formulates the mathematically optimal next operational step for any request.
- Provides chain-of-thought rationale, confidence scoring (e.g., 96%), and estimated cycle time saved (e.g., ~16.5 hours).

---

## 4. Deep-Dive: AuraFlow Frontend Intelligence Components

### 1. `AIRiskRadar.jsx`
- Recharts-powered Polar Radar Chart displaying the 5 core risk vectors.
- Overall risk score badge (`LOW`, `MEDIUM`, `HIGH`, `CRITICAL`), vector breakdown bars, and 1-click "Apply Mitigation" action.

### 2. `ProcessHealth.jsx`
- Executive operational health index (e.g. 96% Optimal).
- Live throughput velocity, MTTR recovery time, and stage-by-stage dwell time latency meters.
- Includes interactive "Run Diagnostics" simulation trigger.

### 3. `BottleneckDetector.jsx`
- Interactive friction cards highlighting department choke points, queue depths, and delay multipliers.
- 1-click "Apply AI Resolution" buttons that simulate instant automated proxy delegation or webhook dispatch.

### 4. `NextBestAction.jsx`
- Sleek glowing card showing prescriptive next steps recommended by the Aura Decision Engine.
- Displays policy compliance references, hours saved, and a 1-click "Execute Next Best Action" button.

### 5. `MissingInfo.jsx`
- Proactive form validator mounted in the request composer.
- Analyzes text and voice dictation in real-time, detecting missing vendor quotes, dates, or cost centers, with 1-click "Append Info" buttons.

### 6. `EscalationTimeline.jsx`
- Interactive visual audit timeline showing SLA milestone watchdogs (Intake → 50% Reminder → 80% Warning → Hard Breach).
- Provides a 1-click "Preemptive Escalation" button with immediate supervisor notification feedback.

---

## 5. Additional Key Capabilities

1. **🎙️ Aura Voice Dictation Hub (`VoiceRequestRecorder.jsx`)**:
   - Hands-free speech-to-text dictation with live audio waveform bars, recording timer, and 1-click transcript insertion into the request form.
2. **🤖 Autonomous AI Agents Matrix (`AiAgentsMatrixModal.jsx`)**:
   - Real-time telemetry inspector for the 5 specialized autonomous agents (Aura Classifier, Risk Sentinel, Policy Auditor, Autonomous Router, Voice & OCR Agent).
3. **⚡ Live Execution Simulator (`AutomationRunsPage.jsx`)**:
   - 1-click animated simulation of an autonomous GPU cloud scaling workflow with real-time stage progression and duration logs.
4. **📄 Document AI & Multimodal OCR**:
   - Drag & drop PDF/image invoices, receipts, or contracts; automatically extracts amount, vendor, and approval chains using Gemini Vision.

---

## 6. Demo Accounts & Credentials

AuraFlow AI includes pre-seeded demo personas with 1-click switching:

| Role | Email | Password | Access Capabilities |
|---|---|---|---|
| **Administrator** | `admin@flowpilot.demo` | `password123` | Full system access, workflow builder, automation rules, risk radar, audit logs |
| **Manager** | `manager@flowpilot.demo` | `password123` | Department approvals, team task assignment, SLA watchdog overrides |
| **Employee** | `employee@flowpilot.demo` | `password123` | Voice & text request submission, personal task tracking, notifications |

---

## 7. Quickstart & Local Execution

### Prerequisites:
- **Node.js** v18+ (tested on Windows & Linux)
- No external MongoDB daemon required — an embedded In-Memory MongoDB engine starts automatically with zero setup!

### 1. Start Backend:
```bash
cd backend
npm install
npm start
```
*Backend will run on `http://localhost:5000` and auto-seed demo workflows, requests, and tasks.*

### 2. Start Frontend:
```bash
cd frontend
npm install
npm run dev
```
*Frontend will launch at `http://localhost:5173`.*

---

## 8. Hackathon Evaluation Checklist

| Requirement | Implementation in AuraFlow AI | Status |
|---|---|---|
| **Real-World Problem** | Eliminates manual ticket chasing, delay-prone approvals, and lack of visibility | ✅ Solved |
| **Smart Automation Theme** | 5 AI Engines: Risk, Escalation, Bottleneck, Duplication, Next Best Action | ✅ Complete |
| **Not a Simple Chatbot** | Full workflow orchestration platform with state machine and Kanban tasks | ✅ Complete |
| **Multi-Modal Input** | Natural language text + Web Speech API voice dictation + Document OCR | ✅ Complete |
| **Prescriptive Guidance** | Next Best Action (NBA) with estimated time saved and 1-click execution | ✅ Complete |
| **Process Mining** | Bottleneck Detector with queue friction multipliers and 1-click auto-proxy | ✅ Complete |
| **Production Aesthetics** | High-density enterprise SaaS layout, dark/light modes, Recharts visualizations | ✅ Complete |
