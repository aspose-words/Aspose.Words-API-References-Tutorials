---
title: รายการเก็บการจัดรูปแบบต้นฉบับ
linktitle: รายการเก็บการจัดรูปแบบต้นฉบับ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรักษาการจัดรูปแบบรายการในขณะที่เข้าร่วมและต่อท้ายเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/list-keep-source-formatting/
---

บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้ฟีเจอร์ List Keep Source Formatting ของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเข้าร่วมและต่อท้ายเอกสาร Word ในขณะที่ยังคงรักษาการจัดรูปแบบต้นฉบับของรายการไว้

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## ขั้นตอนที่ 3: ตั้งค่าเอกสารต้นทางให้ไหลอย่างต่อเนื่อง

 เพื่อให้แน่ใจว่าเนื้อหาจากเอกสารต้นฉบับไหลอย่างต่อเนื่องเมื่อผนวกเข้ากับเอกสารปลายทาง คุณต้องตั้งค่า`SectionStart` คุณสมบัติของส่วนแรกในเอกสารต้นฉบับถึง`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ขั้นตอนที่ 4: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ตอนนี้คุณสามารถผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางได้โดยใช้`AppendDocument` วิธีการของ`Document` ระดับ. ที่`ImportFormatMode.KeepSourceFormatting`พารามิเตอร์ช่วยให้แน่ใจว่าการจัดรูปแบบต้นฉบับ รวมถึงการจัดรูปแบบของรายการ จะถูกรักษาไว้ในระหว่างการดำเนินการผนวก

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 5: บันทึกเอกสารขั้นสุดท้าย

 สุดท้าย ให้บันทึกเอกสารที่ผสานโดยเปิดใช้งานคุณลักษณะ List Keep Source Formatting โดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับ List Keep Source Formatting โดยใช้ Aspose.Words สำหรับ .NET 

นี่คือซอร์สโค้ดแบบเต็มสำหรับฟีเจอร์ List Keep Source Formatting ใน C# โดยใช้ Aspose.Words สำหรับ .NET:

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// ผนวกเนื้อหาของเอกสารเพื่อให้ไหลอย่างต่อเนื่อง
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

แค่นั้นแหละ! คุณใช้งานฟีเจอร์การจัดรูปแบบ List Keep Source โดยใช้ Aspose.Words สำหรับ .NET สำเร็จแล้ว เอกสารขั้นสุดท้ายจะมีเนื้อหาที่ผสานโดยยังคงรักษาการจัดรูปแบบรายการของเอกสารต้นฉบับไว้