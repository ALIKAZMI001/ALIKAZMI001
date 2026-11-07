<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F0C29,40:302B63,100:24243e&height=220&section=header&text=Ali%20Kazmi&fontSize=76&fontColor=ffffff&fontAlignY=36&desc=Applied%20AI%20%E2%80%A2%20Computer%20Vision%20%E2%80%A2%20LLM%20Systems&descAlignY=58&descSize=24&animation=fadeIn&stroke=6EE7F7&strokeWidth=2" width="100%"/>

<br/>

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=700&size=22&duration=2600&pause=800&color=6EE7F7&center=true&vCenter=true&width=800&lines=Production-Ready+AI+%26+Deep+Learning+Systems;Sub-500ms+Duplex+Voice+Agent+with+LiveKit+%26+Groq;Zero-Hallucination+Vector+RAG+Pipeline+with+Qdrant;Real-Time+YOLOv8+%26+MediaPipe+Vision+at+40%2B+FPS;Terminal+AI+Agent+with+Zero-Setup+Failover;Clean+Architecture+%E2%80%A2+100%25+Runnable+Code" alt="Typing SVG"/>

<br/><br/>

[![GitHub followers](https://img.shields.io/github/followers/ALIKAZMI001?style=for-the-badge&color=3B82F6&labelColor=0D1117&logo=github&label=Followers)](https://github.com/ALIKAZMI001?tab=followers)
&nbsp;
[![GitHub Stars](https://img.shields.io/github/stars/ALIKAZMI001?style=for-the-badge&color=FFD700&labelColor=0D1117&logo=github&label=Total%20Stars)](https://github.com/ALIKAZMI001?tab=repositories)
&nbsp;
[![Repositories](https://img.shields.io/badge/All%20Repositories-Explore-6EE7F7?style=for-the-badge&logo=github&logoColor=black)](https://github.com/ALIKAZMI001?tab=repositories)
&nbsp;
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-6EE7F7?style=for-the-badge&logo=git&logoColor=black)](https://github.com/ALIKAZMI001)

<br/>

**[ 🎯 Featured Repositories ](#-featured-repositories)** &nbsp;•&nbsp;
**[ ⚡ Architecture Flows ](#-system-architecture)** &nbsp;•&nbsp;
**[ 📊 Benchmarks ](#-engineering-benchmarks)** &nbsp;•&nbsp;
**[ 🛠️ Tech Stack ](#-technical-arsenal)** &nbsp;•&nbsp;
**[ 🚀 Quickstart ](#-quick-start)** &nbsp;•&nbsp;
**[ 📬 Contact ](#-connect--collaborate)**

</div>

---

## 🎯 Featured Repositories

End-to-end, standalone AI systems with modular architectures and self-contained environments:

| Project | Domain | Key Technologies | Real-World Capability |
|:---|:---:|:---|:---|
| ✈️ **[livekit-trip-agent](https://github.com/ALIKAZMI001/livekit-trip-agent)** | Voice Agent | LiveKit, Groq LLaMA 3.3, Cartesia, Docker | Sub-500ms duplex voice assistant querying live flights, weather & booking |
| 🤖 **[ALI-CODE](https://github.com/ALIKAZMI001/ALI-CODE)** | Dev Tooling | TypeScript, Node.js, OpenAI SDK, Cloudflare Workers | Claude Code-style terminal coding agent with zero-setup shared models and automatic multi-provider failover |
| 📄 **[rag-pdf-chatbot](https://github.com/ALIKAZMI001/rag-pdf-chatbot)** | RAG / NLP | LangChain, Qdrant, sentence-transformers | Grounded document Q&A with strict anti-hallucination boundaries |
| 🎙️ **[urdu-voice-assistant](https://github.com/ALIKAZMI001/urdu-voice-assistant)** | Speech AI | SpeechRecognition, Mistral 7B, gTTS | Complete Urdu speech-to-speech assistant with multi-device fallback |
| 🎯 **[yolo-face-detection](https://github.com/ALIKAZMI001/yolo-face-detection)** | Computer Vision | Ultralytics YOLOv8, MediaPipe, OpenCV | Custom dataset capture & fine-tuned YOLOv8n detector running at 40+ FPS |
| 🏏 **[llm-finetuning](https://github.com/ALIKAZMI001/llm-finetuning)** | Deep Learning | Hugging Face Transformers, PyTorch | BERT fine-tuned on GLUE/MRPC & T5 cricket Q&A chatbot from scratch |
| 🎂 **[age-gender-estimation](https://github.com/ALIKAZMI001/age-gender-estimation)** | Computer Vision | TensorFlow, Keras, OpenCV, IMDB-WIKI | Dual-head multi-task CNN predicting age and gender live on webcam |
| 🪪 **[CNN/KNN face-recognition](https://github.com/ALIKAZMI001/face-recognition)** | Computer Vision | Keras, scikit-learn, Tkinter, OpenCV | Deep metric CNN vs classical KNN comparison inside a desktop app |
| 🎮 **[gesture-game-control](https://github.com/ALIKAZMI001/gesture-game-control)** | Spatial AI | MediaPipe, PyAutoGUI, Unity Engine | Real-time spatial gesture mapping controlling a bundled Unity game |

---

## ⚡ System Architecture

Clean, modular data pipelines engineered for low latency and high reliability:

### 1. Autonomous Real-Time Voice Loop (`livekit-trip-agent`)
```text
  [ User Microphone ]
           │
           ▼ (WebRTC Opus Stream)
  ┌────────────────────────────────────────────────────────┐
  │                 LiveKit Cloud SFU Edge                 │
  └────────────────────────┬───────────────────────────────┘
                           │
                           ▼
  ┌──────────────────┐   ┌─────────────────────────────────┐
  │ Cartesia STT     │──▶│ Groq Cloud Engine (LLaMA 3.3)   │
  └──────────────────┘   └────────────────┬────────────────┘
                                          │
                               (Function Tool Calls)
                                          │
                  ┌───────────────────────┼──────────────────────┐
                  ▼                       ▼                      ▼
         ┌─────────────────┐    ┌──────────────────┐   ┌──────────────────┐
         │ Open-Meteo API  │    │  Geoapify Places │   │ RapidAPI Flights │
         │ (Live Forecast) │    │  (Hotels/Dining) │   │ (Sky Booking)    │
         └─────────────────┘    └──────────────────┘   └──────────────────┘
                                          │
                               (Aggregated Context)
                                          │
                                          ▼
                               ┌─────────────────────┐
                               │ Cartesia Sonic TTS  │
                               └──────────┬──────────┘
                                          │
                                          ▼ (24kHz PCM Audio Stream)
                                  [ User Speaker ]
```

### 2. Zero-Hallucination Vector RAG Pipeline (`rag-pdf-chatbot`)
```text
  [ Source Document (PDF) ]
              │
              ▼ (PyPDFLoader)
  ┌───────────────────────────────────────┐
  │  RecursiveCharacterTextSplitter       │ ──► [ Overlapping 500-char chunks ]
  └───────────────────────────────────────┘
                                                       │
                                                       ▼
                                     ┌──────────────────────────────────┐
                                     │  all-MiniLM-L6-v2 Embeddings     │
                                     └─────────────────┬────────────────┘
                                                       │
                                                       ▼ (Dense 384d Vectors)
                                     ┌──────────────────────────────────┐
                                     │  Qdrant Local Vector Engine      │
                                     └─────────────────┬────────────────┘
                                                       │
  [ User Query ] ──► [ Query Vector ] ──► (Cosine Similarity Search, top-k=3)
                                                       │
                                                       ▼
                                     ┌──────────────────────────────────┐
                                     │  Prompt Constraint Boundary      │
                                     │  "Answer strictly from context"  │
                                     └─────────────────┬────────────────┘
                                                       │
                                                       ▼
                                     ┌──────────────────────────────────┐
                                     │  OpenRouter LLM (Mistral / OSS)  │
                                     └─────────────────┬────────────────┘
                                                       │
                                                       ▼
                                           [ Grounded Fact-Based Answer ]
```

### 3. Autonomous Terminal Coding Agent (`ALI-CODE`)
```text
  [ User Prompt ]
              │
              ▼ (REPL Input Parser)
  ┌────────────────────────────────────────┐
  │  System Prompt + AGENTS.md Context     │
  └───────────────────┬────────────────────┘
                      │
                      ▼ (tool_choice: auto)
  ┌────────────────────────────────────────┐
  │  LLM Streaming Engine (OpenAI SDK)     │ ◄──── (Loop Until No Tool Calls)
  └───────────────────┬────────────────────┘            ▲
                      │                                 │
                      ▼ (Tool Call Dispatch)             │
  ┌────────────────────────────────────────┐            │
  │  Permission Gate                       │            │
  │  (default / accept-edits / plan / yolo)│            │
  └───────────────────┬────────────────────┘            │
                      │                                 │
                      ▼                                 │
  ┌──────┬───────┬───────┬───────┬────────┐            │
  │ Read │ Write │ Edit  │ Bash  │ Task   │            │
  │      │       │       │       │(Agent) │            │
  └──┬───┴───┬───┴───┬───┴───┬───┴────┬───┘            │
     └───────┴───────┴───────┴────────┘                 │
                      │                                 │
                      ▼ (Tool Results, ≤30k chars)      │
  ┌────────────────────────────────────────┐            │
  │  Context Manager (Auto-Compact @ 75%) │ ───────────┘
  └───────────────────┬────────────────────┘
                      │ (No More Tool Calls)
                      ▼
  ┌────────────────────────────────────────┐
  │  Key Pool Router (Round-Robin)         │
  │  OpenRouter ➔ Groq ➔ OpenAI Failover  │
  │  401→Dead  429→60s Cool  5xx→20s Cool │
  └───────────────────┬────────────────────┘
                      │
                      ▼
            [ Rendered Response ]
```

---

## 📊 Engineering Benchmarks

Technical metrics across all deployed standalone systems:

| System | Primary Task | Model / Backbone | Real-World Metric | Hardware Specs |
|---|---|---|---|---|
| **LiveKit Trip Agent** | Duplex Voice Assistant | LLaMA 3.3 + Cartesia | **< 480ms** speech-to-speech | Standard CPU / Cloud |
| **Ali Code** | Terminal Coding Agent | Multi-Provider LLM Router | **42/42** Unit Tests Passing | Any Terminal / Node 20+ |
| **RAG PDF Chatbot** | Document QA | all-MiniLM + Mistral 7B | **~1.1s** retrieval + synth | CPU (Vector DB on disk) |
| **Urdu Voice Assistant** | Multi-hop Speech Pipeline | Google STT + Mistral 7B | **Zero Crash** audio fallback | CPU + Standard Mic |
| **YOLOv8 Detection** | Custom Face Detection | YOLOv8n (Custom Weights) | **42+ FPS** @ 640×640 | CPU or CUDA GPU |
| **LLM Fine-tuning** | Sentence Pairing & QA | BERT & T5-Small | **0.38 Eval Loss** (MRPC) | Single GPU / Colab |
| **Age & Gender Estimator** | Joint Demographics | Shared CNN Dual-Head | **30 FPS** live webcam | CPU / Standard Webcam |
| **CNN/KNN Face Recognition** | Identity Verification | CNN Classifier vs KNN | **> 96%** Top-1 Accuracy | Standard Laptop |
| **Gesture Game Control** | Gameplay Key Injection | MediaPipe + Key Simulator | **< 35ms** keypress dispatch | Standard PC |

---

## 🛠️ Technical Arsenal

<div align="center">

<img src="https://skillicons.dev/icons?i=python,tensorflow,pytorch,opencv,docker,git,github,linux,vscode,jupyter&perline=10" />

<br/><br/>

| Category | Tools & Libraries |
|:---|:---|
| **Languages** | Python 3.10+, Bash |
| **Deep Learning & Vision** | PyTorch, TensorFlow / Keras, Ultralytics YOLOv8, MediaPipe, OpenCV, scikit-learn |
| **NLP & LLM Systems** | Hugging Face Transformers, LangChain, Qdrant Vector DB, sentence-transformers, OpenRouter |
| **Voice & Autonomous Agents** | LiveKit WebRTC Agents, Groq (LLaMA 3.3), Cartesia Sonic TTS, SpeechRecognition, gTTS |
| **Data & APIs** | Geoapify Places & Weather, RapidAPI Sky Flights, openpyxl, pypdf, NumPy, Pandas |
| **DevOps & Infrastructure** | Docker, GitHub Actions (Automated CI), Git, python-dotenv |

</div>

---

## 🚀 Quick Start

Every project is its own standalone repository with self-contained dependencies and guides:

```bash
# Clone any individual project directly:

# ✈️ Real-time voice agent:
git clone https://github.com/ALIKAZMI001/livekit-trip-agent.git

# 📄 Vector RAG PDF search:
git clone https://github.com/ALIKAZMI001/rag-pdf-chatbot.git

# 🤖 Autonomous Terminal Coding Agent (Ali Code):
git clone https://github.com/ALIKAZMI001/ALI-CODE.git

# 🎙️ Urdu Voice Assistant:
git clone https://github.com/ALIKAZMI001/urdu-voice-assistant.git
```

---

<div align="center">

<img src="https://github-readme-activity-graph.vercel.app/api?username=ALIKAZMI001&theme=tokyo-night&bg_color=0D1117&color=6EE7F7&line=3B82F6&point=ffffff&area=true&hide_border=true" width="100%"/>

<br/><br/>

### 📬 Connect & Collaborate

Have an opportunity or interested in building production AI together?

[![GitHub](https://img.shields.io/badge/GitHub-ALIKAZMI001-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ALIKAZMI001)
[![Email](https://img.shields.io/badge/Email-Contact%20Me-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ali984kazmi@gmail.com)

<br/>

⭐ **If you find these projects valuable, please consider leaving a star!**

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:24243e,50:302B63,100:0F0C29&height=120&section=footer" width="100%"/>

</div>
