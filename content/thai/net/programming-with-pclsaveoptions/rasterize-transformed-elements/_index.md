---
title: แรสเตอร์องค์ประกอบที่แปลงแล้ว
linktitle: แรสเตอร์องค์ประกอบที่แปลงแล้ว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีปิดใช้งานการแรสเตอร์ขององค์ประกอบที่แปลงแล้วเมื่อแปลงเป็นรูปแบบ PCL ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการสร้าง จัดการ และแปลงเอกสาร Word ในแอปพลิเคชัน C# หนึ่งในคุณสมบัติที่นำเสนอโดย Aspose.Words คือความสามารถในการแรสเตอร์องค์ประกอบที่แปลงแล้วเมื่อแปลงเอกสารเป็นรูปแบบที่แตกต่างกัน ในคู่มือนี้ เราจะแสดงวิธีใช้ซอร์สโค้ด C# ของ Aspose.Words สำหรับ .NET เพื่อปิดใช้งานการแรสเตอร์ขององค์ประกอบที่ถูกแปลงเมื่อแปลงเอกสารเป็นรูปแบบ PCL

## ทำความเข้าใจกับไลบรารี Aspose.Words

ก่อนที่จะเจาะลึกโค้ด สิ่งสำคัญคือต้องทำความเข้าใจไลบรารี Aspose.Words สำหรับ .NET Aspose.Words เป็นไลบรารียอดนิยมที่ทำให้การประมวลผลคำด้วยเอกสาร Word ง่ายและมีประสิทธิภาพ โดยนำเสนอคุณสมบัติที่หลากหลายสำหรับการสร้าง แก้ไข และแปลงเอกสาร Word รวมถึงการรองรับองค์ประกอบที่ถูกแปลงแบบแรสเตอร์ระหว่างการแปลง

## กำลังโหลดเอกสาร Word

ขั้นตอนแรกคือการโหลดเอกสาร Word ที่คุณต้องการแปลงเป็นรูปแบบ PCL ใช้คลาสเอกสารเพื่อโหลดเอกสารจากไฟล์ต้นฉบับ นี่คือตัวอย่าง:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

ในตัวอย่างนี้ เรากำลังโหลดเอกสาร "Rendering.docx" ที่อยู่ในไดเร็กทอรีเอกสาร

## การกำหนดค่าตัวเลือกการสำรองข้อมูล

ขั้นตอนต่อไปคือการกำหนดค่าตัวเลือกการบันทึกสำหรับการแปลงเป็นรูปแบบ PCL ใช้คลาส PclSaveOptions และตั้งค่าคุณสมบัติ RasterizeTransformedElements เป็น false ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

เราสร้างวัตถุ PclSaveOptions ใหม่และตั้งค่าคุณสมบัติ SaveFormat เป็น SaveFormat.Pcl เพื่อระบุว่าเราต้องการบันทึกเอกสารในรูปแบบ PCL ต่อไป เราตั้งค่าคุณสมบัติ RasterizeTransformedElements เป็นเท็จ เพื่อปิดใช้งานการแรสเตอร์ขององค์ประกอบที่แปลงแล้ว

## การแปลงเอกสารเป็นรูปแบบ PCL

ตอนนี้เราได้กำหนดค่าตัวเลือกการบันทึกแล้ว เราสามารถดำเนินการแปลงเอกสารเป็นรูปแบบ PCL ได้ ใช้วิธีการบันทึกของคลาสเอกสารเพื่อบันทึกเอกสารที่แปลงแล้วในรูปแบบ PCL โดยการระบุตัวเลือกการบันทึก นี่คือตัวอย่าง:

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

ในตัวอย่างนี้ เราบันทึกเอกสารที่แปลงแล้วเป็น "WorkingWithPclSaveOptions. RasterizeTransformedElements.pcl" โดยใช้ตัวเลือกการบันทึกที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับฟีเจอร์ "Rasterize Transformed Elements" ด้วย Aspose.Words สำหรับ .NET

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร Word


Document doc = new Document(dataDir + "Rendering.docx");

// กำหนดค่าตัวเลือกการสำรองข้อมูลสำหรับการแปลงเป็นรูปแบบ PCL
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// แปลงเอกสารเป็นรูปแบบ PCL
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## บทสรุป

ในคู่มือนี้ เราได้กล่าวถึงวิธีใช้ Aspose.Words สำหรับ .NET เพื่อปิดใช้งานการแรสเตอร์ขององค์ประกอบที่แปลงแล้ว เมื่อแปลงเอกสารเป็นรูปแบบ PCL โดยใช้ซอร์สโค้ด C# ที่ให้มา ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถควบคุมพฤติกรรมการแรสเตอร์ขององค์ประกอบที่ถูกแปลงได้อย่างง่ายดายเมื่อแปลงเอกสาร Word ของคุณเป็นรูปแบบที่แตกต่างกัน Aspose.Words มอบความยืดหยุ่นและพลังมหาศาลในการทำงานกับองค์ประกอบที่ได้รับการเปลี่ยนแปลง ช่วยให้คุณสร้างเอกสารที่แปลงแล้วตรงตามความต้องการเฉพาะของคุณ