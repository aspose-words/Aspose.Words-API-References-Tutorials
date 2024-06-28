---
title: เปิดเผยการควบคุมเกณฑ์สำหรับ Tiff Binarization
linktitle: เปิดเผยการควบคุมเกณฑ์สำหรับ Tiff Binarization
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีควบคุมเกณฑ์การแบ่งไบนารี TIFF ด้วย Aspose.Words สำหรับ .NET บทช่วยสอนที่สมบูรณ์เพื่อภาพที่มีคุณภาพดีขึ้น
type: docs
weight: 10
url: /th/net/programming-with-imagesaveoptions/expose-threshold-control-for-tiff-binarization/
---
ในบทช่วยสอนนี้ เราจะสำรวจซอร์สโค้ด C# ที่ให้มาสำหรับฟีเจอร์ “TIFF Binarization Threshold Control Exposure” ด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณควบคุมเกณฑ์การแบ่งไบนารีเมื่อแปลงเอกสารเป็นรูปแบบ TIFF

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
TiffCompression = TiffCompression.Ccitt3,
ImageColorMode = ImageColorMode.Grayscale,
TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
ThresholdForFloydSteinbergDithering = 254
};
```

 ในขั้นตอนนี้ เราจะกำหนดค่าตัวเลือกการสำรองข้อมูลสำหรับรูปภาพ เราสร้างใหม่`ImageSaveOptions` วัตถุที่ระบุรูปแบบการบันทึกที่ต้องการ ที่นี่ "Tiff" สำหรับรูปแบบ TIFF นอกจากนี้เรายังตั้งค่าตัวเลือกการบีบอัด โหมดสีของภาพ และวิธีการแปลงไบนาไรเซชัน TIFF ด้วยเกณฑ์กำหนดไบนาไรเซชันที่ระบุ

## ขั้นตอนที่ 4: การสำรองรูปภาพ

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
```

 ในขั้นตอนสุดท้ายนี้ เราจะบันทึกรูปภาพเอกสารในรูปแบบ TIFF โดยใช้นามสกุลไฟล์`Save` วิธีการและส่งเส้นทางไปยังไฟล์เอาต์พุตพร้อมกับตัวเลือกการบันทึกที่ระบุ

ตอนนี้คุณสามารถเรียกใช้ซอร์สโค้ดเพื่อแปลงเอกสารของคุณเป็นรูปแบบ TIFF ในขณะที่ควบคุมเกณฑ์การแบ่งไบนารีด้วยตัวเลือกที่ระบุ ไฟล์ผลลัพธ์จะถูกบันทึกในไดเร็กทอรีที่ระบุโดยใช้ชื่อ "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff"

### ซอร์สโค้ดตัวอย่างการเปิดเผยการควบคุมเกณฑ์สำหรับ Tiff Binarization

```csharp 

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	TiffCompression = TiffCompression.Ccitt3,
	ImageColorMode = ImageColorMode.Grayscale,
	TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
	ThresholdForFloydSteinbergDithering = 254
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
            
        
```

### บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจฟีเจอร์การรับแสงของ TIFF Binarization Threshold Control ด้วย Aspose.Words สำหรับ .NET เราเรียนรู้วิธีควบคุมเกณฑ์การแบ่งไบนารีเมื่อแปลงเอกสารเป็นรูปแบบ TIFF

คุณสมบัตินี้มีประโยชน์เมื่อคุณต้องการปรับเกณฑ์ไบนาไรเซชันเพื่อให้ได้ภาพ TIFF ที่มีคุณภาพและความคมชัดดีขึ้น ด้วยการระบุเกณฑ์การแบ่งไบนารีพร้อมตัวเลือกการบันทึก คุณจะได้รับผลลัพธ์แบบกำหนดเองที่ปรับให้เหมาะกับความต้องการของคุณ

Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติขั้นสูงที่หลากหลายสำหรับการจัดการและสร้างเอกสาร การเปิดเผย TIFF Binarization Threshold Control เป็นหนึ่งในเครื่องมืออันทรงพลังมากมายที่คุณสามารถใช้ได้

อย่าลังเลที่จะรวมคุณสมบัตินี้เข้ากับโปรเจ็กต์ Aspose.Words สำหรับ .NET ของคุณเพื่อให้ได้ภาพ TIFF คุณภาพสูงพร้อมการควบคุมเกณฑ์ไบนาไรเซชันที่แม่นยำ