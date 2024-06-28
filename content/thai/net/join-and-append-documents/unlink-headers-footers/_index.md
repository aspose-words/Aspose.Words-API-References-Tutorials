---
title: ยกเลิกการเชื่อมโยงส่วนหัวส่วนท้าย
linktitle: ยกเลิกการเชื่อมโยงส่วนหัวส่วนท้าย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเข้าร่วมและผนวกเอกสาร Word ในขณะที่ยกเลิกการเชื่อมโยงส่วนหัวและส่วนท้ายโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/unlink-headers-footers/
---

บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้ฟีเจอร์ Unlink Headers Footers ของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเข้าร่วมและต่อท้ายเอกสาร Word ในขณะที่ยกเลิกการเชื่อมโยงส่วนหัวและส่วนท้ายจากเอกสารต้นฉบับ

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

ถัดไป คุณต้องโหลดเอกสารต้นทางและปลายทางโดยใช้ Aspose.Words`Document` ชั้นเรียน อัพเดตชื่อไฟล์ใน`Document` ตัวสร้างตามชื่อเอกสารของคุณ

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ขั้นตอนที่ 3: ยกเลิกการเชื่อมโยงส่วนหัวและส่วนท้ายในเอกสารต้นฉบับ

 หากต้องการยกเลิกการเชื่อมโยงส่วนหัวและส่วนท้ายในเอกสารต้นทางจากการดำเนินการต่อส่วนหัวและส่วนท้ายของเอกสารปลายทาง คุณจะต้องตั้งค่า`LinkToPrevious` ทรัพย์สินของ`HeadersFooters` คอลเลกชันในส่วนแรกของเอกสารต้นทางถึง`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## ขั้นตอนที่ 4: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ตอนนี้คุณสามารถผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางได้โดยใช้`AppendDocument` วิธีการของ`Document` ชั้นเรียน ที่`ImportFormatMode.KeepSourceFormatting` พารามิเตอร์ช่วยให้แน่ใจว่าการจัดรูปแบบต้นฉบับจะถูกรักษาไว้ระหว่างการดำเนินการผนวก

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 5: บันทึกเอกสารขั้นสุดท้าย

 สุดท้าย ให้บันทึกเอกสารที่ผสานโดยเปิดใช้งานคุณลักษณะ Unlink Headers Footers โดยใช้`Save` วิธีการของ`Document` ชั้นเรียน

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Unlink Headers Footers โดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดแบบเต็มสำหรับฟีเจอร์ "Unlink Headers Footers" ใน C# โดยใช้ Aspose.Words สำหรับ .NET:

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// ยกเลิกการเชื่อมโยงส่วนหัวและส่วนท้ายในเอกสารต้นฉบับเพื่อหยุดสิ่งนี้
	// จากการต่อหัวกระดาษและท้ายกระดาษปลายทาง
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

แค่นั้นแหละ! คุณใช้งานฟีเจอร์ Unlink Headers Footers สำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET เอกสารขั้นสุดท้ายจะมีเนื้อหาที่ผสานโดยมีส่วนหัวและส่วนท้ายจากเอกสารต้นฉบับที่ไม่ได้เชื่อมโยงจากเอกสารปลายทาง