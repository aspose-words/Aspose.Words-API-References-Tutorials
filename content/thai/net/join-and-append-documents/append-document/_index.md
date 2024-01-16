---
title: ผนวกเอกสาร
linktitle: ผนวกเอกสาร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผนวกเนื้อหาของเอกสารหนึ่งไปยังอีกเอกสารหนึ่งโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/append-document/
---

บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อผนวกเนื้อหาของเอกสารหนึ่งไปยังอีกเอกสารหนึ่ง ซอร์สโค้ดที่ให้มาสาธิตวิธีการเปิดเอกสารต้นทางและปลายทาง นำเข้าและผนวกส่วนต่างๆ จากเอกสารต้นทางไปยังเอกสารปลายทาง

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

## ขั้นตอนที่ 3: ผนวกส่วนต่างๆ จากเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 วนซ้ำทุกส่วนในเอกสารต้นฉบับและนำเข้าแต่ละส่วนไปยังเอกสารปลายทางโดยใช้`ImportNode` วิธี. จากนั้น ผนวกส่วนที่นำเข้าเข้ากับเอกสารปลายทาง

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## ขั้นตอนที่ 4: บันทึกเอกสารปลายทาง

 สุดท้าย ให้บันทึกเอกสารปลายทางที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

การดำเนินการผนวกเอกสารโดยใช้ Aspose.Words สำหรับ .NET เสร็จสมบูรณ์

### ตัวอย่างซอร์สโค้ดสำหรับการผนวกเอกสารโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// วนซ้ำทุกส่วนในเอกสารต้นฉบับ
	//โหนดส่วนเป็นโหนดย่อยของโหนดเอกสาร ดังนั้นเราจึงสามารถระบุเอกสารได้
	foreach (Section srcSection in srcDoc)
	{
		// เนื่องจากเรากำลังคัดลอกส่วนจากเอกสารหนึ่งไปยังอีกเอกสารหนึ่ง
		// จำเป็นต้องนำเข้าโหนดส่วนลงในเอกสารปลายทาง
		// ซึ่งจะปรับการอ้างอิงเฉพาะเอกสารไปยังสไตล์ รายการ ฯลฯ
		//
		// การนำเข้าโหนดจะสร้างสำเนาของโหนดดั้งเดิม แต่เป็นสำเนา
		// ss พร้อมที่จะแทรกลงในเอกสารปลายทาง
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// ขณะนี้โหนดส่วนใหม่สามารถต่อท้ายเอกสารปลายทางได้
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```