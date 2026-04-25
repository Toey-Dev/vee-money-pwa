# Vee Money Dashboard (PWA)

ระบบจัดการเงิน 4 บัญชี | กสิกรไทย + กรุงไทย  
รองรับ OCR สแกนสลิป + ใช้งานบนมือถือเหมือน App

---

## Deploy ขึ้น GitHub Pages (5 นาที)

### ขั้นตอนที่ 1: สร้าง Repository ใหม่
1. ไปที่ https://github.com/new
2. ตั้งชื่อ repo: `vee-money` (หรือชื่ออะไรก็ได้)
3. เลือก **Public** (GitHub Pages ฟรีต้อง Public)
4. กด **Create repository**

### ขั้นตอนที่ 2: Push ไฟล์ขึ้น GitHub
เปิด Terminal/PowerShell ที่โฟลเดอร์ `vee-money-pwa` แล้วรัน:

> เปลี่ยน `YOUR_USERNAME` เป็น username GitHub ของคุณ

### ขั้นตอนที่ 3: เปิด GitHub Pages
1. ไปที่ repo บน GitHub
2. Settings → Pages
3. Source: เลือก **Deploy from a branch**
4. Branch: เลือก `main` / `/ (root)`
5. กด **Save**
6. รอ 1-2 นาที จะได้ URL: `https://YOUR_USERNAME.github.io/vee-money/`

### ขั้นตอนที่ 4: เพิ่มลง Home Screen มือถือ
**iPhone (Safari):**
1. เปิด URL ใน Safari
2. แตะปุ่ม Share (กล่องมีลูกศร)
3. เลือก "Add to Home Screen"
4. กด "Add"

**Android (Chrome):**
1. เปิด URL ใน Chrome
2. แตะเมนู 3 จุด (ขวาบน)
3. เลือก "Add to Home screen" / "Install app"
4. กด "Add"

---

## โครงสร้างไฟล์

```
vee-money-pwa/
├── index.html        ← Dashboard หลัก (PWA + OCR)
├── manifest.json     ← PWA manifest
├── sw.js             ← Service Worker (offline support)
├── icon-192.png      ← App icon 192x192
├── icon-512.png      ← App icon 512x512
└── README.md         ← ไฟล์นี้
```

## หมายเหตุ
- ข้อมูลเก็บใน localStorage ของ browser (แยก PC/มือถือ)
- ใช้ Export/Import JSON ย้ายข้อมูลระหว่างเครื่องได้
- OCR ใช้ Tesseract.js โหลดจาก CDN ครั้งแรก (~2MB) แล้ว cache ไว้ offline
