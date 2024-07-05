---
title: เก็บหมายเลขแหล่งที่มา
linktitle: เก็บหมายเลขแหล่งที่มา
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผนวกเอกสารในขณะที่ยังคงรักษาการจัดรูปแบบการกำหนดหมายเลขแหล่งที่มาใน Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/keep-source-numbering/
---

บทช่วยสอนนี้จะอธิบายวิธีการผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง ในขณะที่ยังคงรักษาการจัดรูปแบบการกำหนดหมายเลขดั้งเดิมของย่อหน้าที่มีหมายเลขโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

-  ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Releases]https://releases.aspose.com/words/net/ หรือใช้ตัวจัดการแพ็คเกจ NuGet เพื่อติดตั้ง
- เส้นทางไดเร็กทอรีเอกสารที่จะบันทึกเอกสารต้นทางและปลายทาง

## ขั้นตอนที่ 2: สร้างเอกสารปลายทางและต้นฉบับ

 สร้างอินสแตนซ์ของ`Document` สำหรับเอกสารปลายทางและต้นทาง

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ขั้นตอนที่ 3: เก็บหมายเลขแหล่งที่มาไว้เมื่อนำเข้า

 หากต้องการรักษาการจัดรูปแบบลำดับเลขของย่อหน้าที่มีลำดับเลขจากเอกสารต้นฉบับ ให้สร้างอินสแตนซ์ของ`ImportFormatOptions` และตั้งค่า`KeepSourceNumbering` ถึง`true` - ใช้`NodeImporter` เพื่อนำเข้าโหนดจากเอกสารต้นทางไปยังเอกสารปลายทาง โดยระบุ`ImportFormatMode.KeepSourceFormatting` และ`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## ขั้นตอนที่ 4: นำเข้าและต่อท้ายย่อหน้า

 วนซ้ำย่อหน้าในเอกสารต้นฉบับและนำเข้าแต่ละย่อหน้าไปยังเอกสารปลายทางโดยใช้`importer`- ผนวกโหนดที่นำเข้าเข้ากับเนื้อหาของเอกสารปลายทาง

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## ขั้นตอนที่ 5: บันทึกเอกสารที่แก้ไข

 บันทึกเอกสารที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

ซึ่งจะทำให้การดำเนินการผนวกเอกสารต้นทางเข้ากับเอกสารปลายทางเสร็จสมบูรณ์ ในขณะเดียวกันก็รักษาการจัดรูปแบบการกำหนดหมายเลขดั้งเดิมโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับ Keep Source Numbering โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//เก็บการจัดรูปแบบรายการต้นฉบับเมื่อนำเข้าย่อหน้าที่มีหมายเลขกำกับ
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```