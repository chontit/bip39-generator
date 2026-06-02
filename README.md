# 🎲 Offline BIP39 Seedphrase Generator

[🇬🇧 English](#english) | [🇹🇭 ภาษาไทย](#ภาษาไทย)

---

<h2 id="english">🇬🇧 English</h2>

A fully offline, single-file HTML BIP39 Seed Generator designed for maximum security and trust-minimization. Ideal for running on air-gapped systems like Tails OS.

**"Don't trust, verify."** — This tool uses the native Web Crypto API (`crypto.subtle.digest`) for SHA-256 hashing without relying on any external libraries, internet connections, or third-party fonts. You can audit the entire source code in one standard HTML file.

### ✨ Features
- **100% Offline & Zero Dependencies:** Contains the standard 2048 English wordlist embedded directly within the file.
- **Multiple Entropy Sources:** Binary (Coin flips), Hex (16-sided dice), Base-6 (6-sided dice), and Base-52 (Deck of cards).
- **Customizable Seed Lengths:** Generate 12, 15, 18, 21, or 24 words.
- **Entropy Processing Modes:** Raw Entropy (pure mathematical conversion) or Single/Double/Triple SHA-256 hashing.
- **Transparent Calculation:** Displays step-by-step bitstreams, checksum calculation, and index mapping.
- **Self-Testing Engine:** Automatically verifies standard BIP39 test vectors upon loading.

### 📥 How to Download and Use
*For the highest level of security, **DO NOT** run this tool on a computer connected to the internet.*
1. **Download the file:** [Right-click here and select "Save link as..."](https://github.com/chontit/bip39-generator/releases/download/v1.0.0/BIP39-Generator.html)
2. Transfer the file to a clean, offline USB drive.
3. Boot your offline machine (e.g., Tails OS) with internet disabled.
4. Open the `BIP39-Generator.html` file using a Tor Browser.

### 🔐 File Verification (Checksums)
To ensure the file has not been tampered with, verify the checksums before use:
**Filename:** `BIP39-Generator.html`
* **SHA256:** `eca85441538c982b2b1656d3eb08b16c94555c4cb82783af0fc21c5075634ee2`
* **MD5:** `3bad5bec07329ea7d01d6988b0d90a6d`

#### How to Verify on Different Operating Systems:
Open your terminal or command prompt in the folder where the file is downloaded and run the following commands:

**Windows (PowerShell):**
```powershell
Get-FileHash .\BIP39-Generator.html -Algorithm SHA256
Get-FileHash .\BIP39-Generator.html -Algorithm MD5
```

**macOS (Terminal):**
```Bash
shasum -a 256 BIP39-Generator.html
md5 BIP39-Generator.html
```

**Linux / Tails OS (Terminal):**
```Bash
sha256sum BIP39-Generator.html
md5sum BIP39-Generator.html
```

---

<h2 id="ภาษาไทย">🇹🇭 ภาษาไทย</h2>

เครื่องมือสร้าง BIP39 Seedphrase แบบออฟไลน์ 100% ในรูปแบบ "ไฟล์เดียวจบ" (Single-file HTML) ออกแบบมาเพื่อความปลอดภัยสูงสุดและลดการพึ่งพาบุคคลที่สาม (Trust-minimization) เหมาะอย่างยิ่งสำหรับการใช้งานบนระบบที่ปลอดภัยจากอินเทอร์เน็ต (Air-gapped) เช่น Tails OS

**"Don't trust, verify."** — เครื่องมือนี้ใช้ Web Crypto API ที่ฝังมากับเบราว์เซอร์ (`crypto.subtle.digest`) สำหรับขั้นตอน SHA-256 hashing โดยไม่ต้องพึ่งพาไลบรารีภายนอก หรือโหลดฟอนต์จากอินเทอร์เน็ต คุณสามารถตรวจสอบและ Audit ซอร์สโค้ดทั้งหมดได้ด้วยตาเปล่าในไฟล์เดียว

### ✨ คุณสมบัติเด่น
- **ออฟไลน์ 100%:** ฝังรายการคำศัพท์ภาษาอังกฤษ 2048 คำมาตรฐาน (BIP39 Wordlist) ไว้ในโค้ดแล้ว
- **รองรับแหล่ง Entropy หลากหลาย:** การโยนเหรียญ (ฐาน 2), ทอยลูกเต๋าแบบ 16 หน้า (ฐาน 16), ทอยลูกเต๋า 6 หน้า (ฐาน 6) และการสุ่มไพ่ 1 สำรับ (ฐาน 52)
- **ปรับแต่งความยาว Seedphrase ได้:** รองรับการสร้างชุดคำ 12, 15, 18, 21, หรือ 24 คำ
- **โหมดประมวลผล Entropy:** เลือกได้ทั้งแบบ Raw Entropy (คำนวณคำจาก Raw Bit ตรงๆ ไม่ผ่านแฮช) หรือเลือกแบบผ่านกระบวนการ SHA-256 Hashing (1, 2, หรือ 3 รอบ) ได้
- **ความโปร่งใส:** แสดงบิตสตรีม การคำนวณ Checksum และการจับคู่ Index ให้เห็นทุกขั้นตอน
- **ระบบทดสอบตัวเอง (Self-Test):** ตรวจสอบความถูกต้องของการคำนวณกับ Test Vector มาตรฐานทันทีที่เปิดหน้าเว็บ เพื่อให้ผู้ใช้งานเกิดความมั่นใจว่าระบบทำงานอย่างถูกต้อง

### 📥 วิธีดาวน์โหลดและใช้งาน
*เพื่อความปลอดภัยสูงสุด **ห้าม** ใช้งาน Seedphrase ที่สร้างจากไฟล์นี้บนคอมพิวเตอร์ที่เชื่อมต่ออินเทอร์เน็ตโดยเด็ดขาด*
1. **ดาวน์โหลดไฟล์:** [คลิกขวาที่ลิงก์นี้แล้วเลือก "Save link as..."](https://github.com/chontit/bip39-generator/releases/download/v1.0.0/BIP39-Generator.html)
2. คัดลอกไฟล์ลงใน USB Flash Drive ที่มีความปลอดภัย
3. บูตเข้าสู่ระบบปฏิบัติการออฟไลน์ (เช่น Tails OS) 
4. เปิดไฟล์ `BIP39-Generator.html` ผ่านเบราว์เซอร์ (Tor Browser)
5. นำ Seedphrase ที่ได้ไปใช้งานร่วมกับ Hardware Wallet หรือ Software Wallet ที่ทำงานผ่าน Tails OS (Sparrow Wallet, Electrum Bitcoin Wallet)

### 🔐 การตรวจสอบความถูกต้องของไฟล์ (Checksums)
ก่อนใช้งานจริงทุกครั้ง ควรตรวจสอบค่า Hash เพื่อยืนยันว่าไฟล์ไม่ได้ถูกดัดแปลง:
**ชื่อไฟล์:** `BIP39-Generator.html`
* **SHA256:** `eca85441538c982b2b1656d3eb08b16c94555c4cb82783af0fc21c5075634ee2`
* **MD5:** `3bad5bec07329ea7d01d6988b0d90a6d`

#### วิธีตรวจสอบบนระบบปฏิบัติการต่างๆ:
เปิดโปรแกรม Terminal หรือ Command Prompt ในโฟลเดอร์ที่ดาวน์โหลดไฟล์ไว้ แล้วพิมพ์คำสั่งดังต่อไปนี้:

**Windows (PowerShell):**
```PowerShell
Get-FileHash .\BIP39-Generator.html -Algorithm SHA256
Get-FileHash .\BIP39-Generator.html -Algorithm MD5
```

**macOS (Terminal):**
```Bash
shasum -a 256 BIP39-Generator.html
md5 BIP39-Generator.html
```

**Linux / Tails OS (Terminal):**
```Bash
sha256sum BIP39-Generator.html
md5sum BIP39-Generator.html
```
