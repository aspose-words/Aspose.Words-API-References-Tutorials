---
title: การตั้งค่าหน้าต่างๆ
linktitle: การตั้งค่าหน้าต่างๆ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผนวกเอกสารด้วยการตั้งค่าหน้าต่างๆ โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/different-page-setup/
---

บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อผนวกเอกสารที่มีการตั้งค่าหน้าที่แตกต่างกันไปยังเอกสารอื่น ซอร์สโค้ดที่ให้มาสาธิตวิธีการตั้งค่าหน้าต่างๆ สำหรับเอกสารต้นทางและปลายทาง และรับประกันความต่อเนื่องและการกำหนดหมายเลขที่เหมาะสม

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

## ขั้นตอนที่ 3: ตั้งค่าการตั้งค่าหน้าสำหรับเอกสารต้นฉบับ

 ปรับการตั้งค่าหน้าของเอกสารต้นทางเพื่อให้แน่ใจว่ามีความต่อเนื่องและกำหนดหมายเลขอย่างเหมาะสม ในตัวอย่างนี้ เราตั้งค่าส่วนเริ่มต้นเป็น`SectionStart.Continuous`และรีสตาร์ทการกำหนดหมายเลขหน้า เรายังตรวจสอบให้แน่ใจด้วยว่าความกว้าง ความสูง และการวางแนวของหน้าตรงกับส่วนสุดท้ายของเอกสารปลายทาง

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## ขั้นตอนที่ 4: แก้ไขการจัดรูปแบบย่อหน้า

 เพื่อรักษาการจัดรูปแบบที่เหมาะสม ให้วนซ้ำทุกย่อหน้าในเอกสารต้นฉบับและตั้งค่า`KeepWithNext`ทรัพย์สินเพื่อ`true`- เพื่อให้แน่ใจว่าย่อหน้าจะอยู่ด้วยกันในระหว่างกระบวนการต่อท้าย

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## ขั้นตอนที่ 5: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ใช้`AppendDocument` วิธีการของเอกสารปลายทางเพื่อผนวกเอกสารต้นฉบับที่แก้ไขเข้ากับเอกสารปลายทาง โดยคงการจัดรูปแบบต้นฉบับไว้

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 6: บันทึกเอกสารปลายทาง

สุดท้าย ให้บันทึกเอกสารปลายทางที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ วัตถุ

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

การดำเนินการนี้จะทำให้การดำเนินการผนวกเอกสารด้วยการตั้งค่าการตั้งค่าหน้าต่างๆ เสร็จสมบูรณ์โดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับการตั้งค่าเพจต่างๆ โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// ตั้งค่าเอกสารต้นทางให้ดำเนินการต่อโดยตรงหลังจากสิ้นสุดเอกสารปลายทาง
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// เริ่มการกำหนดหมายเลขหน้าที่จุดเริ่มต้นของเอกสารต้นฉบับอีกครั้ง
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//เพื่อให้แน่ใจว่าสิ่งนี้จะไม่เกิดขึ้นเมื่อเอกสารต้นฉบับมีการตั้งค่าหน้าที่แตกต่างกัน ตรวจสอบให้แน่ใจว่า
	// การตั้งค่าจะเหมือนกันระหว่างส่วนสุดท้ายของเอกสารปลายทาง
	// หากมีส่วนที่ต่อเนื่องกันเพิ่มเติมที่ตามมาในเอกสารต้นฉบับ
	// จะต้องทำซ้ำในส่วนเหล่านั้น
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// วนซ้ำทุกส่วนในเอกสารต้นฉบับ
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```