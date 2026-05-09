# 🎓 PMP Questions UI

A React-based frontend for practicing **Project Management Professional (PMP)** exam questions. Connects to the [pmpquestionservice](https://github.com/sulthanmubaraksyed/pmpquestionservice) backend API to serve, filter, and track your exam practice sessions.

---

## 🖥️ What It Does

- Browse and answer PMP practice questions filtered by **Process Group**, **Knowledge Area**, or **PM Tool/Technique**
- Submit answers and get instant feedback (correct ✅ / incorrect ❌)
- Navigate forward/backward through questions
- Track your score per **Process Group** in real time
- Mark questions as valid/invalid (admin feature)
- Edit question content via the Edit dialog (admin role)
- Retrieve a specific question by ID
- Debug view for inspecting loaded question state

---

## 🏗️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | React 18 + TypeScript |
| UI Components | Material UI (MUI) v5 |
| Styling | CSS Modules |
| Build Tool | Create React App |
| Backend | PMP Question Service REST API |

---

## 📁 Project Structure

```
pmpquestions-ui/
├── src/
│   ├── components/
│   │   ├── AnswerOptions/         # A/B/C/D radio options + Submit/Prev/Next buttons
│   │   ├── ProcessGroupSelector/  # Dropdown: Initiating, Planning, Executing, etc.
│   │   ├── KnowledgeAreaSelector/ # Dropdown: Integration, Scope, Risk, etc.
│   │   ├── ToolSelector/          # Filter by PM tool/technique
│   │   ├── ProcessGroupScores/    # Real-time score display per process group
│   │   ├── QuestionValidityToggle/# Mark questions valid/invalid
│   │   ├── EditResponseDialog/    # Admin: edit question content
│   │   ├── RetrieveQuestionDialog/# Fetch a specific question by ID
│   │   ├── ScoreDisplay.tsx       # Score summary component
│   │   └── DebugDialog/           # Debug: inspect loaded question data
│   ├── config/
│   │   ├── appConfig.ts           # Batch size, thresholds config
│   │   ├── toolsarray.ts          # Full PM tools list
│   │   └── validTools.ts          # Valid tool filters
│   ├── utils/
│   │   ├── questionManager.ts     # State machine for question loading/navigation
│   │   └── questionService.ts     # API calls to the backend service
│   ├── types/
│   │   └── index.ts               # TypeScript interfaces
│   └── App.tsx                    # Root component with all state and logic
├── env.example                    # Environment variable template
└── public/
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js >= 16
- The [pmpquestionservice](https://github.com/sulthanmubaraksyed/pmpquestionservice) backend running on port `3030`

### Installation

```bash
git clone https://github.com/sulthanmubaraksyed/pmpquestions-ui.git
cd pmpquestions-ui
npm install
```

### Environment Setup

```bash
cp env.example .env
```

Edit `.env`:
```env
REACT_APP_PMP_SERVICE_URL=http://localhost:3030
REACT_APP_API_KEY=pmp_service_key_2024
```

### Run

```bash
npm start
```

Opens at **http://localhost:3000**

---

## 🎮 How to Use

1. **Select filters** — choose a Process Group, Knowledge Area, or Tool (mutually exclusive)
2. **Read the question** — displayed in the question area
3. **Pick an answer** — select A, B, C, or D
4. **Submit** — see instant green (correct) or red (incorrect) feedback
5. **Navigate** — use Previous / Next to move through questions
6. **Track scores** — the right panel shows your score per PMP process group

### Admin Features
- **Validity Toggle** — mark a question as valid or invalid
- **Retrieve** button — opens Edit dialog to modify question content
- **Debug** button — inspect raw question data loaded in memory

---

## ⚙️ Configuration

| Variable | Default | Description |
|----------|---------|-------------|
| `MIN_QUESTIONS_THRESHOLD` | 15 | Min questions before fetching more |
| `BATCH_SIZE` | 5 | Questions fetched per batch |
| `ADDITIONAL_RECORDS_ON_SUBMIT` | 2 | Extra questions added on each submit |

---

## 🔗 Related Repositories

- **[pmpquestionservice](https://github.com/sulthanmubaraksyed/pmpquestionservice)** — Local backend API
- **[awspmpquestionservice](https://github.com/sulthanmubaraksyed/awspmpquestionservice)** — AWS Lambda backend
- **[awspmpquestionui](https://github.com/sulthanmubaraksyed/awspmpquestionui)** — AWS-deployed UI version

---

## 📝 License

ISC
