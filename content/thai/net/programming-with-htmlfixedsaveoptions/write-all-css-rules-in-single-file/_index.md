---
title: เขียนกฎ Css ทั้งหมดในไฟล์เดียว
linktitle: เขียนกฎ Css ทั้งหมดในไฟล์เดียว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแปลงเอกสาร Word เป็น HTML แบบคงที่โดยการเขียนกฎ CSS ทั้งหมดในไฟล์เดียวด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

เมื่อแปลงเอกสาร Word เป็น HTML แบบคงที่ในแอปพลิเคชัน C# คุณอาจต้องการรวมกฎ CSS ทั้งหมดไว้ในไฟล์เดียวเพื่อการจัดระเบียบและการพกพาที่ดีขึ้น ด้วยไลบรารี Aspose.Words สำหรับ .NET คุณสามารถระบุฟังก์ชันนี้ได้อย่างง่ายดายโดยใช้ตัวเลือกการบันทึก HtmlFixedSaveOptions ในคำแนะนำทีละขั้นตอนนี้ เราจะอธิบายวิธีใช้ Aspose.Words สำหรับซอร์สโค้ด .NET C# เพื่อแปลงเอกสาร Word เป็น HTML แบบคงที่โดยการเขียนกฎ CSS ทั้งหมดในไฟล์เดียวโดยใช้ตัวเลือกการบันทึก HtmlFixedSaveOptions

## ทำความเข้าใจกับไลบรารี Aspose.Words

ก่อนที่จะเจาะลึกโค้ด สิ่งสำคัญคือต้องทำความเข้าใจไลบรารี Aspose.Words สำหรับ .NET Aspose.Words เป็นไลบรารีที่มีประสิทธิภาพในการสร้าง แก้ไข แปลง และปกป้องเอกสาร Word ในแพลตฟอร์มต่างๆ รวมถึง .NET มันมีฟีเจอร์มากมายสำหรับการจัดการเอกสาร เช่น การแทรกข้อความ การเปลี่ยนการจัดรูปแบบ การเพิ่มส่วน และอื่นๆ อีกมากมาย

## กำลังโหลดเอกสาร Word

ขั้นตอนแรกคือการโหลดเอกสาร Word ที่คุณต้องการแปลงเป็น HTML แบบคงที่ ใช้คลาสเอกสารเพื่อโหลดเอกสารจากไฟล์ต้นฉบับ นี่คือตัวอย่าง:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

ในตัวอย่างนี้ เราโหลดเอกสาร "Document.docx" ที่อยู่ในไดเร็กทอรีเอกสาร

## การกำหนดค่าตัวเลือกการสำรองข้อมูล

ขั้นตอนต่อไปคือการกำหนดค่าตัวเลือกการบันทึกสำหรับการแปลงเป็น HTML แบบคงที่ ใช้คลาส HtmlFixedSaveOptions และตั้งค่าคุณสมบัติ SaveFontFaceCssSeparately เป็น false เพื่อเขียนกฎ CSS ทั้งหมดในไฟล์เดียว ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

เราสร้างวัตถุ HtmlFixedSaveOptions ใหม่และตั้งค่าคุณสมบัติ SaveFontFaceCssSeparately เป็น false เพื่อเขียนกฎ CSS ทั้งหมดในไฟล์เดียว

## แก้ไขการแปลงเอกสาร HTML

ตอนนี้เราได้กำหนดค่าตัวเลือกการบันทึกแล้ว เราสามารถดำเนินการแปลงเอกสารเป็น HTML แบบคงที่ได้ ใช้วิธีการบันทึกของคลาสเอกสารเพื่อบันทึกเอกสารที่แปลงแล้วในรูปแบบ HTML คงที่โดยการระบุตัวเลือกการบันทึก นี่คือตัวอย่าง:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

ในตัวอย่างนี้ เราบันทึกเอกสารที่แปลงแล้วเป็น "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" โดยใช้ตัวเลือกการบันทึกที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับ HtmlFixedSaveOptions พร้อมคุณสมบัติ "เขียนกฎ CSS ทั้งหมดในไฟล์เดียว" โดยใช้ Aspose.Words สำหรับ .NET

```csharp
// เส้นทางการเข้าถึงไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร Word
Document doc = new Document(dataDir + "Document.docx");

// กำหนดค่าตัวเลือกการสำรองข้อมูลด้วยคุณสมบัติ "เขียนกฎ CSS ทั้งหมดในไฟล์เดียว"
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// แปลงเอกสารเป็น HTML คงที่
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## บทสรุป

ในคู่มือนี้ เราได้กล่าวถึงวิธีการแปลงเอกสาร Word เป็น HTML แบบคงที่โดยการเขียนกฎ CSS ทั้งหมดในไฟล์เดียวโดยใช้ HtmlFixedSaveOptions พร้อมด้วยไลบรารี Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้และใช้ซอร์สโค้ด C# ที่ให้มา คุณจะสามารถใช้ฟังก์ชันนี้ในแอปพลิเคชัน C# ของคุณได้อย่างง่ายดาย การเขียนกฎ CSS ทั้งหมดในไฟล์เดียวช่วยให้จัดระเบียบและจัดการโค้ด HTML ที่สร้างขึ้นระหว่างการแปลงเอกสารได้ง่ายขึ้น