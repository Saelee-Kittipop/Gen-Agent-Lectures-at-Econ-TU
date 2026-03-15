# Teaching Demos: Generative Agents for Retail Simulation

สื่อการสอนสำหรับนักศึกษา เรื่อง Generative Agents ในการจำลองพฤติกรรมลูกค้า

## Prerequisites

- Python 3.8+
- ไม่ต้องติดตั้ง library เพิ่ม (ใช้แค่ standard library)
- ถ้าอยากใช้ LLM จริง: `pip install openai` + ตั้งค่า `OPENAI_API_KEY`

## Demo Files

### Demo 1: Memory Stream (`demo_memory.py`)

ระบบความทรงจำของ Agent - หัวใจของ Generative Agents

```bash
python demo_memory.py
```

**สิ่งที่จะได้เรียนรู้:**
- Memory Stream คืออะไร เก็บข้อมูลอะไรบ้าง
- ประเภทความทรงจำ: Observation, Reflection, Plan
- สูตร Retrieval: `score = recency x importance x relevance`
- วิธีคำนวณคะแนนแต่ละส่วน
- ทำไม query ต่างกัน ให้ผลลัพธ์ต่างกัน

**ไม่ต้องใช้ LLM** - ทุกอย่างเป็น pure Python

---

### Demo 2: Cognitive Loop (`demo_cognitive_loop.py`)

วงจรการคิด 5 ขั้นตอนของ Agent

```bash
python demo_cognitive_loop.py
```

**สิ่งที่จะได้เรียนรู้:**
- 5 ขั้นตอน: PERCEIVE → RETRIEVE → PLAN → EXECUTE → REFLECT
- ขั้นตอนไหนใช้ LLM ขั้นตอนไหนไม่ใช้
- Prompt ที่ส่งให้ LLM หน้าตาเป็นอย่างไร
- Chain-of-Thought: Agent คิดทีละขั้นตอนอย่างไร
- Reflection: Agent เรียนรู้จากประสบการณ์อย่างไร

**Toggle LLM:** แก้ `USE_REAL_LLM = True` ที่บรรทัดบนสุดเพื่อใช้ OpenAI API จริง

---

### Demo 3: Multi-Agent Comparison (`demo_multi_agent.py`)

เปรียบเทียบ Agent 3 คนที่มี personality ต่างกัน

```bash
python demo_multi_agent.py
```

**สิ่งที่จะได้เรียนรู้:**
- Personality Traits 6 ตัว ส่งผลต่อการตัดสินใจอย่างไร
- สถานการณ์เดียวกัน → คนต่างกัน → ตัดสินใจต่างกัน
- ข้อดีของ LLM-based vs Rule-based simulation
- วิเคราะห์ว่า trait ไหนทำให้เลือกร้านไหน

**Toggle LLM:** แก้ `USE_REAL_LLM = True` เพื่อให้ LLM ตัดสินใจจริง

---

## ลำดับการสอนที่แนะนำ

1. **Demo 1** (Memory) - เข้าใจระบบความทรงจำก่อน
2. **Demo 2** (Cognitive Loop) - เห็นภาพรวมวงจรการคิด
3. **Demo 3** (Multi-Agent) - เห็นว่า personality ส่งผลอย่างไร

## หมายเหตุ

- ทุกไฟล์ self-contained รันได้อิสระ ไม่ต้องรันตามลำดับ
- Output มีสีสัน (ANSI colors) ควรรันใน terminal ที่รองรับ
- กด Enter เพื่อดูทีละขั้นตอน เหมาะสำหรับการสอนในห้องเรียน
- Comments ทั้งหมดเป็นภาษาไทย อธิบายละเอียดทุกขั้นตอน
