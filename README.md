# AoV SoundCheck (Web Version)

A tool for comparing Arena of Valor `.bytes` files between the **TH (Thailand)** and **VNT (Vietnam)** servers. It shows which `Hero_*` and `Play_*` sound entries are shared and which exist on only one side.

It runs entirely in your browser. **Your files are never uploaded anywhere and are never modified.**

## How to use

1. Open the page in a desktop browser (Chrome, Edge, or Firefox recommended).
2. Under **TH**, click **Choose folder…** and select the folder containing the Thai `.bytes` files.
3. Under **VNT**, do the same with the Vietnamese folder.
   - Your browser will ask for permission to read the files. Allow it (files are only read locally).
   - All subfolders are scanned automatically, and files are paired by **file name**.
4. Click **Compare folders** (or press F5) and wait until the status bar at the bottom says Done.
5. Pick a file from the list on the left to see its comparison.

## Reading the results

**Overview panel (left)** summarizes all files combined.

| Color | Meaning |
|---|---|
| Green (Shared) | Entries present on both sides |
| Red (TH only) | Entries present only on the Thai side |
| Blue (VNT only) | Entries present only on the Vietnamese side |

**File list (left)**
- ✓ File with identical entries on both sides
- ● File with differing entries (the number on the right is how many differ)
- ⚠ File that exists on only one side
- The search box filters by file name, and **Differences only** hides files that are fully identical

**Results area (right)**
- The badges at the top show the token count and decode status for each side:
  - `ZSTD ✓` decoded successfully
  - `Raw` the file is not compressed, so raw bytes are used
  - `Decode failed` decoding failed and raw bytes are used instead (the file may be AES-encrypted or use a different dictionary version)
  - `File missing` the file does not exist on that side
- Filter buttons **All entries / Both / TH Only / VNT Only** and an entry search box
- The table shows up to 3,000 rows at a time. If there are more, type in the search box to narrow it down.

## Copying and exporting

- Click a row to select it (Ctrl+click to select several).
- Double-click, or press Ctrl+C, to copy the selected entries.
- The **CSV / JSON / TXT** buttons at the top right export a report for **all files** (not limited to 3,000 rows).

## Keyboard shortcuts

| Key | Action |
|---|---|
| F5 | Start comparison |
| Ctrl+F | Focus the entry search box |
| Ctrl+E | Export CSV |
| Ctrl+C | Copy selected entries |

## Notes

- Both folders must be selected before Compare is enabled.
- If the same file name appears in several subfolders, the one found last is used.
- Large folders may take a while. Progress is shown in the status bar.
- Folder selection is not supported in many mobile browsers.
- The tool only decodes Zstandard data that uses the AoV dictionary.
[Uploading README.en.md…]()

# AoV SoundCheck (เวอร์ชันเว็บ)

เครื่องมือเปรียบเทียบไฟล์ `.bytes` ของ Arena of Valor ระหว่างเซิร์ฟเวอร์ **TH (ไทย)** และ **VNT (เวียดนาม)** เพื่อดูว่ามี entry เสียง `Hero_*` และ `Play_*` ตัวไหนที่ใช้ร่วมกัน หรือมีเฉพาะฝั่งใดฝั่งหนึ่ง

ทำงานในเบราว์เซอร์ทั้งหมด **ไฟล์ของคุณไม่ถูกอัพโหลดไปที่ไหน และไม่ถูกแก้ไข**

## วิธีใช้งาน

1. เปิดหน้าเว็บด้วยเบราว์เซอร์บนคอมพิวเตอร์ (แนะนำ Chrome, Edge หรือ Firefox)
2. ในช่อง **TH** กด **Choose folder…** แล้วเลือกโฟลเดอร์ที่มีไฟล์ `.bytes` ของฝั่งไทย
3. ในช่อง **VNT** ทำแบบเดียวกันกับโฟลเดอร์ฝั่งเวียดนาม
   - เบราว์เซอร์จะถามยืนยันการเข้าถึงไฟล์ ให้กดอนุญาต (เป็นการอ่านในเครื่องเท่านั้น)
   - ระบบสแกนไฟล์ `.bytes` ในโฟลเดอร์ย่อยทั้งหมดให้อัตโนมัติ และจับคู่ไฟล์จาก **ชื่อไฟล์**
