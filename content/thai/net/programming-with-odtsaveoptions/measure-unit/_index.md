---
title: หน่วยวัด
linktitle: หน่วยวัด
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีระบุหน่วยวัดเมื่อแปลงเอกสาร Word เป็น ODT ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-odtsaveoptions/measure-unit/
---

เมื่อคุณแปลงเอกสาร Word เป็นรูปแบบ OpenDocument Text (ODT) ในแอปพลิเคชัน C# คุณอาจต้องการระบุหน่วยการวัดที่ใช้สำหรับการจัดรูปแบบที่วัดได้และคุณสมบัติเนื้อหา ด้วยไลบรารี Aspose.Words สำหรับ .NET คุณสามารถระบุฟังก์ชันนี้ได้อย่างง่ายดายโดยใช้ตัวเลือกการบันทึก OdtSaveOptions ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำวิธีใช้ Aspose.Words สำหรับซอร์สโค้ด .NET C# เพื่อแปลงเอกสาร Word เป็น ODT โดยการระบุหน่วยวัดโดยใช้ OdtSaveOptions

## ทำความเข้าใจกับไลบรารี Aspose.Words

ก่อนที่จะเจาะลึกโค้ด สิ่งสำคัญคือต้องทำความเข้าใจไลบรารี Aspose.Words สำหรับ .NET Aspose.Words เป็นไลบรารีที่มีประสิทธิภาพในการสร้าง แก้ไข แปลง และปกป้องเอกสาร Word ในแพลตฟอร์มต่างๆ รวมถึง .NET มันมีฟีเจอร์มากมายสำหรับการจัดการเอกสาร เช่น การแทรกข้อความ การเปลี่ยนการจัดรูปแบบ การเพิ่มส่วน และอื่นๆ อีกมากมาย

## กำลังโหลดเอกสาร Word

ขั้นตอนแรกคือโหลดเอกสาร Word ที่คุณต้องการแปลงเป็น ODT ใช้คลาสเอกสารเพื่อโหลดเอกสารจากไฟล์ต้นฉบับ นี่คือตัวอย่าง:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

ในตัวอย่างนี้ เราโหลดเอกสาร "Document.docx" ที่อยู่ในไดเร็กทอรีเอกสาร

## การกำหนดค่าตัวเลือกการสำรองข้อมูล

ขั้นตอนต่อไปคือการกำหนดค่าตัวเลือกการสำรองข้อมูลสำหรับการแปลงเป็น ODT ใช้คลาส OdtSaveOptions และตั้งค่าคุณสมบัติ MeasureUnit ให้เป็นค่าที่ต้องการ ตัวอย่างเช่น หากคุณต้องการใช้นิ้วเป็นหน่วยวัด ให้ตั้งค่า MeasureUnit เป็น OdtSaveMeasureUnit.Inches ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

เราสร้างออบเจ็กต์ OdtSaveOptions ใหม่และตั้งค่าคุณสมบัติ MeasureUnit เป็นค่าที่ต้องการ ในกรณีของเรา OdtSaveMeasureUnit.Inches เพื่อใช้นิ้วเป็นหน่วยการวัด

## แปลงเอกสารเป็น ODT

ตอนนี้เราได้กำหนดค่าตัวเลือกการบันทึกแล้ว เราสามารถดำเนินการแปลงเอกสารเป็น ODT ได้ ใช้วิธีการบันทึกของคลาสเอกสารเพื่อบันทึกเอกสารที่แปลงแล้วในรูปแบบ ODT โดยการระบุตัวเลือกการบันทึก นี่คือตัวอย่าง:

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

ในตัวอย่างนี้ เราบันทึกเอกสารที่แปลงเป็น "WorkingWithOdtSaveOptions.MeasureUnit.odt" โดยใช้ตัวเลือกการบันทึกที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับ OdtSaveOptions พร้อมฟังก์ชัน "หน่วยวัด" โดยใช้ Aspose.Words สำหรับ .NET



```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร Word
Document doc = new Document(dataDir + "Document.docx");

// การกำหนดค่าตัวเลือกสำรองด้วยคุณสมบัติ "หน่วยการวัด"
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// แปลงเอกสารเป็น ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## บทสรุป

ในคู่มือนี้ เราได้อธิบายวิธีการแปลงเอกสาร Word เป็น ODT โดยการระบุหน่วยการวัดโดยใช้ตัวเลือกการบันทึก OdtSaveOptions ด้วยไลบรารี Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้และใช้ซอร์สโค้ด C# ที่ให้มา คุณจะสามารถใช้ฟังก์ชันนี้ในแอปพลิเคชัน C# ของคุณได้อย่างง่ายดาย การระบุหน่วยการวัดเมื่อแปลงเป็น ODT ช่วยให้คุณสามารถควบคุมการจัดรูปแบบและขนาดของเอกสารผลลัพธ์ได้ตามความต้องการเฉพาะของคุณ