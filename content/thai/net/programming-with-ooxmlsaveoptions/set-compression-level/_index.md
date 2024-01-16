---
title: ตั้งค่าระดับการบีบอัด
linktitle: ตั้งค่าระดับการบีบอัด
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตั้งค่าระดับการบีบอัดเมื่อบันทึกเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
ในบทช่วยสอนนี้ เราจะสำรวจซอร์สโค้ด C# ที่ให้มาเพื่อตั้งค่าระดับการบีบอัดเมื่อบันทึกเอกสารโดยใช้ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณควบคุมระดับการบีบอัดของเอกสารที่สร้างขึ้นได้

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มข้อมูลอ้างอิงที่จำเป็นและนำเข้าเนมสเปซที่เหมาะสมแล้ว

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 ในขั้นตอนนี้ เราโหลดเอกสารโดยใช้`Document` วิธีการและส่งเส้นทางไปยังไฟล์ DOCX ที่จะโหลด

## ขั้นตอนที่ 3: การกำหนดค่าตัวเลือกการสำรองข้อมูล OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 ในขั้นตอนนี้ เรากำหนดค่าตัวเลือกการบันทึก OOXML โดยใช้`OoxmlSaveOptions` ระดับ. เราตั้งค่าระดับการบีบอัดเป็น`SuperFast` เพื่อให้ได้การบีบอัดที่รวดเร็วยิ่งขึ้น

## ขั้นตอนที่ 4: บันทึกเอกสารด้วยระดับการบีบอัดที่ระบุ

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 ในขั้นตอนสุดท้ายนี้ เราจะบันทึกเอกสารโดยใช้`Save` วิธีการและส่งเส้นทางไปยังไฟล์เอาต์พุตด้วย`.docx` ส่วนขยายพร้อมกับตัวเลือกการบันทึกที่ระบุ

ตอนนี้คุณสามารถรันซอร์สโค้ดเพื่อตั้งค่าระดับการบีบอัดเมื่อบันทึกเอกสาร ไฟล์ผลลัพธ์จะถูกบันทึกในไดเร็กทอรีที่ระบุโดยใช้ชื่อ "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx"

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าระดับการบีบอัดโดยใช้ Aspose.Words สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจฟังก์ชันการทำงานของการตั้งค่าระดับการบีบอัดเมื่อบันทึกเอกสารโดยใช้ Aspose.Words สำหรับ .NET ด้วยการระบุระดับการบีบอัดที่เหมาะสม คุณสามารถปรับขนาดเอกสารและความเร็วการสร้างให้เหมาะสมได้

 ที่`OoxmlSaveOptions` คลาสให้ความยืดหยุ่นในการควบคุมระดับการบีบอัดโดยการตั้งค่า`CompressionLevel` ทรัพย์สินให้มีมูลค่าที่เหมาะสม เช่น`SuperFast`. สิ่งนี้ช่วยให้คุณสร้างสมดุลที่เหมาะสมระหว่างขนาดไฟล์และความเร็วการสำรองข้อมูลตามความต้องการเฉพาะของคุณ

การใช้การบีบอัดจะเป็นประโยชน์เมื่อคุณต้องการลดขนาดของไฟล์ที่สร้างขึ้น โดยเฉพาะอย่างยิ่งสำหรับเอกสารขนาดใหญ่ ซึ่งช่วยให้จัดเก็บ แบ่งปัน และส่งเอกสารได้ง่ายขึ้น

Aspose.Words สำหรับ .NET นำเสนอตัวเลือกและฟีเจอร์ที่มีประสิทธิภาพมากมายสำหรับการจัดการเอกสาร ด้วยการใช้ตัวเลือกการสำรองข้อมูลที่เหมาะสม คุณสามารถปรับแต่งกระบวนการสร้างเอกสารและเพิ่มประสิทธิภาพการทำงานของแอปพลิเคชันของคุณได้

สำรวจคุณสมบัติเพิ่มเติมของ Aspose.Words สำหรับ .NET ได้อย่างอิสระ เพื่อปรับปรุงเวิร์กโฟลว์การสร้างเอกสารของคุณ