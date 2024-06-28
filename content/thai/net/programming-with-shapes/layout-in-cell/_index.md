---
title: เค้าโครงในเซลล์
linktitle: เค้าโครงในเซลล์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีการจัดวางรูปร่างภายในเซลล์ตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-shapes/layout-in-cell/
---

บทช่วยสอนนี้จะอธิบายวิธีจัดวางรูปร่างภายในเซลล์ตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการปรับคุณสมบัติรูปร่างและใช้ตัวเลือกเค้าโครง คุณสามารถควบคุมตำแหน่งและลักษณะของรูปร่างภายในเซลล์ได้

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่คุณต้องการบันทึกเอกสาร

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารใหม่และ DocumentBuilder
 สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`DocumentBuilder` คัดค้านการทำงานกับเอกสาร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: สร้างตาราง
 ใช้`StartTable`, `EndTable`, `InsertCell` , และ`Write` วิธีการของ`DocumentBuilder`วัตถุเพื่อสร้างตาราง ตั้งค่ากฎความสูงและความสูงของแถวที่ต้องการโดยใช้`RowFormat` คุณสมบัติ.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## ขั้นตอนที่ 4: สร้างและจัดรูปแบบรูปร่าง
 สร้างก`Shape` วัตถุและกำหนดค่าคุณสมบัติเพื่อกำหนดลายน้ำ กำหนดรูปร่างที่จะจัดวางภายในเซลล์โดยใช้`IsLayoutInCell` คุณสมบัติ.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true,
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## ขั้นตอนที่ 5: ปรับแต่งรูปร่าง
 ปรับแต่งลักษณะที่ปรากฏและข้อความของรูปร่างลายน้ำโดยการตั้งค่าคุณสมบัติเช่น`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`ฯลฯ

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## ขั้นตอนที่ 6: แทรกรูปร่างลงในเอกสาร
 แทรกรูปร่างลายน้ำลงในเอกสารโดยใช้`InsertNode` วิธีการของ`DocumentBuilder` วัตถุ วัตถุ วางตำแหน่งรูปร่างโดยใช้`MoveTo` วิธีการวางหลังจากการรันครั้งสุดท้ายในเอกสาร

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithShapes.LayoutInCell.docx"

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับเค้าโครงในเซลล์โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.RowFormat.Height = 100;
	builder.RowFormat.HeightRule = HeightRule.Exactly;
	for (int i = 0; i < 31; i++)
	{
		if (i != 0 && i % 7 == 0) builder.EndRow();
		builder.InsertCell();
		builder.Write("Cell contents");
	}
	builder.EndTable();
	Shape watermark = new Shape(doc, ShapeType.TextPlainText)
	{
		RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
		RelativeVerticalPosition = RelativeVerticalPosition.Page,
		IsLayoutInCell = true, // แสดงรูปร่างภายนอกเซลล์ตารางหากจะวางลงในเซลล์
		Width = 300,
		Height = 70,
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center,
		Rotation = -40
	};
	watermark.FillColor = Color.Gray;
	watermark.StrokeColor = Color.Gray;
	watermark.TextPath.Text = "watermarkText";
	watermark.TextPath.FontFamily = "Arial";
	watermark.Name = $"WaterMark_{Guid.NewGuid()}";
	watermark.WrapType = WrapType.None;
	Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
	builder.MoveTo(run);
	builder.InsertNode(watermark);
	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
	doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

แค่นั้นแหละ! คุณได้วางรูปร่างภายในเซลล์ตารางในเอกสาร Word เรียบร้อยแล้วโดยใช้ Aspose.Words สำหรับ .NET