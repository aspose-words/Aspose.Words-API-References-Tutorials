---
title: แก้ไขการควบคุมเนื้อหา
linktitle: แก้ไขการควบคุมเนื้อหา
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแก้ไขข้อความ รายการดรอปดาวน์ และรูปภาพภายในตัวควบคุมเนื้อหาในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-sdt/modify-content-controls/
---

บทช่วยสอนนี้จะอธิบายวิธีแก้ไขการควบคุมเนื้อหาประเภทต่างๆ ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถอัปเดตข้อความ ค่าที่เลือกของรายการดรอปดาวน์ หรือแทนที่รูปภาพภายในตัวควบคุมเนื้อหาได้

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารและวนซ้ำการควบคุมเนื้อหา
 โหลดเอกสาร Word โดยใช้ไฟล์`Document` Constructor โดยส่งเส้นทางไปยังเอกสารเป็นพารามิเตอร์ วนซ้ำแท็กเอกสารที่มีโครงสร้างทั้งหมดในเอกสารโดยใช้`foreach` วนซ้ำ

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // ดำเนินการตามประเภทของการควบคุมเนื้อหา
}
```

## ขั้นตอนที่ 3: แก้ไขการควบคุมเนื้อหาข้อความธรรมดา
 สำหรับการควบคุมเนื้อหาประเภท`SdtType.PlainText`ลบรายการย่อยที่มีอยู่ทั้งหมด สร้างย่อหน้าใหม่ และเพิ่มข้อความที่ต้องการต่อท้าย

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## ขั้นตอนที่ 4: แก้ไขการควบคุมเนื้อหารายการแบบหล่นลง
 สำหรับการควบคุมเนื้อหาประเภท`SdtType.DropDownList` ให้อัปเดตค่าที่เลือกโดยตั้งค่าเป็นค่าเฉพาะ`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## ขั้นตอนที่ 5: แก้ไขการควบคุมเนื้อหารูปภาพ
 สำหรับการควบคุมเนื้อหาประเภท`SdtType.Picture`ให้ดึงรูปร่างภายในตัวควบคุมเนื้อหาและแทนที่รูปภาพด้วยรูปร่างใหม่

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไข
 บันทึกเอกสารที่แก้ไขไปยังไดเร็กทอรีที่ระบุโดยใช้`Save`วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithSdt.ModifyContentControls.docx"

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับแก้ไขการควบคุมเนื้อหาโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

แค่นั้นแหละ! คุณได้แก้ไขการควบคุมเนื้อหาประเภทต่างๆ ในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET