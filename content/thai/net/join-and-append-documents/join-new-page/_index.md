---
title: เข้าร่วมหน้าใหม่
linktitle: เข้าร่วมหน้าใหม่
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรวมเอกสารสองฉบับในหน้าใหม่โดยคงการจัดรูปแบบไว้โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/join-new-page/
---

บทช่วยสอนนี้จะอธิบายวิธีรวมเอกสารสองฉบับในหน้าใหม่โดยใช้ Aspose.Words สำหรับ .NET ซอร์สโค้ดที่ให้มาสาธิตวิธีการต่อท้ายเอกสารที่ส่วนท้ายของเอกสารอื่นในขณะที่เริ่มต้นเอกสารต่อท้ายในหน้าใหม่

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Releases]https://releases.aspose.com/words/net/ หรือใช้ตัวจัดการแพ็คเกจ NuGet เพื่อติดตั้ง
- เส้นทางไดเร็กทอรีเอกสารที่มีเอกสารต้นทางและปลายทางอยู่

## ขั้นตอนที่ 2: เปิดเอกสารต้นทางและปลายทาง

 เปิดเอกสารต้นทางและปลายทางโดยใช้`Document` ตัวสร้างคลาส แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ขั้นตอนที่ 3: ตั้งค่าการเริ่มต้นส่วนของหน้าใหม่

 หากต้องการเริ่มเอกสารต่อท้ายในหน้าใหม่ ให้ตั้งค่า`SectionStart` คุณสมบัติของส่วนแรกในเอกสารต้นฉบับถึง`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## ขั้นตอนที่ 4: ผนวกเอกสารต้นฉบับ

 ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางโดยใช้`AppendDocument` วิธีการของ`Document` ระดับ. ตั้งค่าโหมดรูปแบบการนำเข้าเป็น`ImportFormatMode.KeepSourceFormatting` เพื่อรักษาสไตล์ดั้งเดิมจากเอกสารต้นฉบับ

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 5: บันทึกเอกสารที่แก้ไข

สุดท้าย ให้บันทึกเอกสารปลายทางที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

การดำเนินการนี้จะทำให้การรวมเอกสารสองฉบับในหน้าใหม่เสร็จสมบูรณ์โดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับการเข้าร่วมเพจใหม่โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// ตั้งค่าเอกสารต่อท้ายให้เริ่มต้นในหน้าใหม่
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// ผนวกเอกสารต้นฉบับโดยใช้สไตล์ดั้งเดิมที่พบในเอกสารต้นฉบับ
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```