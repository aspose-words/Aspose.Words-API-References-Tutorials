---
title: ใช้สไตล์ปลายทาง
linktitle: ใช้สไตล์ปลายทาง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเข้าร่วมและผนวกเอกสาร Word ในขณะที่ใช้สไตล์เอกสารปลายทางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/use-destination-styles/
---

บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้ฟีเจอร์ใช้สไตล์ปลายทางของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเข้าร่วมและต่อท้ายเอกสาร Word ในขณะที่ใช้สไตล์ของเอกสารปลายทาง

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

## ขั้นตอนที่ 3: ผนวกเอกสารต้นฉบับด้วยสไตล์ปลายทาง

 หากต้องการเพิ่มเอกสารต้นทางต่อท้ายเอกสารปลายทางในขณะที่นำสไตล์ของเอกสารปลายทางไปใช้ คุณสามารถใช้`AppendDocument` วิธีการของ`Document` ชั้นเรียนด้วย`ImportFormatMode.UseDestinationStyles` พารามิเตอร์.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## ขั้นตอนที่ 4: บันทึกเอกสารขั้นสุดท้าย

 สุดท้าย ให้บันทึกเอกสารที่ผสานโดยเปิดใช้งานคุณลักษณะใช้สไตล์ปลายทางโดยใช้`Save` วิธีการของ`Document` ชั้นเรียน

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับใช้สไตล์ปลายทางโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดแบบเต็มสำหรับฟีเจอร์ "ใช้สไตล์ปลายทาง" ใน C# โดยใช้ Aspose.Words สำหรับ .NET:

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// ผนวกเอกสารต้นทางโดยใช้สไตล์ของเอกสารปลายทาง
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

แค่นั้นแหละ! คุณได้ปรับใช้ฟีเจอร์ใช้สไตล์ปลายทางโดยใช้ Aspose.Words สำหรับ .NET สำเร็จแล้ว เอกสารขั้นสุดท้ายจะมีเนื้อหาที่ผสานเข้ากับสไตล์ของเอกสารปลายทางที่ใช้