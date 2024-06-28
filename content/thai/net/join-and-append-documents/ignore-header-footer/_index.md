---
title: ละเว้นส่วนหัวส่วนท้าย
linktitle: ละเว้นส่วนหัวส่วนท้าย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผนวกเอกสารโดยไม่สนใจเนื้อหาส่วนหัวและส่วนท้ายโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/ignore-header-footer/
---

บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อผนวกเอกสารโดยไม่สนใจเนื้อหาส่วนหัวและส่วนท้าย ซอร์สโค้ดที่ให้มาสาธิตวิธีการตั้งค่าตัวเลือกรูปแบบการนำเข้าเพื่อแยกส่วนหัวและส่วนท้ายในระหว่างกระบวนการต่อท้าย

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Releases]https://releases.aspose.com/words/net/ หรือใช้ตัวจัดการแพ็คเกจ NuGet เพื่อติดตั้ง
- เส้นทางไดเร็กทอรีเอกสารที่มีเอกสารต้นทางและปลายทางอยู่

## ขั้นตอนที่ 2: เปิดเอกสารต้นทางและปลายทาง

 เปิดเอกสารต้นทางและปลายทางโดยใช้`Document` ตัวสร้างคลาส แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกรูปแบบการนำเข้า

 สร้างอินสแตนซ์ของ`ImportFormatOptions` คลาสและตั้งค่า`IgnoreHeaderFooter`ทรัพย์สินเพื่อ`false`- เพื่อให้แน่ใจว่าเนื้อหาส่วนหัวและส่วนท้ายถูกรวมไว้ในระหว่างกระบวนการต่อท้าย

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## ขั้นตอนที่ 4: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ใช้`AppendDocument` วิธีการนำเอกสารปลายทางมาต่อท้ายเอกสารต้นทาง ผ่าน`ImportFormatMode.KeepSourceFormatting`เป็นพารามิเตอร์ที่สองและตัวเลือกรูปแบบการนำเข้าเป็นพารามิเตอร์ที่สาม

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## ขั้นตอนที่ 5: บันทึกเอกสารปลายทาง

สุดท้าย ให้บันทึกเอกสารปลายทางที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ วัตถุ

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

การดำเนินการนี้ทำให้การใช้งานการต่อท้ายเอกสารเสร็จสมบูรณ์โดยไม่สนใจเนื้อหาส่วนหัวและส่วนท้ายโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับละเว้น Header Footer โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```