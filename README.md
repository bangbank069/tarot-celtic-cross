# 🌙 Celtic Cross Tarot Reader

Web app ทำนายไพ่ยิปซี 10 ตำแหน่ง (Celtic Cross / ทศดารา) ภาษาไทย  
ขับเคลื่อนด้วย Google Gemini AI — ทำงานเป็น Static Site เปิดจาก browser ได้เลย

![preview](https://img.shields.io/badge/status-ready-brightgreen) ![license](https://img.shields.io/badge/license-MIT-blue)

---

## ✨ Features

- ไพ่ครบ 78 ใบ — Major Arcana 22 ใบ + Minor Arcana 56 ใบ
- Celtic Cross spread 10 ตำแหน่งพร้อมความหมายแต่ละตำแหน่ง
- ค้นหาไพ่ได้ในหน้า modal
- กรอกข้อมูลเจ้าของดวง (ชื่อ, วันเกิด, เวลาเกิด) เพื่อเพิ่มความแม่นยำ
- AI อ่านคำทำนายภาษาไทยโดย Google Gemini 2.5 Flash
- บันทึกคำทำนายลง browser (สูงสุด 10 ครั้ง) — ดูย้อนหลังได้
- Dark theme, Responsive (mobile-friendly)
- API Key เก็บใน localStorage เท่านั้น — ไม่ถูกส่งออกไปที่อื่น

---

## 🚀 วิธีใช้งาน

### 1. รับ Gemini API Key (ฟรี)

1. เข้า [Google AI Studio](https://aistudio.google.com/app/apikey)
2. กด **Get API Key** → Create API key
3. Copy key ที่ได้ไว้

### 2. เปิด App

```
เปิดไฟล์ index.html ด้วย browser โดยตรง
หรือ serve ผ่าน web server ใดก็ได้
```

> **GitHub Pages:** Push repo แล้วเปิด Settings → Pages → Deploy from branch `main`

### 3. ใส่ API Key

เมื่อเปิด app ครั้งแรก จะมี popup ให้กรอก API Key  
(กดปุ่ม ⚙️ API Key มุมขวาบนเพื่อแก้ไขภายหลัง)

### 4. เลือกไพ่ & ทำนาย

1. กรอกข้อมูลเจ้าของดวง (ไม่บังคับ)
2. กดช่องไพ่แต่ละตำแหน่ง → เลือกไพ่ให้ครบ 10 ตำแหน่ง
3. กด **อ่านคำทำนาย**
4. กด **บันทึกคำทำนายนี้** เพื่อเก็บไว้ดูย้อนหลัง

---

## 📁 โครงสร้างไฟล์

```
V.2/
├── index.html          ← แอปทั้งหมด (HTML + CSS + JS)
└── images/             ← ภาพไพ่ทาโรต์ 78 ใบ (.png)
    ├── ar00.png        ← The Fool
    ├── ar01.png        ← The Magician
    ├── ...             ← Major Arcana (ar00–ar21)
    ├── waac.png        ← Ace of Wands
    ├── ...             ← Wands (wa*)
    ├── cuac.png        ← Ace of Cups
    ├── ...             ← Cups (cu*)
    ├── swac.png        ← Ace of Swords
    ├── ...             ← Swords (sw*)
    ├── peac.png        ← Ace of Pentacles
    └── ...             ← Pentacles (pe*)
```

### ชื่อไฟล์ภาพ

| ชุด | Prefix | ตัวอย่าง |
|-----|--------|---------|
| Major Arcana | `ar` | `ar00.png` (Fool) … `ar21.png` (World) |
| Wands | `wa` | `waac.png` (Ace), `wa02.png`–`wa10.png`, `wapa.png`, `wakn.png`, `waqu.png`, `waki.png` |
| Cups | `cu` | `cuac.png`, `cu02.png`–`cu10.png`, `cupa.png`, … |
| Swords | `sw` | `swac.png`, `sw02.png`–`sw10.png`, `swpa.png`, … |
| Pentacles | `pe` | `peac.png`, `pe02.png`–`pe10.png`, `pepa.png`, … |

> ถ้าภาพในเครื่องโหลดไม่ได้ จะ fallback ไปดึงจาก Wikimedia Commons อัตโนมัติ

---

## 🔑 API Key & Privacy

- API Key เก็บใน `localStorage` ของ browser เท่านั้น
- ไม่มี backend — ทุก request ส่งตรงจาก browser → Google Gemini API
- **ไม่ commit API Key ลง Git** — `.gitignore` ครอบคลุมไฟล์ config แล้ว

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML / CSS / JavaScript |
| CSS Framework | Tailwind CSS (CDN) |
| Icons | Lucide Icons (CDN) |
| Fonts | Google Fonts — Prompt |
| AI | Google Gemini 2.5 Flash |
| Storage | localStorage (API Key + History) |

---

## 📄 License

MIT License — ใช้และดัดแปลงได้อย่างอิสระ
