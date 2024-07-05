---
title: พฤติกรรมสไตล์สมาร์ท
linktitle: พฤติกรรมสไตล์สมาร์ท
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรักษาพฤติกรรมสไตล์อัจฉริยะเมื่อเข้าร่วมและต่อท้ายเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/smart-style-behavior/
---

บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้คุณสมบัติ Smart Style Behavior ของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเข้าร่วมและต่อท้ายเอกสาร Word ในขณะที่ยังคงลักษณะการทำงานของสไตล์ที่ชาญฉลาด

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

## ขั้นตอนที่ 3: แทรกตัวแบ่งหน้าในเอกสารปลายทาง

 เพื่อให้แน่ใจว่าเนื้อหาที่ต่อท้ายปรากฏบนหน้าใหม่ในเอกสารปลายทาง คุณสามารถแทรกตัวแบ่งหน้าได้โดยใช้`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## ขั้นตอนที่ 4: ตั้งค่าตัวเลือกพฤติกรรมสไตล์อัจฉริยะ

หากต้องการเปิดใช้งานลักษณะการทำงานสไตล์อัจฉริยะระหว่างการดำเนินการผนวก คุณต้องสร้างอินสแตนซ์ของ`ImportFormatOptions` และตั้งค่า`SmartStyleBehavior`ทรัพย์สินเพื่อ`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## ขั้นตอนที่ 5: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ตอนนี้คุณสามารถผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางได้โดยใช้`InsertDocument` วิธีการของ`DocumentBuilder` ระดับ. ใช้`ImportFormatMode.UseDestinationStyles` พารามิเตอร์และผ่าน`ImportFormatOptions` วัตถุเพื่อรักษาพฤติกรรมสไตล์สมาร์ท

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## ขั้นตอนที่ 6: บันทึกเอกสารขั้นสุดท้าย

 สุดท้าย ให้บันทึกเอกสารที่ผสานโดยเปิดใช้งานคุณสมบัติ Smart Style Behavior โดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับพฤติกรรมสไตล์อัจฉริยะโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดแบบเต็มสำหรับฟีเจอร์ "Smart Style Behavior" ใน C# โดยใช้ Aspose.Words สำหรับ .NET:
 
```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

แค่นั้นแหละ! คุณได้ปรับใช้ฟีเจอร์ Smart Style Behavior โดยใช้ Aspose.Words สำหรับ .NET สำเร็จแล้ว เอกสารขั้นสุดท้ายจะมีเนื้อหาที่ผสานโดยคงลักษณะการทำงานสไตล์อัจฉริยะไว้