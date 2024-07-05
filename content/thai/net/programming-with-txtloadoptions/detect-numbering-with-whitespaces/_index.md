---
title: ตรวจจับการกำหนดหมายเลขด้วยช่องว่าง
linktitle: ตรวจจับการกำหนดหมายเลขด้วยช่องว่าง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตรวจสอบหมายเลขรายการที่มีช่องว่างใน Aspose.Words for .NET ปรับปรุงโครงสร้างเอกสารของคุณได้อย่างง่ายดาย
type: docs
weight: 10
url: /th/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
ในบทช่วยสอนนี้ เราจะสำรวจซอร์สโค้ด C# ที่ให้มาสำหรับฟีเจอร์ "การตรวจจับการกำหนดหมายเลขด้วยช่องว่าง" ด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถตรวจจับและสร้างรายการจากเอกสารข้อความที่มีหมายเลขรายการตามด้วยช่องว่าง

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มข้อมูลอ้างอิงที่จำเป็นและนำเข้าเนมสเปซที่เหมาะสมแล้ว

## ขั้นตอนที่ 2: การสร้างเอกสารข้อความ

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

ในขั้นตอนนี้ เราสร้างสตริงข้อความที่จำลองเอกสารข้อความที่มีหมายเลขรายการตามด้วยช่องว่าง เราใช้ตัวคั่นรายการที่แตกต่างกัน เช่น จุด วงเล็บขวา สัญลักษณ์หัวข้อย่อย และช่องว่าง

## ขั้นตอนที่ 3: การกำหนดค่าตัวเลือกการอัปโหลด

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 ในขั้นตอนนี้ เรากำหนดค่าตัวเลือกการโหลดเอกสาร เราสร้างใหม่`TxtLoadOptions` วัตถุและตั้งค่า`DetectNumberingWithWhitespaces`ทรัพย์สินเพื่อ`true`- ซึ่งจะทำให้ Aspose.Words ตรวจจับหมายเลขรายการได้แม้ว่าจะมีช่องว่างตามหลังก็ตาม

## ขั้นตอนที่ 4: กำลังโหลดเอกสารและบันทึก

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 ในขั้นตอนนี้ เราโหลดเอกสารโดยใช้สตริงข้อความที่ระบุและตัวเลือกการโหลด เราใช้ก`MemoryStream` เพื่อแปลงสตริงข้อความเป็นสตรีมหน่วยความจำ จากนั้นเราจะบันทึกเอกสารผลลัพธ์ในรูปแบบ .docx

### ตัวอย่างซอร์สโค้ดสำหรับคุณสมบัติ White Space Numbering Detection ด้วย Aspose.Words สำหรับ .NET

```csharp

            
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// สร้างเอกสารข้อความธรรมดาในรูปแบบของสตริงที่มีส่วนต่างๆ ที่อาจตีความได้ว่าเป็นรายการ
// เมื่อโหลดแล้ว Aspose.Words จะตรวจพบสามรายการแรกเสมอ
// และรายการวัตถุจะถูกสร้างขึ้นสำหรับพวกเขาหลังจากโหลด
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// รายการที่สี่ โดยมีช่องว่างอยู่ระหว่างหมายเลขรายการและเนื้อหารายการ
// จะถูกตรวจพบเป็นรายการหากตั้งค่า "DetectNumberingWithWhitespaces" ในวัตถุ LoadOptions เป็นจริงเท่านั้น
// เพื่อหลีกเลี่ยงย่อหน้าที่ขึ้นต้นด้วยตัวเลขที่ถูกตรวจพบว่าเป็นรายการโดยไม่ตั้งใจ
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// โหลดเอกสารในขณะที่ใช้ LoadOptions เป็นพารามิเตอร์และตรวจสอบผลลัพธ์
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

ตอนนี้คุณสามารถรันซอร์สโค้ดเพื่อโหลดเอกสารข้อความที่มีหมายเลขรายการพร้อมช่องว่าง จากนั้นสร้างเอกสาร .docx พร้อมรายการที่ตรวจพบ ไฟล์เอาต์พุตจะถูกบันทึกในไดเร็กทอรีที่ระบุโดยใช้ชื่อ "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx"

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจคุณลักษณะการตรวจจับการกำหนดหมายเลขช่องว่างใน Aspose.Words สำหรับ .NET เราเรียนรู้วิธีสร้างรายการจากเอกสารข้อความที่มีหมายเลขรายการตามด้วยช่องว่าง

คุณสมบัตินี้มีประโยชน์อย่างมากสำหรับการประมวลผลเอกสารที่มีหมายเลขรายการที่จัดรูปแบบในรูปแบบต่างๆ ด้วยการใช้ตัวเลือกการโหลดที่เหมาะสม Aspose.Words สามารถตรวจจับหมายเลขรายการเหล่านี้ได้ แม้ว่าจะตามด้วยช่องว่างก็ตาม และแปลงเป็นรายการที่มีโครงสร้างในเอกสารขั้นสุดท้าย

การใช้คุณสมบัตินี้สามารถช่วยคุณประหยัดเวลาและปรับปรุงประสิทธิภาพเวิร์กโฟลว์ของคุณได้ คุณสามารถดึงข้อมูลจากเอกสารข้อความและแปลงเป็นเอกสารที่มีโครงสร้างอย่างดีพร้อมรายการที่เหมาะสมได้อย่างง่ายดาย

อย่าลืมพิจารณาโหลดตัวเลือกต่างๆ เช่น การกำหนดค่าการตรวจจับการโทรด้วยช่องว่าง เพื่อให้ได้ผลลัพธ์ที่ต้องการ

Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติขั้นสูงมากมายสำหรับการจัดการและสร้างเอกสาร ด้วยการสำรวจเอกสารและตัวอย่างเพิ่มเติมที่ Aspose.Words มอบให้ คุณจะสามารถใช้ประโยชน์จากความสามารถของไลบรารีอันทรงพลังนี้ได้อย่างเต็มที่

ดังนั้น อย่าลังเลที่จะผสานรวมการตรวจจับการกำหนดหมายเลขช่องว่างเข้ากับโปรเจ็กต์ Aspose.Words สำหรับ .NET และใช้ประโยชน์จากข้อดีของมันเพื่อสร้างเอกสารที่มีโครงสร้างที่ดีและอ่านง่าย


