---
title: แทรกเอกสารด้วยตัวสร้าง
linktitle: แทรกเอกสารด้วยตัวสร้าง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกเอกสารที่ส่วนท้ายของเอกสารอื่นโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/insert-document-with-builder/
---

 บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อแทรกเอกสารลงในเอกสารอื่นโดยใช้`DocumentBuilder` ชั้นเรียน ซอร์สโค้ดที่ให้มาสาธิตวิธีการแทรกเอกสารที่ส่วนท้ายของเอกสารอื่นโดยยังคงรักษาการจัดรูปแบบต้นฉบับไว้

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

## ขั้นตอนที่ 3: เริ่มต้น DocumentBuilder

 สร้างอินสแตนซ์ใหม่ของ`DocumentBuilder` คลาสและส่งเอกสารปลายทางเป็นพารามิเตอร์

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## ขั้นตอนที่ 4: วางตำแหน่ง DocumentBuilder

ย้าย`DocumentBuilder` ที่ส่วนท้ายของเอกสารโดยใช้`MoveToDocumentEnd` วิธี. แทรกตัวแบ่งหน้าเพื่อแยกเนื้อหาที่มีอยู่ออกจากเอกสารที่แทรก

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## ขั้นตอนที่ 5: แทรกเอกสารต้นฉบับ

 ใช้`InsertDocument` วิธีการของ`DocumentBuilder` คลาสเพื่อแทรกเอกสารต้นฉบับลงในเอกสารปลายทาง ตั้งค่าโหมดรูปแบบการนำเข้าเป็น`ImportFormatMode.KeepSourceFormatting` เพื่อรักษาการจัดรูปแบบต้นฉบับ

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไข

สุดท้าย ให้บันทึกเอกสารปลายทางที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ วัตถุ

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

การดำเนินการแทรกเอกสารลงในเอกสารอื่นโดยใช้ Aspose.Words สำหรับ .NET เสร็จสมบูรณ์

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกเอกสารด้วย Builder โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```