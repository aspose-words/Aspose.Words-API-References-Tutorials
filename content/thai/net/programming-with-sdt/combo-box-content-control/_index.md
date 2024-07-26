---
title: การควบคุมเนื้อหากล่องคำสั่งผสม
linktitle: การควบคุมเนื้อหากล่องคำสั่งผสม
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้าง Combo Box Content Control ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-sdt/combo-box-content-control/
---

บทช่วยสอนนี้จะอธิบายวิธีสร้างการควบคุมเนื้อหา Combo Box ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ตัวควบคุมเนื้อหากล่องคำสั่งผสมอนุญาตให้ผู้ใช้เลือกรายการจากรายการดรอปดาวน์

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
 สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`StructuredDocumentTag` เพื่อแสดงถึงการควบคุมเนื้อหาของกล่องคำสั่งผสม ระบุ`SdtType.ComboBox` เป็นประเภทและ`MarkupLevel.Block` เป็นระดับมาร์กอัปเพื่อสร้างกล่องคำสั่งผสมระดับบล็อก

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## ขั้นตอนที่ 3: เพิ่มรายการลงใน Combo Box
 เพิ่มรายการลงในกล่องคำสั่งผสมโดยใช้การ`ListItems` ทรัพย์สินของ`StructuredDocumentTag` - แต่ละรายการจะแสดงด้วย`SdtListItem` วัตถุซึ่งรับข้อความที่แสดงและค่า ในตัวอย่างนี้ เราเพิ่มสามรายการลงในกล่องคำสั่งผสม

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## ขั้นตอนที่ 4: ผนวก StructuredDocumentTag เข้ากับเอกสาร
 ผนวกตัวควบคุมเนื้อหากล่องคำสั่งผสมเข้ากับเนื้อความของเอกสารโดยใช้`AppendChild` วิธีการของเนื้อหาส่วนแรกของเอกสาร

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## ขั้นตอนที่ 5: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithSdt.ComboBoxContentControl.docx"

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการควบคุมเนื้อหา Combo Box โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

แค่นั้นแหละ! คุณสร้าง Combo Box Content Control ในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words for .NET