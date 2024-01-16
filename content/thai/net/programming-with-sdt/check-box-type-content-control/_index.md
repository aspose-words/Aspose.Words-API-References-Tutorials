---
title: การควบคุมเนื้อหาประเภทกล่องกาเครื่องหมาย
linktitle: การควบคุมเนื้อหาประเภทกล่องกาเครื่องหมาย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างการควบคุมเนื้อหาประเภทกล่องกาเครื่องหมายในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-sdt/check-box-type-content-control/
---

บทช่วยสอนนี้จะอธิบายวิธีสร้างการควบคุมเนื้อหาประเภทกล่องกาเครื่องหมายในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ตัวควบคุมเนื้อหากล่องกาเครื่องหมายอนุญาตให้ผู้ใช้เลือกหรือล้างกล่องกาเครื่องหมายภายในเอกสาร

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่คุณต้องการบันทึกเอกสาร

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารและ DocumentBuilder
 สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`DocumentBuilder` เพื่อสร้างเนื้อหาของเอกสาร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: เพิ่มการควบคุมเนื้อหาประเภทกล่องกาเครื่องหมาย
 สร้างก`StructuredDocumentTag` กับ`SdtType.Checkbox` เพื่อแสดงการควบคุมเนื้อหากล่องกาเครื่องหมาย ระบุ`MarkupLevel.Inline` เพื่อวางไว้ในข้อความ

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithSdt.CheckBoxTypeContentControl.docx"

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### ตัวอย่างซอร์สโค้ดสำหรับการควบคุมเนื้อหาประเภทกล่องกาเครื่องหมายโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

แค่นั้นแหละ! คุณได้สร้างการควบคุมเนื้อหาประเภทกล่องกาเครื่องหมายในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว