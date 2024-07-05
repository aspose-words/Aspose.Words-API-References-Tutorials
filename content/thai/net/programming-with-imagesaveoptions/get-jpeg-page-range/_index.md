---
title: รับช่วงหน้า JPEG
linktitle: รับช่วงหน้า JPEG
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรับหน้า JPEG ที่หลากหลายด้วย Aspose.Words สำหรับ .NET บทช่วยสอนที่สมบูรณ์สำหรับการแยกรูปภาพที่กำหนดเอง
type: docs
weight: 10
url: /th/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

ในบทช่วยสอนนี้ เราจะสำรวจซอร์สโค้ด C# ที่ให้มาสำหรับฟีเจอร์ "รับช่วงของเพจ JPEG" ด้วย Aspose.Words สำหรับ .NET คุณสมบัตินี้ช่วยให้คุณสามารถแปลงช่วงหน้าของเอกสารเป็นรูปภาพในรูปแบบ JPEG ได้

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มข้อมูลอ้างอิงที่จำเป็นและนำเข้าเนมสเปซที่เหมาะสมแล้ว

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 ในขั้นตอนนี้ เราโหลดเอกสารโดยใช้`Document` วิธีการและส่งเส้นทางไปยังไฟล์ DOCX ที่จะโหลด

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการสำรองข้อมูลรูปภาพ

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 ในขั้นตอนนี้ เราจะกำหนดค่าตัวเลือกการสำรองข้อมูลสำหรับรูปภาพ เราสร้างใหม่`ImageSaveOptions` วัตถุที่ระบุรูปแบบการบันทึกที่ต้องการ ที่นี่ "Jpeg" สำหรับรูปแบบ JPEG นอกจากนี้เรายังกำหนดช่วงของหน้าที่จะแปลงโดยใช้`PageSet`วัตถุ. สุดท้ายเราปรับความสว่างและคอนทราสต์ของภาพโดยใช้`ImageBrightness` และ`ImageContrast` คุณสมบัติตามลำดับ นอกจากนี้เรายังเปลี่ยนความละเอียดแนวนอนโดยใช้`HorizontalResolution` คุณสมบัติ.

## ขั้นตอนที่ 4: การสำรองรูปภาพ

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 ในขั้นตอนสุดท้ายนี้ เราจะบันทึกรูปภาพในช่วงหน้าที่ระบุในรูปแบบ JPEG โดยใช้`Save` วิธีการและส่งเส้นทางไปยังไฟล์เอาต์พุตพร้อมกับตัวเลือกการบันทึกที่ระบุ

ตอนนี้คุณสามารถเรียกใช้ซอร์สโค้ดเพื่อแปลงช่วงหน้าในเอกสารของคุณให้เป็นภาพ JPEG ได้แล้ว ไฟล์ผลลัพธ์จะถูกบันทึกในไดเร็กทอรีที่ระบุโดยใช้ชื่อ "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg"

### ตัวอย่างซอร์สโค้ดสำหรับรับช่วงหน้า Jpeg โดยใช้ Aspose.Words For .NET

```csharp 
 // เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// ตั้งค่า "PageSet" เป็น "0" เพื่อแปลงเฉพาะหน้าแรกของเอกสาร
options.PageSet = new PageSet(0);

// เปลี่ยนความสว่างและความคมชัดของภาพ
// ทั้งคู่อยู่ในระดับ 0-1 และอยู่ที่ 0.5 ตามค่าเริ่มต้น
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// เปลี่ยนความละเอียดแนวนอน
// ค่าเริ่มต้นสำหรับคุณสมบัติเหล่านี้คือ 96.0 สำหรับความละเอียด 96dpi
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจฟังก์ชันการรับช่วงเพจ JPEG ด้วย Aspose.Words สำหรับ .NET เราได้เรียนรู้วิธีแปลงช่วงหน้าของเอกสารให้เป็นรูปภาพในรูปแบบ JPEG พร้อมทั้งปรับแต่งตัวเลือกการบันทึก

คุณสมบัตินี้มีประโยชน์เมื่อคุณต้องการแยกหน้าเฉพาะจากเอกสารและบันทึกเป็นภาพ JPEG คุณยังสามารถปรับความสว่าง คอนทราสต์ และความละเอียดแนวนอนของรูปภาพเพื่อให้ได้ผลลัพธ์ในแบบของคุณ

Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติขั้นสูงที่หลากหลายสำหรับการจัดการและสร้างเอกสาร การรับช่วงหน้า JPEG เป็นหนึ่งในเครื่องมืออันทรงพลังมากมายที่คุณสามารถใช้ได้

อย่าลังเลที่จะรวมคุณสมบัตินี้เข้ากับโครงการ Aspose.Words สำหรับ .NET ของคุณเพื่อรับภาพ JPEG คุณภาพสูงจากเอกสารของคุณ