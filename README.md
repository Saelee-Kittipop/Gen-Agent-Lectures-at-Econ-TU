# Teaching Materials: Generative Agents for Retail Simulation

> **เปิด Slides ได้เลย:** [https://tiraphap.github.io/Gen-Agent-Lectures-at-Econ-TU/](https://tiraphap.github.io/Gen-Agent-Lectures-at-Econ-TU/)

## Overview

สื่อการสอนชุดนี้ออกแบบมาเพื่อให้เข้าใจ **Generative Agents** ตั้งแต่ทฤษฎีจาก papers จนถึงการนำไปประยุกต์ใช้จริงในโปรเจค Retail Customer Behavior Simulation

### Papers ที่ใช้อ้างอิง

| # | Paper | ผู้แต่ง | สิ่งที่เรียนรู้ |
|---|-------|---------|----------------|
| 1 | [**Generative Agents: Interactive Simulacra of Human Behavior**](https://arxiv.org/abs/2304.03442) (2023) | Joon Sung Park et al., Stanford | สถาปัตยกรรมพื้นฐาน: Memory Stream, Retrieval, Reflection |
| 2 | [**Generative Agent Simulations of 1,000 People**](https://arxiv.org/abs/2411.10109) (2024) | Joon Sung Park et al. | การ scale ระบบไปสู่ 1,000 agents + การ validate กับคนจริง |

---

## โครงสร้าง Materials

```
teaching/
├── slides/          → Reveal.js slides (เปิดใน browser)
├── notebooks/       → Jupyter / Google Colab (เนื้อหาหลัก)
├── demos/           → Jupyter notebooks สำหรับ demo (interactive)
└── exercises/       → แบบฝึกหัด + เฉลย (Jupyter notebooks)
```

**ทุกไฟล์เป็น `.ipynb`** (ยกเว้น slides) → เปิดใน Google Colab ได้ทันที!

### 1. Slides (`slides/`)
- เปิดไฟล์ `slides/generative-agents-slides.html` ใน browser ได้เลย (ไม่ต้อง install อะไร)
- มี interactive elements: Memory Score Calculator, Personality Sliders
- ใช้ลูกศร ← → เปลี่ยนสไลด์, ลูกศร ↑ ↓ เข้า sub-sections

### 2. Notebooks (`notebooks/`)
- รันได้ทั้งใน **Google Colab** และ **Jupyter Notebook** ในเครื่อง
- ทุก notebook มี toggle `USE_REAL_LLM = False` รันได้โดยไม่ต้องมี API key
- เรียงลำดับจากง่ายไปยาก: 01 → 02 → 03

### 3. Demos (`demos/`)
- Jupyter notebooks สำหรับ demo แบบ interactive
- `demo_memory.ipynb` ไม่ต้องใช้ LLM (รันได้เลย!)
- `demo_cognitive_loop.ipynb` ใช้ LLM หรือ mock ก็ได้
- `demo_multi_agent.ipynb` เปรียบเทียบ 3 agents

### 4. Exercises (`exercises/`)
- แบบฝึกหัดสำหรับ นศ. ทำเอง (Jupyter notebooks)
- มีเฉลยใน `exercises/solutions/`

---

## Quick Start

### วิธีที่ 1: Google Colab (แนะนำ - ไม่ต้อง install อะไร)
1. Upload notebook (.ipynb) ไปที่ Google Drive
2. Double-click เปิดด้วย Google Colab
3. Run ทุก cell ได้เลย (ตั้ง `USE_REAL_LLM = False`)

### วิธีที่ 2: Jupyter Notebook ในเครื่อง
```bash
# 1. Clone repo
git clone <repo-url>
cd Gen-Agent-Lectures-at-Econ-TU

# 2. สร้าง virtual environment
python -m venv venv
source venv/bin/activate  # Mac/Linux
# หรือ venv\Scripts\activate  # Windows

# 3. Install dependencies
pip install -r requirements.txt jupyter

# 4. เปิด Jupyter
jupyter notebook teaching/
```

---

## ลำดับการเรียน (แนะนำ)

```
Step 1: ดู Slides ทั้งหมด (30 นาที)
   ↓
Step 2: Notebook 01 - Memory Stream (45 นาที)
   ↓
Step 3: รัน demo_memory.ipynb ดูผลจริง (15 นาที)
   ↓
Step 4: Notebook 02 - Cognitive Loop (60 นาที)
   ↓
Step 5: ทำ Exercise 01-02 (45 นาที)
   ↓
Step 6: Notebook 03 - Full Simulation (60 นาที)
   ↓
Step 7: ทำ Exercise 03 - สร้าง agent ของตัวเอง (60 นาที)
```

---

## Requirements

- Python 3.9+
- ไม่จำเป็นต้องมี OpenAI API key (ใช้ mock responses ได้)
- Browser สำหรับดู slides

### Python packages (install ผ่าน pip)
```
openai>=1.0.0        # สำหรับ LLM จริง (optional)
python-dotenv        # อ่าน .env file
pydantic>=2.0.0      # Data validation
```

---

## Roadmap

- [ ] **Vector Embeddings สำหรับ Relevance** — ปัจจุบันใช้ keyword matching ในการคำนวณ relevance score อยู่ ในอนาคตจะเปลี่ยนมาใช้ vector embeddings ตามที่ paper ต้นฉบับเสนอ เพื่อให้การ retrieve memory แม่นยำขึ้น
