---
title: เก็บอักขระควบคุมแบบเดิมไว้
linktitle: เก็บอักขระควบคุมแบบเดิมไว้
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรักษาอักขระควบคุมแบบเดิมเมื่อบันทึกเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

ในบทช่วยสอนนี้ เราจะสำรวจซอร์สโค้ด C# ที่ให้ไว้เพื่อรักษาอักขระควบคุมแบบเดิมเมื่อบันทึกเอกสารโดยใช้ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถรักษาอักขระควบคุมพิเศษไว้ได้เมื่อแปลงหรือบันทึกเอกสาร

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มข้อมูลอ้างอิงที่จำเป็นและนำเข้าเนมสเปซที่เหมาะสมแล้ว

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 ในขั้นตอนนี้ เราโหลดเอกสารโดยใช้`Document` วิธีการและส่งเส้นทางไปยังไฟล์ที่มีอักขระควบคุมที่สืบทอดมา

## ขั้นตอนที่ 3: การกำหนดค่าตัวเลือกการสำรองข้อมูล OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 ในขั้นตอนนี้ เรากำหนดค่าตัวเลือกการบันทึก OOXML โดยการสร้างตัวเลือกใหม่`OoxmlSaveOptions` วัตถุ. เราระบุรูปแบบการบันทึกที่ต้องการ (ที่นี่`FlatOpc` ) และเปิดใช้งาน`KeepLegacyControlChars` ตัวเลือกในการเก็บอักขระควบคุมแบบเดิม

## ขั้นตอนที่ 4: บันทึกเอกสารด้วยอักขระควบคุมแบบเดิม

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 ในขั้นตอนสุดท้ายนี้ เราจะบันทึกเอกสารโดยใช้`Save` วิธีการและส่งเส้นทางไปยังไฟล์เอาต์พุตด้วย`.docx` ส่วนขยายพร้อมกับตัวเลือกการบันทึกที่ระบุ

ตอนนี้คุณสามารถเรียกใช้ซอร์สโค้ดเพื่อรักษาอักขระควบคุมแบบเดิมเมื่อบันทึกเอกสาร ไฟล์ผลลัพธ์จะถูกบันทึกในไดเร็กทอรีที่ระบุโดยใช้ชื่อ "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx"

### ตัวอย่างซอร์สโค้ดสำหรับ Keep Legacy Control Chars โดยใช้ Aspose.Words สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจฟังก์ชันการทำงานของการรักษาอักขระควบคุมแบบเดิมเมื่อบันทึกเอกสารโดยใช้ Aspose.Words สำหรับ .NET เราได้เรียนรู้วิธีการรักษาอักขระพิเศษที่อาจมีความสำคัญสำหรับการจัดรูปแบบหรือการแสดงเอกสารที่เหมาะสม

 การรักษาอักขระควบคุมแบบเดิมมีประโยชน์อย่างยิ่งเมื่อประมวลผลคำกับเอกสารที่ใช้ฟีเจอร์เก่าหรือเฉพาะ เช่น อักขระควบคุมพิเศษ โดยเปิดใช้งาน`KeepLegacyControlChars` ตัวเลือกเมื่อบันทึกเอกสาร คุณต้องแน่ใจว่าอักขระเหล่านี้ยังคงอยู่

Aspose.Words สำหรับ .NET นำเสนอตัวเลือกการสำรองข้อมูลที่ยืดหยุ่นและมีประสิทธิภาพมากมาย เพื่อตอบสนองความต้องการในการจัดการเอกสารของคุณ ด้วยการใช้ตัวเลือกที่เหมาะสม คุณสามารถปรับแต่งกระบวนการสำรองข้อมูลเพื่อรักษาลักษณะเฉพาะของเอกสารของคุณได้

อย่าลังเลที่จะรวมฟังก์ชันนี้เข้ากับโปรเจ็กต์ Aspose.Words สำหรับ .NET ของคุณ เพื่อให้มั่นใจถึงความสมบูรณ์และการรักษาอักขระควบคุมแบบเดิมในเอกสารของคุณ