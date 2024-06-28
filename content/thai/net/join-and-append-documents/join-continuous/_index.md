---
title: เข้าร่วมอย่างต่อเนื่อง
linktitle: เข้าร่วมอย่างต่อเนื่อง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีการรวมเอกสารสองฉบับอย่างต่อเนื่องโดยยังคงรักษาการจัดรูปแบบโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/join-continuous/
---

บทช่วยสอนนี้จะอธิบายวิธีการรวมเอกสารสองฉบับอย่างต่อเนื่องโดยใช้ Aspose.Words สำหรับ .NET ซอร์สโค้ดที่ให้มาจะสาธิตวิธีการต่อท้ายเอกสารต่อท้ายเอกสารอื่นโดยที่ยังคงรูปแบบเดิมไว้

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

## ขั้นตอนที่ 3: ตั้งค่าการเริ่มต้นส่วนต่อเนื่อง

หากต้องการให้เอกสารต้นทางปรากฏต่อจากเนื้อหาของเอกสารปลายทาง ให้ตั้งค่า`SectionStart` คุณสมบัติของส่วนแรกในเอกสารต้นฉบับถึง`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ขั้นตอนที่ 4: ผนวกเอกสารต้นฉบับ

 ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางโดยใช้`AppendDocument` วิธีการของ`Document` ชั้นเรียน ตั้งค่าโหมดรูปแบบการนำเข้าเป็น`ImportFormatMode.KeepSourceFormatting` เพื่อรักษาสไตล์ดั้งเดิมจากเอกสารต้นฉบับ

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 5: บันทึกเอกสารที่แก้ไข

สุดท้าย ให้บันทึกเอกสารปลายทางที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ วัตถุ

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

การดำเนินการนี้ทำให้การรวมเอกสารสองฉบับเข้าด้วยกันอย่างต่อเนื่องโดยใช้ Aspose.Words สำหรับ .NET เสร็จสมบูรณ์

### ตัวอย่างซอร์สโค้ดสำหรับเข้าร่วมต่อเนื่องโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// ทำให้เอกสารปรากฏต่อจากเนื้อหาเอกสารปลายทาง
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// ผนวกเอกสารต้นฉบับโดยใช้สไตล์ดั้งเดิมที่พบในเอกสารต้นฉบับ
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```