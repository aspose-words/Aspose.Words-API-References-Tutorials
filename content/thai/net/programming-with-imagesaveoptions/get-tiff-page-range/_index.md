---
title: รับช่วงหน้า Tiff
linktitle: รับช่วงหน้า Tiff
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแยกหน้า TIFF ต่างๆ ด้วย Aspose.Words สำหรับ .NET บทช่วยสอนที่สมบูรณ์สำหรับไฟล์ TIFF แบบกำหนดเอง
type: docs
weight: 10
url: /th/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

ในบทช่วยสอนนี้ เราจะสำรวจซอร์สโค้ด C# ที่ให้มาเพื่อรับหน้า TIFF ที่หลากหลายด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถแยกช่วงหน้าจากเอกสารและบันทึกเป็นไฟล์ TIFF ได้

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มข้อมูลอ้างอิงที่จำเป็นและนำเข้าเนมสเปซที่เหมาะสมแล้ว

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 ในขั้นตอนนี้ เราโหลดเอกสารโดยใช้`Document` วิธีการและส่งเส้นทางไปยังไฟล์ DOCX ที่จะโหลด

## ขั้นตอนที่ 3: บันทึกเอกสารฉบับสมบูรณ์ใน TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

ในขั้นตอนนี้ เราจะบันทึกเอกสารทั้งหมดในรูปแบบ TIFF โดยใช้นามสกุลไฟล์`Save` และระบุเส้นทางไปยังไฟล์เอาต์พุตที่มีนามสกุล`.tiff`.

## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกการสำรองข้อมูลสำหรับช่วงหน้า

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 ในขั้นตอนนี้ เราจะกำหนดค่าตัวเลือกการสำรองข้อมูลสำหรับช่วงหน้าที่ระบุ เราสร้างใหม่`ImageSaveOptions` วัตถุที่ระบุรูปแบบการบันทึกที่ต้องการ ที่นี่ "Tiff" สำหรับรูปแบบ TIFF เราใช้`PageSet` เพื่อระบุช่วงหน้าที่เราต้องการแยกจากหน้า 0 ถึงหน้าที่ 1 (รวม) เรายังตั้งค่าการบีบอัด TIFF เป็น`Ccitt4` และความละเอียดถึง 160 dpi

## ขั้นตอนที่ 5: บันทึกช่วงหน้าเป็น TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 ในขั้นตอนสุดท้ายนี้ เราจะบันทึกช่วงหน้าที่ระบุในรูปแบบ TIFF โดยใช้`Save` วิธีการและส่งผ่านเส้นทางไปยังไฟล์เอาต์พุตด้วย`.tiff` ส่วนขยายพร้อมกับตัวเลือกการบันทึกที่ระบุ

ตอนนี้คุณสามารถเรียกใช้ซอร์สโค้ดเพื่อรับช่วงหน้าที่ต้องการจากเอกสารของคุณและบันทึกเป็นไฟล์ TIFF ไฟล์ผลลัพธ์จะถูกบันทึกในไดเร็กทอรีที่ระบุโดยใช้ชื่อ "WorkingWithImageSaveOptions.MultipageTiff.tiff" สำหรับเอกสารฉบับเต็มและ "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" สำหรับช่วงเพจที่ระบุ

### ตัวอย่างซอร์สโค้ดของ Get Tiff Page Range โดยใช้ Aspose.Words สำหรับ .NET

```csharp 

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจฟังก์ชันการทำงานของการรับหน้า TIFF หลายหน้าด้วย Aspose.Words สำหรับ .NET เราได้เรียนรู้วิธีแยกหน้าต่างๆ จากเอกสารและบันทึกเป็นไฟล์ TIFF

คุณสมบัตินี้มีประโยชน์เมื่อคุณต้องการดึงเฉพาะบางหน้าจากเอกสารและบันทึกในรูปแบบรูปภาพมาตรฐาน เช่น TIFF คุณยังสามารถปรับแต่งตัวเลือกการบีบอัดและความละเอียดเพื่อให้ได้ไฟล์ TIFF คุณภาพดีที่สุด

Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติขั้นสูงที่หลากหลายสำหรับการจัดการและสร้างเอกสาร การรับช่วงหน้า TIFF เป็นหนึ่งในเครื่องมือที่มีประสิทธิภาพมากมายที่คุณมี

คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับโปรเจ็กต์ Aspose.Words สำหรับ .NET ของคุณได้อย่างอิสระ เพื่อแยกและบันทึกหน้าต่างๆ จากเอกสารของคุณในรูปแบบ TIFF