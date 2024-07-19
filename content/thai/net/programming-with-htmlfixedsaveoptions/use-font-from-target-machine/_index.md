---
title: ใช้แบบอักษรจากเครื่องเป้าหมาย
linktitle: ใช้แบบอักษรจากเครื่องเป้าหมาย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแปลงเอกสาร Word เป็น HTML แบบคงที่โดยใช้แบบอักษรของเครื่องเป้าหมายด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

เมื่อแปลงเอกสาร Word เป็น HTML แบบคงที่ในแอปพลิเคชัน C# คุณอาจต้องการใช้แบบอักษรของเครื่องเป้าหมายเพื่อให้แน่ใจว่า HTML ที่แสดงผลจะคงรูปลักษณ์และสไตล์ดั้งเดิมของเอกสารไว้ ด้วยไลบรารี Aspose.Words สำหรับ .NET คุณสามารถระบุฟังก์ชันนี้ได้อย่างง่ายดายโดยใช้ตัวเลือกการบันทึก HtmlFixedSaveOptions ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำวิธีใช้ซอร์สโค้ด C# ของ Aspose.Words สำหรับ .NET เพื่อแปลงเอกสาร Word เป็น HTML แบบคงที่โดยใช้แบบอักษรของเครื่องเป้าหมายโดยใช้ HtmlFixedSaveOptions

## ทำความเข้าใจกับไลบรารี Aspose.Words

ก่อนที่จะเจาะลึกโค้ด สิ่งสำคัญคือต้องทำความเข้าใจไลบรารี Aspose.Words สำหรับ .NET Aspose.Words เป็นไลบรารีที่มีประสิทธิภาพในการสร้าง แก้ไข แปลง และปกป้องเอกสาร Word ในแพลตฟอร์มต่างๆ รวมถึง .NET มันมีฟีเจอร์มากมายสำหรับการจัดการเอกสาร เช่น การแทรกข้อความ การเปลี่ยนการจัดรูปแบบ การเพิ่มส่วน และอื่นๆ อีกมากมาย

## กำลังโหลดเอกสาร Word

ขั้นตอนแรกคือการโหลดเอกสาร Word ที่คุณต้องการแปลงเป็น HTML แบบคงที่ ใช้คลาสเอกสารเพื่อโหลดเอกสารจากไฟล์ต้นฉบับ นี่คือตัวอย่าง:

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

ในตัวอย่างนี้ เราโหลดเอกสาร "Bullet point with Alternative font.docx" ที่อยู่ในไดเร็กทอรีเอกสาร

## การกำหนดค่าตัวเลือกการสำรองข้อมูล

ขั้นตอนต่อไปคือการกำหนดค่าตัวเลือกการบันทึกสำหรับการแปลงเป็น HTML แบบคงที่ ใช้คลาส HtmlFixedSaveOptions และตั้งค่าคุณสมบัติ UseTargetMachineFonts ให้เป็นจริงเพื่อบอกให้ Aspose.Words ใช้แบบอักษรจากเครื่องเป้าหมาย ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

เราสร้างออบเจ็กต์ HtmlFixedSaveOptions ใหม่และตั้งค่าคุณสมบัติ UseTargetMachineFonts ให้เป็นจริงเพื่อใช้แบบอักษรของเครื่องเป้าหมายเมื่อทำการแปลง

## แก้ไขการแปลงเอกสาร HTML

ตอนนี้เราได้กำหนดค่าตัวเลือกการบันทึกแล้ว เราสามารถดำเนินการแปลงเอกสารเป็น HTML แบบคงที่ได้ ใช้วิธีการบันทึกของคลาสเอกสารเพื่อบันทึกเอกสารที่แปลงแล้วในรูปแบบ HTML คงที่โดยการระบุตัวเลือกการบันทึก นี่คือตัวอย่าง:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

ในตัวอย่างนี้ เราบันทึกเอกสารที่แปลงแล้วเป็น "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" โดยใช้ตัวเลือกการบันทึกที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับ HtmlFixedSaveOptions พร้อมคุณสมบัติ "ใช้แบบอักษรจากเครื่องเป้าหมาย" โดยใช้ Aspose.Words สำหรับ .NET

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร Word
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// กำหนดค่าตัวเลือกการสำรองข้อมูลด้วยคุณสมบัติ "ใช้แบบอักษรจากเครื่องเป้าหมาย"
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// แปลงเอกสารเป็น HTML คงที่
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## บทสรุป

ในคู่มือนี้ เราได้อธิบายวิธีการแปลงเอกสาร Word เป็น HTML แบบคงที่โดยใช้แบบอักษรของเครื่องเป้าหมายด้วยไลบรารี Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้และใช้ซอร์สโค้ด C# ที่ให้มา คุณจะสามารถใช้ฟังก์ชันนี้ในแอปพลิเคชัน C# ของคุณได้อย่างง่ายดาย การแปลงเป็น HTML แบบคงที่ด้วยแบบอักษรของเครื่องเป้าหมายรับประกันการแสดงผลเอกสารในรูปแบบ HTML ที่เที่ยงตรงและสม่ำเสมอ
