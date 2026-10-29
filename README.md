AoV SoundCheckTool 2.0

รายละเอียดการปรับปรุง 
1. สิ่งที่ปรับปรุง
โครงสร้างหน้าจอ

เดิมเรียงจากบนลงล่าง ตอนนี้แบ่งเป็น 2 ส่วน

Sidebar ซ้าย (ตั้งค่าและภาพรวม)

SOURCES: การ์ดโฟลเดอร์ TH (แดง) และ VNT (ฟ้า) แต่ละใบมีช่องพาธ ปุ่ม Browse และสถานะ ✓ found / ✗ not found
ปุ่ม Compare folders พร้อมแถบความคืบหน้าที่โผล่ขึ้นเฉพาะตอนกำลังเปรียบเทียบ
OVERVIEW: จำนวนไฟล์ทั้งหมด จำนวนไฟล์ที่ต่างกัน แถบสัดส่วน Shared / TH only / VNT only และตัวเลขพร้อมเปอร์เซ็นต์
FILES: รายการไฟล์ พร้อมช่องค้นหาและตัวเลือก “Differences only”

พื้นที่ขวา (ผลลัพธ์)

ชื่อไฟล์ที่เลือก ป้ายสถานะการถอดรหัสของ TH/VNT และปุ่ม Export
แถบสัดส่วนของไฟล์นั้น
ปุ่มกรองพร้อมตัวเลข และช่องค้นหา
ตารางผลลัพธ์ และบรรทัดสรุปจำนวนที่แสดง
หน้าตา
ธีมสีใหม่: พื้นดำอมน้ำเงิน สีหลักม่วง มีเส้นไล่สีม่วงไปฟ้าด้านบน
สีสถานะ: Shared เขียว, TH only แดง, VNT only ฟ้า
ตารางใช้ฟอนต์ Consolas แถวสลับสี อ่านชื่อ Hero_... / Play_... ง่ายขึ้น
Scrollbar แบบเรียว ไม่มีลูกศร
แถบชื่อหน้าต่างเป็นสีเข้มบน Windows 10/11
รองรับจอความละเอียดสูง ตัวอักษรคมขึ้น
ขนาดหน้าต่างถูกจำกัดไม่ให้สูงเกินจอ แถบสถานะด้านล่างจึงไม่ถูกบัง
การใช้งาน
การเปรียบเทียบรันเบื้องหลัง หน้าต่างไม่ค้างเมื่อโฟลเดอร์ใหญ่ และเห็นว่ากำลังประมวลผลไฟล์ไหนอยู่
ตรวจพาธให้ทันทีที่พิมพ์หรือเลือก
หลังกด Browse ช่องพาธจะเลื่อนไปแสดงท้ายพาธ
คัดลอก entry ได้ด้วยดับเบิลคลิก, Ctrl+C หรือคลิกขวา
ค้นหามีดีเลย์สั้นๆ ไม่กระตุกเมื่อพิมพ์เร็ว
ถ้าผลลัพธ์เกิน 20,000 แถว จะแสดงเฉพาะส่วนแรกพร้อมข้อความบอก
ส่วนที่ไม่เปลี่ยน

ลอจิกการเปรียบเทียบ การถอดรหัส ZSTD (dictionary เหมือนต้นฉบับทุกไบต์) และรูปแบบไฟล์ส่งออก CSV/JSON/TXT

2. วิธีใช้งาน
ติดตั้งและเปิดโปรแกรม
ติดตั้ง Python 3.10 ขึ้นไป (ติ๊ก “Add Python to PATH” ตอนติดตั้ง)
แตก zip แล้วดับเบิลคลิก Run_SoundCheck.bat ซึ่งจะติดตั้ง pyzstd ให้และเปิดโปรแกรม

ถ้าต้องการไฟล์ .exe ให้รัน Build_Windows_EXE.bat (ต้องต่ออินเทอร์เน็ต) จะได้ไฟล์ที่ dist\AoV_SoundCheckTool.exe

ขั้นตอนเปรียบเทียบ
ที่การ์ด Thailand กด Browse แล้วเลือกโฟลเดอร์ที่มีไฟล์ .bytes ของ TH หรือวางพาธลงในช่องก็ได้
ทำแบบเดียวกันกับการ์ด Vietnam
เมื่อพาธทั้งสองขึ้น ✓ found กด Compare folders (หรือ F5 หรือกด Enter ในช่องพาธ)
รอแถบความคืบหน้าจนจบ ผลสรุปจะขึ้นใน Overview และแถบสถานะด้านล่าง

