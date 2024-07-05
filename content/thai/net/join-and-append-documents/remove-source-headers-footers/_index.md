---
title: ลบส่วนท้ายของส่วนหัวแหล่งที่มา
linktitle: ลบส่วนท้ายของส่วนหัวแหล่งที่มา
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีลบส่วนหัวและส่วนท้ายขณะเข้าร่วมและต่อท้ายเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/remove-source-headers-footers/
---

บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้ฟีเจอร์ Remove Source Headers Footers ของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเข้าร่วมและต่อท้ายเอกสาร Word ในขณะที่ลบส่วนหัวและส่วนท้ายออกจากเอกสารต้นฉบับ

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

## ขั้นตอนที่ 3: ลบส่วนหัวและส่วนท้ายออกจากส่วนเอกสารต้นฉบับ

 หากต้องการลบส่วนหัวและส่วนท้ายออกจากแต่ละส่วนในเอกสารต้นฉบับ คุณสามารถวนซ้ำส่วนต่างๆ ได้โดยใช้`foreach` วนซ้ำและโทรไปที่`ClearHeadersFooters` วิธี.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## ขั้นตอนที่ 4: ปิดใช้งานการตั้งค่า "LinkToPrevious" สำหรับ HeadersFooters

แม้ว่าหลังจากการล้างส่วนหัวและส่วนท้ายจากเอกสารต้นฉบับแล้ว ยังมีความเป็นไปได้ที่การตั้งค่า "LinkToPrevious" สำหรับ`HeadersFooters` ยังสามารถตั้งค่าได้ เพื่อหลีกเลี่ยงพฤติกรรมนี้ คุณต้องตั้งค่าอย่างชัดเจน`false` สำหรับภาคแรก`HeadersFooters` คุณสมบัติ.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## ขั้นตอนที่ 5: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ตอนนี้คุณสามารถผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางได้โดยใช้`AppendDocument` วิธีการของ`Document` ระดับ. ที่`ImportFormatMode.KeepSourceFormatting` พารามิเตอร์ช่วยให้มั่นใจได้ว่าการจัดรูปแบบต้นฉบับจะถูกรักษาไว้ระหว่างการดำเนินการผนวก

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 6: บันทึกเอกสารขั้นสุดท้าย

 สุดท้าย ให้บันทึกเอกสารที่ผสานโดยเปิดใช้งานคุณลักษณะ Remove Source Headers Footers โดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการลบส่วนท้ายของส่วนหัวแหล่งที่มาโดยใช้ Aspose.Words สำหรับ .NET 

นี่คือซอร์สโค้ดแบบเต็มสำหรับฟีเจอร์ "Remove Source Headers Footers" ใน C# โดยใช้ Aspose.Words สำหรับ .NET:


```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// ลบส่วนหัวและส่วนท้ายออกจากแต่ละส่วนในเอกสารต้นฉบับ
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// แม้ว่าส่วนหัวและส่วนท้ายจะถูกล้างออกจากเอกสารต้นฉบับแล้ว การตั้งค่า "LinkToPrevious"
	// สำหรับ HeadersFooters ยังสามารถตั้งค่าได้ ซึ่งจะทำให้ส่วนหัวและส่วนท้ายต่อจากปลายทาง
	// เอกสาร. ควรตั้งค่าเป็นเท็จเพื่อหลีกเลี่ยงพฤติกรรมนี้
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
แค่นั้นแหละ! คุณได้นำคุณลักษณะ Remove Source Headers Footers ไปใช้เรียบร้อยแล้วโดยใช้ Aspose.Words for .NET เอกสารขั้นสุดท้ายจะมีเนื้อหาที่ผสานโดยนำส่วนหัวและส่วนท้ายออกจากเอกสารต้นฉบับ