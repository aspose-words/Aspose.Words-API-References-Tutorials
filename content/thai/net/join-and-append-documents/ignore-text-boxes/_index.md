---
title: ละเว้นกล่องข้อความ
linktitle: ละเว้นกล่องข้อความ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผนวกเอกสารโดยไม่สนใจการจัดรูปแบบกล่องข้อความโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/ignore-text-boxes/
---

บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อผนวกเอกสารโดยยังคงรักษาการจัดรูปแบบของกล่องข้อความไว้ ซอร์สโค้ดที่ให้มาสาธิตวิธีการตั้งค่าตัวเลือกรูปแบบการนำเข้าเพื่อรวมกล่องข้อความในระหว่างกระบวนการต่อท้าย

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

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกรูปแบบการนำเข้า

 สร้างอินสแตนซ์ของ`ImportFormatOptions` คลาสและตั้งค่า`IgnoreTextBoxes`ทรัพย์สินเพื่อ`false`- เพื่อให้แน่ใจว่ากล่องข้อความจะรวมอยู่ในกระบวนการต่อท้ายโดยที่ยังคงการจัดรูปแบบไว้

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## ขั้นตอนที่ 4: ผนวกเนื้อหากล่องข้อความ

 สร้างก`NodeImporter`object และใช้เพื่อนำเข้าโหนดกล่องข้อความจากเอกสารต้นทางไปยังเอกสารปลายทาง วนซ้ำแต่ละย่อหน้าในเอกสารต้นฉบับและนำเข้าไปยังเอกสารปลายทาง

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## ขั้นตอนที่ 5: บันทึกเอกสารปลายทาง

สุดท้าย ให้บันทึกเอกสารปลายทางที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ วัตถุ

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

การดำเนินการนี้ทำให้การดำเนินการผนวกเอกสารเสร็จสมบูรณ์ในขณะที่ยังคงรักษาการจัดรูปแบบกล่องข้อความโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับละเว้นกล่องข้อความโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// รักษาการจัดรูปแบบกล่องข้อความต้นฉบับเมื่อนำเข้า
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```