โปรแกรมสแกนโฟลเดอร์ย่อยทุกชั้น และจับคู่ไฟล์จากชื่อไฟล์ ระหว่างสองโฟลเดอร์

อ่านผล

รายการไฟล์ (ซ้าย)

สัญลักษณ์    ความหมาย
✓    entry ของสองฝั่งเหมือนกันทั้งหมด
●    มี entry ที่ต่างกัน (ตัวเลขด้านขวาคือจำนวนที่ต่าง)
⚠    ไฟล์นี้มีอยู่แค่ฝั่งเดียว
พิมพ์ในช่องค้นหาเพื่อกรองชื่อไฟล์
ติ๊ก Differences only เพื่อซ่อนไฟล์ที่เหมือนกัน

ตารางผลลัพธ์ (ขวา)

เลือกไฟล์ทางซ้าย ตารางจะแสดง entry ที่ไม่ซ้ำกันของไฟล์นั้น
สถานะ: Shared (เขียว) มีทั้งสองฝั่ง, TH only (แดง) มีเฉพาะ TH, VNT only (ฟ้า) มีเฉพาะ VNT
ปุ่มกรอง All entries / Both / TH Only / VNT Only มีตัวเลขกำกับ
ช่องค้นหามุมขวาใช้กรอง entry เช่น พิมพ์ชื่อฮีโร่เพื่อดูเฉพาะเสียงของฮีโร่นั้น

ป้ายสถานะการถอดรหัส (ใต้ชื่อไฟล์)

ZSTD ✓: พบและถอดรหัสสำเร็จ
Raw: ไม่มี ZSTD frame ใช้ไบต์ดิบ
Decode failed: พบ ZSTD frame แต่ถอดไม่สำเร็จ (อาจเข้ารหัส AES หรือใช้ dictionary/เวอร์ชันอื่น) โปรแกรมจะใช้ไบต์ดิบแทน ผลเปรียบเทียบของไฟล์นี้จึงอาจไม่ครบ
File missing: ไฟล์นี้ไม่มีในฝั่งนั้น
คัดลอกและส่งออก
ดับเบิลคลิกแถวเพื่อคัดลอก entry ถ้าเลือกหลายแถว (Ctrl/Shift+คลิก) แล้วกด Ctrl+C จะคัดลอกทุกแถวที่เลือก แถวละบรรทัด
คลิกขวา: Copy entry หรือ Copy all visible (คัดลอกทุกแถวที่กรองอยู่)
Export report ↓ (Ctrl+E) เลือกชนิดไฟล์ตอนบันทึก
.csv: ทุกไฟล์ทุก entry พร้อมสถานะ
.json: ข้อมูลครบรวมสรุปรายไฟล์
.txt: สรุปรายไฟล์ และรายการที่ต่างกันเท่านั้น
ปุ่มลัด
ปุ่ม    ทำอะไร
F5 / Enter (ในช่องพาธ)    เริ่มเปรียบเทียบ
Ctrl+F    ไปที่ช่องค้นหา entry
Ctrl+E    ส่งออกรายงาน
Ctrl+C    คัดลอกแถวที่เลือก
3. ข้อควรรู้
โปรแกรมไม่แก้ไขหรือเขียนทับไฟล์ต้นฉบับ ถอดรหัสในหน่วยความจำเท่านั้น
ถ้าไม่ได้ติดตั้ง pyzstd จะมีข้อความแจ้งและเปรียบเทียบไม่ได้ ให้รัน pip install pyzstd

# AoV SoundCheckTool 2.0

## Update Details

### 1. Improvements

#### UI Layout

The previous top-to-bottom layout has been redesigned into two main sections.

**Left Sidebar (Settings & Overview)**

- **SOURCES:** Displays two folder cards: TH (red) and VNT (blue). Each card includes a path input field, a Browse button, and a status indicator (✓ found / ✗ not found).
- **Compare folders:** A comparison button with a progress bar that appears only while the comparison is running.
- **OVERVIEW:** Displays the total number of files, the number of files with differences, a Shared / TH only / VNT only distribution bar, and corresponding counts and percentages.
- **FILES:** Displays the file list with a search field and a "Differences only" option.

**Right Panel (Results)**

- Displays the selected filename, TH/VNT decoding status badges, and an Export button.
- Shows the distribution bar for the selected file.
- Provides filter buttons with entry counts and a search field.
- Displays the results table and a summary line showing the number of entries currently displayed.

#### Visual Design

- New color theme: dark navy background, purple as the primary color, and a purple-to-blue gradient accent line across the top.
- Status colors:
  - Shared: Green
  - TH only: Red
  - VNT only: Blue
