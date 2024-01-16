---
title: รูปแบบ 1Bpp จัดทำดัชนี
linktitle: รูปแบบ 1Bpp จัดทำดัชนี
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีจัดรูปแบบรูปภาพใน 1 bpp ที่จัดทำดัชนีด้วย Aspose.Words สำหรับ .NET บทช่วยสอนที่สมบูรณ์สำหรับรูปภาพที่มีความลึกของสีต่ำ
type: docs
weight: 10
url: /th/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
ในบทช่วยสอนนี้ เราจะสำรวจซอร์สโค้ด C# ที่ให้มาสำหรับฟังก์ชัน "Format 1Bpp Indexed" ด้วย Aspose.Words สำหรับ .NET คุณสมบัตินี้ช่วยให้คุณสามารถจัดรูปแบบรูปภาพในเอกสารในรูปแบบ PNG โดยมีความลึกของสี 1 บิตต่อพิกเซล (1 bpp) และโหมดสีที่จัดทำดัชนีไว้

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 ในขั้นตอนนี้ เราจะกำหนดค่าตัวเลือกการสำรองข้อมูลสำหรับรูปภาพ เราสร้างใหม่`ImageSaveOptions`วัตถุที่ระบุรูปแบบการบันทึกที่ต้องการ ที่นี่ "Png" สำหรับรูปแบบ PNG นอกจากนี้เรายังกำหนดหน้าที่จะรวมไว้ในรูปภาพ โหมดขาวดำ และรูปแบบพิกเซล 1 bpp ที่จัดทำดัชนีไว้

## ขั้นตอนที่ 4: การสำรองรูปภาพ

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 ในขั้นตอนสุดท้ายนี้ เราจะบันทึกรูปภาพเอกสารในรูปแบบ PNG โดยใช้นามสกุลไฟล์`Save` วิธีการและส่งเส้นทางไปยังไฟล์เอาต์พุตพร้อมกับตัวเลือกการบันทึกที่ระบุ

ตอนนี้คุณสามารถรันซอร์สโค้ดเพื่อจัดรูปแบบภาพเอกสารในรูปแบบ PNG โดยมีความลึกของสีอยู่ที่ 1 bpp ที่จัดทำดัชนีไว้ ไฟล์ผลลัพธ์จะถูกบันทึกในไดเร็กทอรีที่ระบุโดยใช้ชื่อ "WorkingWithImageSaveOptions.Format1BppIndexed.Png"

### ตัวอย่างซอร์สโค้ดสำหรับรูปแบบ 1Bpp ที่จัดทำดัชนีโดยใช้ Aspose.Words สำหรับ .NET

```csharp 
 
			 // เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจฟีเจอร์รูปแบบดัชนี 1Bpp ด้วย Aspose.Words สำหรับ .NET เราเรียนรู้วิธีจัดรูปแบบรูปภาพในเอกสารในรูปแบบ PNG ด้วยความลึกของสี 1 บิตต่อพิกเซล (1 bpp) และโหมดสีที่จัดทำดัชนีไว้

คุณสมบัตินี้มีประโยชน์เมื่อคุณต้องการรับภาพที่มีความลึกของสีต่ำและขนาดไฟล์เล็ก รูปแบบการจัดทำดัชนี 1Bpp ช่วยให้สามารถแสดงภาพโดยใช้ชุดสีที่มีการจัดทำดัชนี ซึ่งอาจเป็นประโยชน์สำหรับการใช้งานเฉพาะบางอย่าง

Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติขั้นสูงที่หลากหลายสำหรับการจัดการและสร้างเอกสาร รูปแบบการจัดทำดัชนี 1Bpp เป็นหนึ่งในเครื่องมืออันทรงพลังมากมายที่คุณสามารถใช้ได้