4. กด **Compare folders** (หรือ F5) แล้วรอจนแถบสถานะด้านล่างขึ้นว่า Done
5. เลือกไฟล์จากรายการด้านซ้ายเพื่อดูผลเปรียบเทียบของไฟล์นั้น

## อ่านผลลัพธ์

**แถบ Overview (ซ้าย)** สรุปทุกไฟล์รวมกัน

| สี | ความหมาย |
|---|---|
| เขียว (Shared) | entry ที่มีทั้งสองฝั่ง |
| แดง (TH only) | entry ที่มีเฉพาะฝั่งไทย |
| ฟ้า (VNT only) | entry ที่มีเฉพาะฝั่งเวียดนาม |

**รายการไฟล์ (ซ้าย)**
- ✓ ไฟล์ที่เหมือนกันทุก entry
- ● ไฟล์ที่มี entry ต่างกัน (ตัวเลขด้านขวาคือจำนวนที่ต่าง)
- ⚠ ไฟล์ที่มีเพียงฝั่งเดียว
- ช่องค้นหาใช้กรองตามชื่อไฟล์ และปุ่ม **Differences only** ซ่อนไฟล์ที่เหมือนกันทั้งหมด

**ส่วนผลลัพธ์ (ขวา)**
- ป้ายด้านบนบอกจำนวน token และสถานะการถอดรหัสของแต่ละฝั่ง:
  - `ZSTD ✓` ถอดรหัสสำเร็จ
  - `Raw` ไฟล์ไม่ได้บีบอัด ใช้ข้อมูลดิบ
  - `Decode failed` ถอดรหัสไม่สำเร็จ จึงใช้ข้อมูลดิบแทน (ไฟล์อาจเข้ารหัสด้วย AES หรือใช้ดิกชันนารีคนละเวอร์ชัน)
  - `File missing` ไม่มีไฟล์ในฝั่งนั้น
- ปุ่มกรอง **All entries / Both / TH Only / VNT Only** และช่องค้นหา entry
- ตารางแสดงสูงสุด 3,000 แถวต่อครั้ง ถ้ามีมากกว่านั้นให้พิมพ์ค้นหาเพื่อกรอง

## คัดลอกและส่งออก

- คลิกแถวเพื่อเลือก (Ctrl+คลิกเพื่อเลือกหลายแถว)
- ดับเบิลคลิกหรือกด Ctrl+C เพื่อคัดลอก entry ที่เลือก
- ปุ่ม **CSV / JSON / TXT** ที่มุมขวาบนส่งออกรายงานของ **ทุกไฟล์** (ไม่ถูกจำกัดที่ 3,000 แถว)

## คีย์ลัด

| คีย์ | การทำงาน |
|---|---|
| F5 | เริ่มเปรียบเทียบ |
| Ctrl+F | ไปที่ช่องค้นหา entry |
| Ctrl+E | ส่งออก CSV |
| Ctrl+C | คัดลอก entry ที่เลือก |

## ข้อควรรู้

- ต้องเลือกครบทั้งสองโฟลเดอร์ก่อนจึงจะกด Compare ได้
- หากมีไฟล์ชื่อซ้ำกันในหลายโฟลเดอร์ย่อย ระบบจะใช้ไฟล์ที่พบทีหลัง
- โฟลเดอร์ขนาดใหญ่อาจใช้เวลาสักครู่ ดูความคืบหน้าได้ที่แถบด้านล่าง
- การเลือกโฟลเดอร์ไม่รองรับในเบราว์เซอร์มือถือหลายรุ่น
- เครื่องมือนี้ถอดรหัสเฉพาะ Zstandard ที่ใช้ดิกชันนารีของ AoV เท่านั้น

<img width="1297" height="869" alt="image" src="https://github.com/user-attachments/assets/bf6c4d62-8c11-4ca9-91a8-8e88c022aaa6" />

