# 🎲 Offline BIP39 Seedphrase Generator

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Status: Production Ready](https://img.shields.io/badge/Status-Production_Ready-success)
![Security: Air-Gapped Only](https://img.shields.io/badge/Security-Air--Gapped_Only-red)
![Offline: 100%](https://img.shields.io/badge/Offline-100%25_No_CDN-blue)

[🇬🇧 English](#-english) | [🇹🇭 ภาษาไทย](#-ภาษาไทย)

> 🌐 **Live Demo (Educational Purpose Only):**
> [https://chontit.github.io/bip39-generator/](https://chontit.github.io/bip39-generator/)
> ⚠️ *Never generate your real seed phrase on a networked environment. Demo mode only.*

---

## 🇬🇧 English

A fully offline, single-file HTML BIP39 Seed Generator designed for maximum security and trust-minimization. Ideal for running on air-gapped systems like **Tails OS**.

**"Don't trust, verify."** — This tool uses the native Web Crypto API (`crypto.subtle.digest`) for SHA-256 hashing without relying on any external libraries, internet connections, or third-party fonts. You can audit the entire source code in one standard HTML file.

Co-developed with Claude AI · Audited by Gemini AI · Built by [@chontit](https://github.com/chontit)

---

### ✨ Core Features & Entropy Sources

The system allows you to generate true randomness using physical objects, completely removing the reliance on computer-generated randomness:

| Entropy Source | Base | Description |
|---|---|---|
| **Coin Flips** | Base-2 | Pure binary data (`0` or `1`). Needs 128 to 256 flips. |
| **Hex Dice (16-sided)** | Base-16 | Hexadecimal characters (`0-9`, `a-f`). |
| **Normal Dice (6-sided)** | Base-6 | Standard dice rolls (`1-6`). |
| **Playing Cards** | Base-52 | A standard deck of 52 cards (e.g., `ah` for Ace of Hearts, `7c` for 7 of Clubs). |

You can customize your seed length to generate **12, 15, 18, 21, or 24 words**.

---

### 🔍 Transparent 6-Step Verification Process

This tool doesn't just give you the final words; it shows you exactly how the math works step-by-step so you can verify the cryptography:

1. **Entropy Source:** Displays your raw input data and calculates the total bits of entropy provided.
2. **Processing Mode (Real vs. Hash):**
    * **Real Entropy Mode:** Directly converts your input to binary (no hashing). Every bit directly translates to your final seed.
    * **Hash Mode (1x, 2x, or 3x SHA-256):** Hashes your input to diffuse the bits. *Note: Coins and Hex dice are hashed as Raw Bytes, while Normal Dice and Cards are encoded in UTF-8 before hashing.*
3. **Entropy Extraction:** Slices the required 128-256 bits from the processed data.
4. **Checksum Calculation:** Calculates `SHA-256(entropy)` and extracts the first `ENT/32` bits to create the BIP-39 checksum. The tool highlights the exact hex characters responsible for this.
5. **11-Bit Grouping:** Combines the Entropy and Checksum bits, then cleanly divides them into 11-bit chunks, displaying the decimal index mapping (0-2047) for each.
6. **Mnemonic Generation:** Outputs your final BIP-39 Seed Phrase based on the standard English wordlist embedded within the file.

### ⚙️ Self-Testing Engine

Upon loading, the script runs an automatic engine self-test using standard BIP-39 test vectors to guarantee mathematically flawless execution before you even type a single character:
* **Vector 1 (All Zeros):** Tests a 16-byte zero entropy input. Must resolve exactly to `abandon` (11 times) + `about`.
* **Vector 2 (All 0xff):** Tests a 16-byte maximum entropy input. Must resolve exactly to `zoo` (11 times) + `wrong`.

---

### 📥 Secure Usage Guide

> ⚠️ **NEVER run this tool on a computer connected to the internet.**

1. **Download the file:** Right-click the raw file link and select **Save link as...**
2. **Verify Checksum:** Ensure the file hash matches the values provided below.
3. **Go Offline:** Transfer the file to a clean, offline USB drive.
4. **Boot Tails OS:** Boot your offline machine with internet physically disabled.
5. **Generate:** Open `BIP39-Generator.html` using Tor Browser, input your physical entropy, and generate your Seed Phrase.
6. **Secure & Wipe:** Write your words on paper/metal. Do not take photos. Close the browser and shut down the computer to wipe the RAM.

---

### 🔐 File Verification (Checksums)

To ensure the file has not been tampered with, verify the checksums before use:

**Filename:** `BIP39-Generator.html`
| Algorithm | Hash |
|---|---|
| **SHA-256** | `eca85441538c982b2b1656d3eb08b16c94555c4cb82783af0fc21c5075634ee2` |
| **MD5** | `3bad5bec07329ea7d01d6988b0d90a6d` |

**Verification Commands:**
* **Windows (PowerShell):** `Get-FileHash .\BIP39-Generator.html -Algorithm SHA256`
* **macOS / Linux / Tails OS:** `sha256sum BIP39-Generator.html`

---

## 🇹🇭 ภาษาไทย

เครื่องมือสร้าง **BIP39 Seedphrase** แบบออฟไลน์ 100% ในรูปแบบ "ไฟล์เดียวจบ" (Single-file HTML) ออกแบบมาเพื่อความปลอดภัยสูงสุดและลดการพึ่งพาบุคคลที่สาม (Trust-minimization) เหมาะอย่างยิ่งสำหรับการใช้งานบนระบบที่ถูกตัดขาดจากอินเทอร์เน็ต (Air-gapped) เช่น **Tails OS**

**"Don't trust, verify."** — เครื่องมือนี้ใช้ฟังก์ชัน Web Crypto API ที่ฝังมากับเบราว์เซอร์ (`crypto.subtle.digest`) สำหรับขั้นตอน SHA-256 Hashing เพียงอย่างเดียว โดยไม่ต้องพึ่งพาไลบรารีภายนอก ไม่มี External Links และไม่โหลดข้อมูลใดๆ จากอินเทอร์เน็ต คุณสามารถตรวจสอบ (Audit) ซอร์สโค้ดและตรรกะทางคณิตศาสตร์ทั้งหมดได้ด้วยตาเปล่า

พัฒนาร่วมกับ Claude AI · ตรวจสอบความปลอดภัยโดย Gemini AI · สร้างโดย [@chontit](https://github.com/chontit)

---

### ✨ แหล่งกำเนิด Entropy และคุณสมบัติเด่น

ระบบอนุญาตให้คุณสร้างความสุ่มที่แท้จริงจากวัตถุทางกายภาพ (Physical Randomness) เพื่อตัดปัญหาการสุ่มที่คาดเดาได้จากคอมพิวเตอร์:

| แหล่ง Entropy | ฐาน (Base) | คำอธิบาย |
|---|---|---|
| **การโยนเหรียญ** | ฐาน 2 | ข้อมูล Binary บริสุทธิ์ (`0` หรือ `1`) ต้องโยน 128 - 256 ครั้ง |
| **ลูกเต๋า 16 หน้า** | ฐาน 16 | ข้อมูล Hexadecimal (`0-9`, `a-f`) เหมาะสำหรับผู้ที่มีเต๋า D16 |
| **ลูกเต๋า 6 หน้า** | ฐาน 6 | ลูกเต๋ามาตรฐานทั่วไป (`1-6`) |
| **ไพ่ 1 สำรับ** | ฐาน 52 | ใช้ไพ่ 52 ใบ (เช่น `ah` = A โพแดง, `7c` = 7 ดอกจิก) |

คุณสามารถปรับแต่งความยาวของ Seedphrase ที่ต้องการได้ตั้งแต่ **12, 15, 18, 21, จนถึง 24 คำ**

---

### 🔍 กระบวนการทำงานแบบโปร่งใส 6 ขั้นตอน

เครื่องมือนี้ไม่ได้ทำหน้าที่แค่สุ่มคำให้คุณ แต่จะแสดงการคำนวณทางคณิตศาสตร์อย่างละเอียดในทุกขั้นตอน เพื่อให้คุณสามารถตรวจสอบย้อนกลับได้ (Verify):

1. **ข้อมูลจากการ "สุ่ม" (Entropy Source):** แสดงข้อมูลดิบที่คุณป้อน พร้อมคำนวณปริมาณเอนโทรปีที่ได้ว่าถึงเกณฑ์ความปลอดภัยหรือไม่
2. **โหมดประมวลผล (Processing Mode):**
    * **โหมด Raw Entropy:** นำข้อมูลสุ่มแปลงเป็นเลขฐานสองตรงๆ (ไม่มีการ Hash) ทุกบิตที่เกิดขึ้นมาจากมือคุณ 100%
    * **โหมด Hash (SHA-256 1-3 รอบ):** นำข้อมูลไปผ่านฟังก์ชันแฮชเพื่อกระจายบิตให้สม่ำเสมอ *(ระบบฉลาดพอที่จะแยกแยะว่า ถ้าเป็นเหรียญ/เต๋า16 จะนำ Raw Byte ไปแฮชโดยตรง แต่ถ้าเป็นเต๋า6/ไพ่ จะนำไปเข้ารหัสเป็น UTF-8 ก่อน)*
3. **ดึงข้อมูล Entropy:** ตัดขอบเขตข้อมูลบิตให้พอดีกับจำนวนคำที่ต้องการ (128 - 256 บิต)
4. **คำนวณ Checksum:** ระบบจะนำเอนโทรปีไปเข้าสมการ `SHA-256` และดึงข้อมูลส่วนหัวมา `ENT/32` บิต เพื่อใช้เป็นตัวเช็คความถูกต้อง (Checksum) โดยมีการไฮไลต์ตัวอักษร HEX ที่เป็นต้นทางให้เห็นชัดเจน
5. **รวมบิตและแบ่งชุดละ 11 บิต:** ระบบจะนำเอนโทรปีมาต่อกับ Checksum (เช่น เขียวต่อส้ม) แล้วซอยย่อยออกเป็นก้อนละ 11 บิต เพื่อแปลงเป็นดัชนีตัวเลขฐานสิบ (0-2047)
6. **สร้าง Seed Phrase (BIP-39 Mnemonic):** นำดัชนีไปเทียบกับตารางคำศัพท์ภาษาอังกฤษมาตรฐาน 2048 คำที่ฝังตัวอยู่ในไฟล์ เพื่อออกมาเป็น Seedphrase ลับของคุณ

### ⚙️ ระบบทดสอบตัวเอง (Self-Test Engine)

ทันทีที่เปิดไฟล์ขึ้นมา ระบบจะทำงานทดสอบตัวเองแบบอัตโนมัติ (Automated Test Vectors) เพื่อยืนยันว่า Engine การคำนวณและ Wordlist ทำงานถูกต้องตามมาตรฐาน BIP-39 ทุกประการ ก่อนที่คุณจะเริ่มใช้งาน:
* **Vector 1 (ศูนย์ 16 ไบต์):** ตรวจสอบ Entropy ที่มีแต่บิต `0` ผลลัพธ์ต้องได้คำว่า `abandon` (11 คำ) ตามด้วย `about`
* **Vector 2 (0xff 16 ไบต์):** ตรวจสอบ Entropy ที่มีแต่บิต `1` ผลลัพธ์ต้องได้คำว่า `zoo` (11 คำ) ตามด้วย `wrong`

---

### 📥 วิธีดาวน์โหลดและใช้งาน (ปลอดภัยสูงสุด)

> ⚠️ **กฎเหล็ก: ห้ามป้อนและสร้าง Seed จริงบนคอมพิวเตอร์ที่ต่ออินเทอร์เน็ตเด็ดขาด**

1. **ดาวน์โหลด:** กดคลิกขวาที่ไฟล์นี้แล้วเลือก **Save link as...** ลงในคอมพิวเตอร์
2. **ตรวจสอบความบริสุทธิ์ของไฟล์:** เช็คค่า Hash ตามตารางด้านล่างเพื่อป้องกันมัลแวร์
3. **ตัดขาดโลกภายนอก:** ก๊อปปี้ไฟล์ใส่แฟลชไดร์ฟ บูตคอมพิวเตอร์ด้วยระบบออฟไลน์ที่ไม่มีการจำข้อมูล เช่น **Tails OS** และดึงสาย LAN/Wi-Fi ออก
4. **คำนวณ:** เปิดไฟล์ `BIP39-Generator.html` โยนเหรียญหรือทอยลูกเต๋าของจริง ป้อนข้อมูล และสร้าง Seed Phrase
5. **จดบันทึกและทำลายหลักฐาน:** จดคำศัพท์ลงบนกระดาษหรือตอกลงแผ่นเหล็ก (ห้ามถ่ายรูป) จากนั้นปิดเบราว์เซอร์และสั่ง Shut down คอมพิวเตอร์ทันที เพื่อล้างข้อมูลทั้งหมดใน RAM

---

### 🔐 การตรวจสอบความปลอดภัยของไฟล์ (Checksums)

เพื่อความสบายใจสูงสุด คุณควรตรวจสอบค่า Hash ของไฟล์ก่อนนำไปรันออฟไลน์เสมอ:

**ชื่อไฟล์:** `BIP39-Generator.html`
| อัลกอริทึม | รหัส Hash ที่ถูกต้อง |
|---|---|
| **SHA-256** | `eca85441538c982b2b1656d3eb08b16c94555c4cb82783af0fc21c5075634ee2` |
| **MD5** | `3bad5bec07329ea7d01d6988b0d90a6d` |

**วิธีตรวจสอบบนระบบของคุณ:**
* **Windows (เปิด PowerShell):** พิมพ์คำสั่ง `Get-FileHash .\BIP39-Generator.html -Algorithm SHA256`
* **macOS / Linux / Tails OS (เปิด Terminal):** พิมพ์คำสั่ง `sha256sum BIP39-Generator.html`

---

### 🤝 เครดิตผู้พัฒนา

- **พัฒนาโดย:** [Chollatis Bitcoiner](https://github.com/chontit)
- **AI Co-pilot:** ร่วมออกแบบสถาปัตยกรรมและเขียนโค้ดโดย Claude (Anthropic)
- **Security Audit:** ตรวจสอบตรรกะและช่องโหว่โดย Gemini (Google)

---
*Don't Trust, Verify ⚡*
