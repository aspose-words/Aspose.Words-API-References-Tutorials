---
title: อัปเดตเค้าโครงหน้า
linktitle: อัปเดตเค้าโครงหน้า
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีอัปเดตเค้าโครงหน้าเมื่อเข้าร่วมและต่อท้ายเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/update-page-layout/
---

บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้คุณสมบัติอัปเดตเค้าโครงหน้าของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้แน่ใจว่าเค้าโครงหน้าได้รับการอัปเดตอย่างถูกต้องเมื่อเข้าร่วมและต่อท้ายเอกสาร Word

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

## ขั้นตอนที่ 3: อัปเดตเค้าโครงหน้าสำหรับเอกสารปลายทาง

 เพื่อให้แน่ใจว่าเค้าโครงหน้าได้รับการอัปเดตอย่างถูกต้องก่อนที่จะผนวกเอกสารต้นฉบับ คุณสามารถเรียก`UpdatePageLayout` วิธีการในเอกสารปลายทาง

```csharp
dstDoc.UpdatePageLayout();
```

## ขั้นตอนที่ 4: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ตอนนี้คุณสามารถผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางได้โดยใช้`AppendDocument` วิธีการของ`Document` ระดับ. ที่`ImportFormatMode.KeepSourceFormatting` พารามิเตอร์ช่วยให้มั่นใจได้ว่าการจัดรูปแบบต้นฉบับจะถูกรักษาไว้ระหว่างการดำเนินการผนวก

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 5: อัปเดตเค้าโครงหน้าอีกครั้ง

 หลังจากผนวกเอกสารต้นฉบับแล้ว คุณจะต้องเรียกไฟล์`UpdatePageLayout`ในเอกสารปลายทางอีกครั้งเพื่อให้แน่ใจว่าการเปลี่ยนแปลงใด ๆ ที่เกิดขึ้นหลังจากการดำเนินการผนวกจะสะท้อนให้เห็นในเอาต์พุตที่แสดงผล

```csharp
dstDoc.UpdatePageLayout();
```

## ขั้นตอนที่ 6: บันทึกเอกสารขั้นสุดท้าย

 สุดท้าย ให้บันทึกเอกสารที่ผสานโดยเปิดใช้งานคุณลักษณะอัปเดตเค้าโครงหน้ากระดาษโดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับอัปเดตเค้าโครงหน้าโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดแบบเต็มสำหรับฟีเจอร์ "อัปเดตเค้าโครงหน้า" ใน C# โดยใช้ Aspose.Words สำหรับ .NET:

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// หากเอกสารปลายทางแสดงเป็น PDF รูปภาพ ฯลฯ
	// หรือ UpdatePageLayout ถูกเรียกก่อนเอกสารต้นฉบับ จะถูกต่อท้าย,
	// ดังนั้นการเปลี่ยนแปลงใด ๆ ที่เกิดขึ้นหลังจากนั้นจะไม่สะท้อนให้เห็นในเอาท์พุตที่เรนเดอร์
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// หากต้องการอัปเดตการเปลี่ยนแปลงเป็นเอาต์พุตที่แสดงผล ต้องเรียก UpdatePageLayout อีกครั้ง
	// หากไม่ถูกเรียกอีกครั้ง เอกสารที่ต่อท้ายจะไม่ปรากฏในเอาต์พุตของการเรนเดอร์ครั้งถัดไป
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

แค่นั้นแหละ! คุณได้ปรับใช้ฟีเจอร์อัปเดตเค้าโครงหน้าโดยใช้ Aspose.Words สำหรับ .NET สำเร็จแล้ว เอกสารขั้นสุดท้ายจะมีเนื้อหาที่ผสานและมีการอัปเดตเค้าโครงหน้าอย่างถูกต้อง