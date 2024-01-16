---
title: ผนวกด้วยตัวเลือกรูปแบบการนำเข้า
linktitle: ผนวกด้วยตัวเลือกรูปแบบการนำเข้า
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผนวกเอกสารด้วยตัวเลือกรูปแบบการนำเข้าโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/append-with-import-format-options/
---

บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อผนวกเนื้อหาของเอกสารหนึ่งไปยังอีกเอกสารหนึ่งด้วยตัวเลือกรูปแบบการนำเข้า ซอร์สโค้ดที่ให้มาสาธิตวิธีการเปิดเอกสารต้นทางและปลายทาง ระบุตัวเลือกรูปแบบการนำเข้า และผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Releases]https://releases.aspose.com/words/net/ หรือใช้ตัวจัดการแพ็คเกจ NuGet เพื่อติดตั้ง
- เส้นทางไดเร็กทอรีเอกสารที่มีเอกสารต้นทางและปลายทางอยู่

## ขั้นตอนที่ 2: เปิดเอกสารต้นทางและปลายทาง

 เปิดเอกสารต้นทางและปลายทางโดยใช้`Document` ตัวสร้างคลาส แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## ขั้นตอนที่ 3: ระบุตัวเลือกรูปแบบการนำเข้า

 สร้างอินสแตนซ์ของ`ImportFormatOptions` คลาสเพื่อระบุตัวเลือกรูปแบบการนำเข้า ในตัวอย่างนี้ เราใช้`KeepSourceNumbering` คุณสมบัติเพื่อให้แน่ใจว่ามีการใช้การกำหนดหมายเลขจากเอกสารต้นทางหากมีข้อขัดแย้งกับเอกสารปลายทาง

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## ขั้นตอนที่ 4: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ใช้`AppendDocument` วิธีการนำเอกสารปลายทางมาต่อท้ายเอกสารต้นทาง ผ่าน`ImportFormatMode.UseDestinationStyles` เป็นพารามิเตอร์ตัวที่สองเพื่อใช้สไตล์และการจัดรูปแบบของเอกสารปลายทาง

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## ขั้นตอนที่ 5: บันทึกเอกสารปลายทาง

 สุดท้าย ให้บันทึกเอกสารปลายทางที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

ซึ่งจะทำให้การดำเนินการผนวกเอกสารด้วยตัวเลือกรูปแบบการนำเข้าเสร็จสมบูรณ์โดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับผนวกด้วยตัวเลือกรูปแบบการนำเข้าโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// ระบุว่าหากการขัดแย้งกันของหมายเลขในเอกสารต้นทางและปลายทาง
	//จากนั้นจะใช้การกำหนดหมายเลขจากเอกสารต้นทาง
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```