---
title: เก็บหมายเลขแหล่งที่มา
linktitle: เก็บหมายเลขแหล่งที่มา
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีนำเข้าเอกสารในขณะที่รักษาการจัดรูปแบบโดยใช้ Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด
type: docs
weight: 10
url: /th/net/join-and-append-documents/keep-source-numbering/
---
## การแนะนำ

 เมื่อทำงานกับ Aspose.Words สำหรับ .NET การนำเข้าเอกสารจากแหล่งหนึ่งไปยังอีกแหล่งหนึ่งโดยที่ยังคงการจัดรูปแบบไว้สามารถจัดการได้อย่างมีประสิทธิภาพโดยใช้`NodeImporter` ระดับ. บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
-  ติดตั้ง Aspose.Words สำหรับ .NET แล้ว ถ้าไม่เช่นนั้นให้ดาวน์โหลดจาก[ที่นี่](https://releases.aspose.com/words/net/).
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# และ .NET

## นำเข้าเนมสเปซ

ขั้นแรก ให้รวมเนมสเปซที่จำเป็นในโครงการของคุณ:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ใน Visual Studio และติดตั้ง Aspose.Words ผ่าน NuGet Package Manager

## ขั้นตอนที่ 2: เริ่มต้นเอกสาร
สร้างอินสแตนซ์ของแหล่งที่มา (`srcDoc`) และปลายทาง (`dstDoc`) เอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการนำเข้า
ตั้งค่าตัวเลือกการนำเข้าเพื่อรักษาการจัดรูปแบบต้นฉบับ รวมถึงย่อหน้าที่มีหมายเลขกำกับ

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## ขั้นตอนที่ 4: นำเข้าย่อหน้า
วนซ้ำแต่ละย่อหน้าในเอกสารต้นฉบับและนำเข้าไปยังเอกสารปลายทาง

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## ขั้นตอนที่ 5: บันทึกเอกสาร
บันทึกเอกสารที่ผสานไปยังตำแหน่งที่คุณต้องการ

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## บทสรุป

 โดยสรุป การใช้ Aspose.Words สำหรับ .NET เพื่อนำเข้าเอกสารในขณะที่ยังคงการจัดรูปแบบไว้นั้นตรงไปตรงมากับ`NodeImporter` ระดับ. วิธีการนี้ช่วยให้แน่ใจว่าเอกสารของคุณคงรูปลักษณ์และโครงสร้างดั้งเดิมไว้ได้อย่างราบรื่น

## คำถามที่พบบ่อย

### ฉันสามารถนำเข้าเอกสารที่มีรูปแบบการจัดรูปแบบที่แตกต่างกันได้หรือไม่
 ใช่`NodeImporter` คลาสรองรับการนำเข้าเอกสารที่มีสไตล์การจัดรูปแบบที่หลากหลาย

### จะเกิดอะไรขึ้นหากเอกสารของฉันมีตารางและรูปภาพที่ซับซ้อน
Aspose.Words สำหรับ .NET จัดการโครงสร้างที่ซับซ้อน เช่น ตารางและรูปภาพระหว่างการดำเนินการนำเข้า

### Aspose.Words เข้ากันได้กับ .NET ทุกเวอร์ชันหรือไม่
Aspose.Words รองรับเวอร์ชัน .NET Framework และ .NET Core เพื่อการบูรณาการที่ราบรื่น

### ฉันจะจัดการกับข้อผิดพลาดระหว่างการนำเข้าเอกสารได้อย่างไร
ใช้บล็อก try-catch เพื่อจัดการกับข้อยกเว้นที่อาจเกิดขึ้นระหว่างกระบวนการนำเข้า

### ฉันจะหาเอกสารรายละเอียดเพิ่มเติมเกี่ยวกับ Aspose.Words สำหรับ .NET ได้ที่ไหน
 เยี่ยมชม[เอกสารประกอบ](https://reference.aspose.com/words/net/) สำหรับคำแนะนำที่ครอบคลุมและการอ้างอิง API
