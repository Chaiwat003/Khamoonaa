# NomNaa - Instagram Caption Generator 🎨

ตัวสร้างแคปชั่น Instagram สำหรับเมนูอาหารในคาเฟ่ Nomnaa โดยใช้ AI (Google Gemini 2.5 Flash)

## ✨ ฟีเจอร์

- 🎯 สร้างแคปชั่น Instagram 3 แบบสไตล์ต่าง ๆ:
  - **Cute**: น่ารัก สนุกสนาน มีอีโมจิ
  - **Minimal**: สวยหรู เรียบร้อย ใช้คำน้อย
  - **Gen-Z**: ทันสมัย ตลกขบขัน เข้าใจง่าย
- 🤖 ใช้ Google Gemini API สำหรับการสร้างเนื้อหา
- 🔄 รับข้อมูลจากผู้ใช้ผ่าน input
- 📝 ผลลัพธ์เป็นภาษาไทย

## 📋 ความต้องการ

- Python 3.8 ขึ้นไป
- Google API Key (สำหรับ Gemini)
- `google-generativeai` library
- `python-dotenv` library

## 🚀 วิธีการใช้งาน

### 1. ติดตั้ง Dependencies

```bash
pip install google-generativeai python-dotenv
```

### 2. ตั้งค่า Environment Variables

สร้างไฟล์ `.env` ในโฟลเดอร์โปรเจกต์:

```
GOOGLE_API_KEY=your_google_api_key_here
```

> 📌 ได้ API Key จาก [Google AI Studio](https://aistudio.google.com/apikey)

### 3. รันโปรแกรม

```bash
python caption.py
```

ระบบจะขอให้คุณป้อนข้อมูล:
- 🍽️ ชื่อเมนู (เช่น "Matcha Latte")
- 💰 ราคา (เช่น "120")

### 4. ดูผลลัพธ์

โปรแกรมจะแสดง 3 แคปชั่นที่สร้างขึ้นมา พร้อมตัวอย่าง:

```
==================================================
📝 Cute:
[แคปชั่นน่ารัก...]

==================================================
✨ Minimal:
[แคปชั่นสวยหรู...]

==================================================
🚀 Gen-Z:
[แคปชั่นทันสมัย...]
==================================================
```

## 📁 โครงสร้างไฟล์

```
NomNaa/
├── caption.py          # โปรแกรมสร้างแคปชั่น
├── test.py            # ตัวอย่างฟังก์ชัน (ไม่เกี่ยวข้อง)
├── .env               # Environment variables
├── .gitignore         # Git ignore rules
└── README.md          # ไฟล์นี้
```

## 🔧 ฟังก์ชั่นหลัก

### `generate_captions(menu_name: str, price: float) -> Dict[str, str]`
สร้างแคปชั่น 3 แบบสำหรับเมนูโดยใช้ Gemini API

**Parameters:**
- `menu_name` (str): ชื่อรายการเมนู
- `price` (float): ราคา (บาท)

**Returns:**
- Dictionary ที่มี keys: "Cute", "Minimal", "Gen-Z"

### `parse_captions(response_text: str) -> Dict[str, str]`
แยกแคปชั่นจากการตอบกลับของโมเดล

## ⚙️ ตัวแปร Environment

| ตัวแปร | คำอธิบาย |
|--------|---------|
| `GOOGLE_API_KEY` | Google API Key สำหรับใช้ Gemini API |

## 📝 ตัวอย่างการใช้งาน

```python
from caption import generate_captions

# สร้างแคปชั่นสำหรับเมนู
captions = generate_captions("Iced Americano", 79.0)

# แสดงผลลัพธ์
print(captions['Cute'])
print(captions['Minimal'])
print(captions['Gen-Z'])
```

## 🎯 Case Use

- 📱 สร้างแคปชั่น Instagram สำหรับโพสต์เมนูใหม่
- 🎨 ทดลองรูปแบบการเขียนแบบต่าง ๆ
- ⚡ ประหยัดเวลาในการ copywriting

## 🐛 แก้ไขปัญหา

### "ModuleNotFoundError: No module named 'google'"
```bash
pip install google-generativeai
```

### "GOOGLE_API_KEY not found"
ตรวจสอบว่า:
- ไฟล์ `.env` อยู่ในโฟลเดอร์เดียวกับ `caption.py`
- `.env` มี `GOOGLE_API_KEY=...` ถูกต้อง

### "ValueError: ราคาต้องเป็นตัวเลข"
ป้อนราคาเป็นตัวเลขเท่านั้น (เช่น 120 ไม่ใช่ "120 บาท")

## 📄 License

ยังไม่ระบุ

## 👨‍💻 Author

NomNaa Cafe Team