- The results table uses the Consolas font with alternating row colors, making entries such as Hero_... and Play_... easier to read.
- Slim scrollbars without arrow buttons.
- Dark title bar on Windows 10/11.
- High-DPI display support for sharper text.
- Window height is constrained to fit within the screen, ensuring the bottom status bar remains visible.

#### Functionality & Usability

- Folder comparison runs in the background, preventing the window from freezing when processing large folders. The tool also displays which file is currently being processed.
- Folder paths are validated immediately when typed or selected.
- After clicking Browse, the path field automatically scrolls to display the end of the path.
- Entries can be copied by double-clicking, pressing Ctrl+C, or using the right-click context menu.
- Search uses a short delay (debounce) to prevent lag when typing quickly.
- If the results exceed 20,000 rows, only the first portion is displayed, along with a notification.

#### Unchanged Components

The following remain exactly the same:

- Comparison logic.
- ZSTD decoding logic, including the dictionary, which remains byte-for-byte identical to the original.
- Export file formats: CSV / JSON / TXT.

### 2. How to Use

#### Installation & Launch

1. Install Python 3.10 or later. Make sure to check **"Add Python to PATH"** during installation.
2. Extract the ZIP archive.
3. Double-click `Run_SoundCheck.bat`. The script will automatically install `pyzstd` and launch the application.

**Building a Windows EXE**

To create a standalone `.exe` file, run `Build_Windows_EXE.bat` (an internet connection is required).

The resulting file will be available at:

`dist\AoV_SoundCheckTool.exe`

#### Comparison Procedure

1. On the **Thailand** card, click Browse and select the folder containing the TH `.bytes` files. Alternatively, you can paste the folder path directly into the input field.
2. Repeat the same process for the **Vietnam** card.
3. Once both paths display ✓ found, click **Compare folders** (or press F5 / Enter while focused on either path field).
4. Wait for the progress bar to finish. The comparison summary will appear in the Overview section and the bottom status bar.

The program scans all subdirectories recursively and matches files between the two folders based on their filenames.

#### Understanding the Results

**File List (Left Panel)**

| Symbol | Meaning |
|---|---|
| ✓ | All entries in both versions are identical. |
| ● | One or more entries are different. The number on the right indicates how many entries differ. |
| ⚠ | The file exists in only one version. |

- Type in the search field to filter filenames.
- Enable **Differences only** to hide files with no differences.

**Results Table (Right Panel)**

- Select a file from the left panel to display its unique entries in the results table.
- Status indicators:
  - **Shared (Green):** The entry exists in both versions.
  - **TH only (Red):** The entry exists only in TH.
  - **VNT only (Blue):** The entry exists only in VNT.
- Filter buttons: **All entries / Both / TH Only / VNT Only**, each displaying the corresponding entry count.
- Use the search field in the upper-right corner to filter entries. For example, enter a hero's name to display only that hero's sound entries.

**Decoding Status Badges (Below the Filename)**

- **ZSTD ✓:** A ZSTD frame was detected and successfully decoded.
- **Raw:** No ZSTD frame was found. The original raw bytes are used.
- **Decode failed:** A ZSTD frame was detected, but decoding failed. This may occur if the data is AES-encrypted or uses a different dictionary/version. The program will fall back to using the raw bytes, so the comparison results for this file may be incomplete.
- **File missing:** The file does not exist on that side.

#### Copying & Exporting

- **Double-click a row** to copy its entry.
- To copy multiple rows, select them using Ctrl+Click or Shift+Click, then press **Ctrl+C**. All selected entries will be copied, one per line.
- **Right-click menu:**
  - Copy entry
  - Copy all visible (copies all currently filtered rows).

**Export report ↓ (Ctrl+E)**

Choose the desired file format when saving the report:

- **.csv:** Includes all files, all entries, and their corresponding statuses.
- **.json:** Contains complete data, including per-file summaries.
- **.txt:** Contains per-file summaries and only the entries with differences.

#### Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| F5 / Enter (in path field) | Start folder comparison |
| Ctrl+F | Focus the entry search field |
| Ctrl+E | Export report |
| Ctrl+C | Copy selected rows |

### 3. Important Notes

- The program does not modify or overwrite any original files. All decoding is performed in memory only.
- If `pyzstd` is not installed, the program will display a notification and comparison will not be available.

  To install it manually, run:

  `pip install pyzstd`

  <img width="1918" height="932" alt="image" src="https://github.com/user-attachments/assets/3efb8245-962c-415a-84c5-605d0c3e8521" />
