---
title: ลิงก์ส่วนหัวส่วนท้าย
linktitle: ลิงก์ส่วนหัวส่วนท้าย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีการเชื่อมโยงส่วนหัวและส่วนท้ายในขณะที่เข้าร่วมและต่อท้ายเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/link-headers-footers/
---

บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้คุณสมบัติ Link Headers Footers ของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเข้าร่วมและต่อท้ายเอกสาร Word หลายชุดในขณะที่เชื่อมโยงส่วนหัวและส่วนท้ายของเอกสารต้นฉบับไปยังส่วนก่อนหน้าในเอกสารปลายทาง

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

## ขั้นตอนที่ 3: ตั้งค่าเอกสารต่อท้ายให้ปรากฏบนหน้าใหม่

 เพื่อให้แน่ใจว่าเนื้อหาจากเอกสารต้นฉบับปรากฏบนหน้าใหม่ในเอกสารปลายทาง คุณต้องตั้งค่า`SectionStart` คุณสมบัติของส่วนแรกในเอกสารต้นฉบับถึง`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## ขั้นตอนที่ 4: เชื่อมโยงส่วนหัวและส่วนท้ายไปยังส่วนก่อนหน้า

 หากต้องการเชื่อมโยงส่วนหัวและส่วนท้ายของเอกสารต้นฉบับกับส่วนก่อนหน้าในเอกสารปลายทาง คุณสามารถใช้`LinkToPrevious` วิธีการของ`HeadersFooters` ของสะสม. โดยผ่าน`true` ในฐานะพารามิเตอร์ คุณจะแทนที่ส่วนหัวหรือส่วนท้ายที่มีอยู่ในเอกสารต้นฉบับ

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## ขั้นตอนที่ 5: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ตอนนี้คุณสามารถผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางได้โดยใช้`AppendDocument` วิธีการของ`Document` ระดับ. ที่`ImportFormatMode.KeepSourceFormatting` พารามิเตอร์ช่วยให้มั่นใจได้ว่าการจัดรูปแบบต้นฉบับจะถูกรักษาไว้ระหว่างการดำเนินการผนวก

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 6: บันทึกเอกสารขั้นสุดท้าย

 สุดท้าย ให้บันทึกเอกสารที่ผสานด้วยส่วนหัวและส่วนท้ายที่เชื่อมโยงโดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Link Headers Footers โดยใช้ Aspose.Words สำหรับ .NET 

นี่คือซอร์สโค้ดแบบเต็มสำหรับฟีเจอร์ "Link Headers Footers" ใน C# โดยใช้ Aspose.Words สำหรับ .NET:


```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// ตั้งค่าเอกสารต่อท้ายให้ปรากฏในหน้าใหม่
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// เชื่อมโยงส่วนหัวและส่วนท้ายในเอกสารต้นฉบับกับส่วนก่อนหน้า
	// การดำเนินการนี้จะแทนที่ส่วนหัวหรือส่วนท้ายใดๆ ที่พบในเอกสารต้นฉบับ
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

แค่นั้นแหละ! คุณได้ปรับใช้คุณลักษณะ Link Headers Footers สำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET เอกสารขั้นสุดท้ายจะมีเนื้อหาที่ผสานเข้ากับส่วนหัวและส่วนท้ายจากเอกสารต้นฉบับที่เชื่อมโยงกับส่วนก่อนหน้าในเอกสารปลายทาง