---
title: ผนวกเอกสารลงในช่องว่าง
linktitle: ผนวกเอกสารลงในช่องว่าง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผนวกเอกสารเข้ากับเอกสารปลายทางที่ว่างเปล่าใน Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/append-document-to-blank/
---

บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อผนวกเนื้อหาของเอกสารหนึ่งฉบับเข้ากับเอกสารปลายทางที่ว่างเปล่า ซอร์สโค้ดที่ให้มาสาธิตวิธีการสร้างเอกสารใหม่ ลบเนื้อหา และจากนั้นจึงผนวกเอกสารต้นฉบับเข้าไป

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Releases]https://releases.aspose.com/words/net/ หรือใช้ตัวจัดการแพ็คเกจ NuGet เพื่อติดตั้ง
- เส้นทางไดเร็กทอรีเอกสารที่มีเอกสารต้นทางและปลายทางอยู่

## ขั้นตอนที่ 2: สร้างเอกสารปลายทางใหม่

 สร้างใหม่`Document` วัตถุสำหรับเอกสารปลายทาง

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## ขั้นตอนที่ 3: ลบเนื้อหาที่มีอยู่ออกจากเอกสารปลายทาง

 เพื่อให้แน่ใจว่าเอกสารปลายทางสะอาด ให้ลบเนื้อหาที่มีอยู่ทั้งหมดออกจากเอกสารโดยใช้`RemoveAllChildren` วิธี.

```csharp
dstDoc.RemoveAllChildren();
```

## ขั้นตอนที่ 4: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ผนวกเนื้อหาของเอกสารต้นฉบับไปยังเอกสารปลายทางโดยใช้`AppendDocument` วิธีการด้วย`ImportFormatMode.KeepSourceFormatting` ตัวเลือก.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 5: บันทึกเอกสารปลายทาง

สุดท้าย ให้บันทึกเอกสารปลายทางที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ วัตถุ

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

ซึ่งจะทำให้การดำเนินการผนวกเอกสารเข้ากับเอกสารปลายทางที่ว่างเปล่าโดยใช้ Aspose.Words สำหรับ .NET เสร็จสมบูรณ์

### ตัวอย่างซอร์สโค้ดสำหรับผนวกเอกสารไปยังช่องว่างโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// เอกสารปลายทางไม่ว่างเปล่า มักทำให้หน้าว่างปรากฏขึ้นก่อนเอกสารที่ต่อท้าย
	// นี่เป็นเพราะเอกสารฐานมีส่วนว่างและเอกสารใหม่กำลังเริ่มต้นในหน้าถัดไป
	// ลบเนื้อหาทั้งหมดออกจากเอกสารปลายทางก่อนที่จะต่อท้าย
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```