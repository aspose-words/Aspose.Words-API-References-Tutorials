---
title: การควบคุมเนื้อหากล่องข้อความแบบ Rich
linktitle: การควบคุมเนื้อหากล่องข้อความแบบ Rich
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างการควบคุมเนื้อหากล่องข้อความแบบ Rich Text ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ซึ่งเปิดใช้งานการจัดรูปแบบและสไตล์ข้อความ
type: docs
weight: 10
url: /th/net/programming-with-sdt/rich-text-box-content-control/
---

บทช่วยสอนนี้สาธิตวิธีการสร้างตัวควบคุมเนื้อหากล่องข้อความแบบ Rich Text ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ตัวควบคุมเนื้อหาของกล่องข้อความ Rich ช่วยให้ผู้ใช้สามารถป้อนและจัดรูปแบบข้อความด้วยสไตล์และตัวเลือกการจัดรูปแบบต่างๆ

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่คุณต้องการบันทึกเอกสาร

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารและ StructuredDocumentTag
 สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`StructuredDocumentTag` เพื่อแสดงการควบคุมเนื้อหาของกล่องข้อความแบบ Rich ระบุ`SdtType.RichText` เป็นประเภทและ`MarkupLevel.Block` เป็นระดับมาร์กอัปเพื่อสร้างกล่องข้อความที่หลากหลายระดับบล็อก

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## ขั้นตอนที่ 3: สร้างและจัดรูปแบบเนื้อหา Rich Text
สร้างย่อหน้าและเรียกใช้เพื่อแสดงเนื้อหา Rich Text ตั้งค่าตัวเลือกข้อความและการจัดรูปแบบ เช่น สี แบบอักษร ฯลฯ

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## ขั้นตอนที่ 4: เพิ่มเนื้อหา Rich Text ลงในการควบคุมเนื้อหา
เพิ่มย่อหน้าที่มีเนื้อหา Rich Text ลงใน`ChildNodes` คอลเลกชันของการควบคุมเนื้อหากล่องข้อความแบบ Rich

```csharp
sdtRichText.ChildNodes.Add(para);
```

## ขั้นตอนที่ 5: ผนวกการควบคุมเนื้อหาเข้ากับเอกสาร
 ผนวกตัวควบคุมเนื้อหากล่องข้อความ rich text เข้ากับเนื้อความของเอกสารโดยใช้`AppendChild` วิธีการของเนื้อหาส่วนแรกของเอกสาร

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## ขั้นตอนที่ 6: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithSdt.RichTextBoxContentControl.docx"

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการควบคุมเนื้อหากล่องข้อความ Rich โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

แค่นั้นแหละ! คุณได้สร้างตัวควบคุมเนื้อหากล่องข้อความ rich text ในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว