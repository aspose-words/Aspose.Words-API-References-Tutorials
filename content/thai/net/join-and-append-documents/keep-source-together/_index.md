---
title: เก็บแหล่งที่มาไว้ด้วยกัน
linktitle: เก็บแหล่งที่มาไว้ด้วยกัน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้ Aspose.Words สำหรับ .NET เพื่อเข้าร่วมและผนวกเอกสาร Word ในขณะที่ยังคงรักษาเนื้อหาต้นฉบับไว้พร้อมกับเอกสารปลายทาง
type: docs
weight: 10
url: /th/net/join-and-append-documents/keep-source-together/
---

บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้ฟีเจอร์ Keep Source Together ของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเข้าร่วมและผนวกเอกสาร Word หลายชุดโดยยังคงรักษาเนื้อหาของเอกสารต้นทางร่วมกับเนื้อหาของเอกสารปลายทาง 

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## ขั้นตอนที่ 3: ตั้งค่าเอกสารต้นฉบับให้ปรากฏหลังจากเนื้อหาของเอกสารปลายทาง

 เพื่อให้แน่ใจว่าเอกสารต้นทางปรากฏขึ้นทันทีหลังจากเนื้อหาของเอกสารปลายทาง คุณต้องตั้งค่า`SectionStart` คุณสมบัติของส่วนแรกในเอกสารต้นฉบับถึง`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ขั้นตอนที่ 4: ตั้งค่าการจัดรูปแบบย่อหน้า "Keep with Next" สำหรับเอกสารต้นฉบับ

 หากต้องการเก็บย่อหน้าในเอกสารต้นฉบับไว้ด้วยกัน คุณสามารถวนซ้ำแต่ละย่อหน้าในเอกสารและตั้งค่า`KeepWithNext`ทรัพย์สินเพื่อ`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## ขั้นตอนที่ 5: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ตอนนี้คุณสามารถผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางได้โดยใช้`AppendDocument` วิธีการของ`Document` ชั้นเรียน ที่`ImportFormatMode.KeepSourceFormatting` พารามิเตอร์ช่วยให้แน่ใจว่าการจัดรูปแบบต้นฉบับจะถูกรักษาไว้ระหว่างการดำเนินการผนวก

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ขั้นตอนที่ 6: บันทึกเอกสารขั้นสุดท้าย

 สุดท้าย ให้บันทึกเอกสารที่ผสานด้วยคุณลักษณะ "Keep Source Together" ที่เปิดใช้งานโดยใช้`Save` วิธีการของ`Document` ชั้นเรียน

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Keep Source Together โดยใช้ Aspose.Words สำหรับ .NET 

นี่คือซอร์สโค้ดแบบเต็มสำหรับฟีเจอร์ "Keep Source Together" ใน C# โดยใช้ Aspose.Words สำหรับ .NET:


```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// ตั้งค่าเอกสารต้นทางให้ปรากฏต่อจากเนื้อหาของเอกสารปลายทาง
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

แค่นั้นแหละ! คุณใช้งานฟีเจอร์ Keep Source Together สำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET เอกสารขั้นสุดท้ายจะมีเนื้อหาที่ผสานกับย่อหน้าในเอกสารต้นฉบับที่เก็บไว้ด้วยกัน