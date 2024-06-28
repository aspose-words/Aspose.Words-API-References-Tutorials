---
title: เก็บการจัดรูปแบบแหล่งที่มา
linktitle: เก็บการจัดรูปแบบแหล่งที่มา
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางโดยยังคงรักษาการจัดรูปแบบดั้งเดิมโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/keep-source-formatting/
---

บทช่วยสอนนี้สาธิตวิธีการผนวกเอกสารต้นทางเข้ากับเอกสารปลายทางในขณะที่ยังคงรูปแบบดั้งเดิมของเอกสารต้นทางโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Releases]https://releases.aspose.com/words/net/ หรือใช้ตัวจัดการแพ็คเกจ NuGet เพื่อติดตั้ง
- เส้นทางไดเร็กทอรีเอกสารที่จะบันทึกเอกสารต้นทางและปลายทาง

## ขั้นตอนที่ 2: สร้างเอกสารปลายทางและต้นฉบับ

 สร้างอินสแตนซ์ของ`Document` สำหรับเอกสารปลายทางและต้นทาง

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## ขั้นตอนที่ 3: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ใช้`AppendDocument` วิธีการนำเอกสารปลายทางมาต่อท้ายเอกสารต้นทาง ผ่าน`ImportFormatMode.KeepSourceFormatting` เป็นโหมดรูปแบบการนำเข้าเพื่อรักษารูปแบบดั้งเดิมของเอกสารต้นฉบับ

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข

 บันทึกเอกสารที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ วัตถุ

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

การดำเนินการนี้จะทำให้การผนวกเอกสารต้นทางเข้ากับเอกสารปลายทางเสร็จสมบูรณ์ ในขณะเดียวกันก็รักษาการจัดรูปแบบดั้งเดิมโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับเก็บการจัดรูปแบบต้นฉบับโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง
	// ผ่านโหมดรูปแบบเพื่อรักษารูปแบบดั้งเดิมของเอกสารต้นฉบับเมื่อนำเข้า
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```