---
title: รีสตาร์ทการกำหนดหมายเลขหน้า
linktitle: รีสตาร์ทการกำหนดหมายเลขหน้า
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรีสตาร์ทการกำหนดหมายเลขหน้าขณะเข้าร่วมและต่อท้ายเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/restart-page-numbering/
---

บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้คุณสมบัติการรีสตาร์ทการกำหนดหมายเลขหน้าของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเข้าร่วมและต่อท้ายเอกสาร Word ในขณะที่เริ่มใหม่การกำหนดหมายเลขหน้าในเอกสารต้นฉบับ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ติดตั้ง Aspose.Words สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose หรือติดตั้งผ่าน NuGet
2. Visual Studio หรือสภาพแวดล้อมการพัฒนา C# อื่น ๆ

## ขั้นตอนที่ 1: เริ่มต้นไดเร็กทอรีเอกสาร

 ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แก้ไขค่าของ`dataDir` ตัวแปรไปยังเส้นทางที่เอกสารของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารต้นทางและปลายทาง

 ถัดไป คุณต้องโหลดเอกสารต้นทางและปลายทางโดยใช้ Aspose.Words`Document` ระดับ. อัพเดตชื่อไฟล์ใน`Document` ตัวสร้างตามชื่อเอกสารของคุณ

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ขั้นตอนที่ 3: ตั้งค่าเอกสารต้นฉบับเพื่อเริ่มการกำหนดหมายเลขหน้าใหม่

 หากต้องการเริ่มการกำหนดหมายเลขหน้าใหม่ในเอกสารต้นฉบับ คุณต้องตั้งค่า`SectionStart` คุณสมบัติของส่วนแรกในเอกสารต้นฉบับถึง`SectionStart.NewPage` และตั้งค่า`RestartPageNumbering`ทรัพย์สินเพื่อ`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## ขั้นตอนที่ 4: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ตอนนี้คุณสามารถผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางได้โดยใช้`AppendDocument` วิธีการของ`Document` ระดับ. ที่`ImportFormatMode.KeepSourceFormatting` พารามิเตอร์ช่วยให้มั่นใจได้ว่าการจัดรูปแบบต้นฉบับจะถูกรักษาไว้ระหว่างการดำเนินการผนวก

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 5: บันทึกเอกสารขั้นสุดท้าย

 สุดท้าย ให้บันทึกเอกสารที่ผสานโดยเปิดใช้งานคุณลักษณะ Restart Page Numbering โดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการรีสตาร์ทการกำหนดหมายเลขหน้าโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดแบบเต็มสำหรับฟีเจอร์ "รีสตาร์ทการกำหนดหมายเลขหน้า" ใน C# โดยใช้ Aspose.Words สำหรับ .NET:
 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

แค่นั้นแหละ! คุณได้นำคุณลักษณะการรีสตาร์ทการกำหนดหมายเลขหน้าไปใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว เอกสารขั้นสุดท้ายจะมีเนื้อหาที่ผสานโดยเริ่มการเริ่มหมายเลขหน้าใหม่ในเอกสารต้นฉบับ