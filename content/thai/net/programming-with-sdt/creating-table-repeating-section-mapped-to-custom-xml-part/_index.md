---
title: การสร้างส่วนการทำซ้ำตารางที่แมปกับส่วน Xml ที่กำหนดเอง
linktitle: การสร้างส่วนการทำซ้ำตารางที่แมปกับส่วน Xml ที่กำหนดเอง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างตารางด้วยส่วนที่ซ้ำกันซึ่งแมปกับ CustomXmlPart ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

บทช่วยสอนนี้สาธิตวิธีการสร้างตารางที่มีส่วนที่ซ้ำกันซึ่งแมปกับส่วน Xml แบบกำหนดเองในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ส่วนการทำซ้ำช่วยให้คุณสามารถเพิ่มแถวแบบไดนามิกตามข้อมูล XML ที่จัดเก็บไว้ในส่วน Xml แบบกำหนดเอง

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

## ขั้นตอนที่ 3: เพิ่มข้อมูล XML แบบกำหนดเองลงใน CustomXmlPart
 สร้างก`CustomXmlPart` และเพิ่มข้อมูล XML ที่กำหนดเองลงไป ในตัวอย่างนี้ เราสร้างสตริง XML ที่แสดงถึงคอลเลกชั่นหนังสือที่มีชื่อและผู้แต่ง

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## ขั้นตอนที่ 4: สร้างตารางและโครงสร้างตาราง
เริ่มสร้างตารางโดยใช้`StartTable` วิธีการของ`DocumentBuilder` - เพิ่มเซลล์ตารางและเนื้อหาโดยใช้`InsertCell`และ`Write` วิธีการ

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## ขั้นตอนที่ 5: สร้างส่วนที่ทำซ้ำซึ่งแมปกับ XML แบบกำหนดเอง
 สร้างก`StructuredDocumentTag` กับ`SdtType.RepeatingSection` เพื่อเป็นตัวแทนของส่วนที่ซ้ำกัน ตั้งค่าการแมป XML สำหรับส่วนที่ทำซ้ำโดยใช้`SetMapping` วิธีการของ`XmlMapping` คุณสมบัติ. ในตัวอย่างนี้ เราแมปส่วนที่ทำซ้ำกับ`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## ขั้นตอนที่ 6: สร้างรายการส่วนที่ทำซ้ำและเพิ่มเซลล์
 สร้างก`StructuredDocumentTag` กับ`SdtType.RepeatingSectionItem` เพื่อแสดงรายการส่วนที่ซ้ำกัน ผนวกเป็นรายการย่อยในส่วนการทำซ้ำ

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 สร้างก`Row` เพื่อเป็นตัวแทนของแต่ละรายการในส่วนการทำซ้ำและผนวกเข้ากับรายการส่วนการทำซ้ำ

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## ขั้นตอนที่ 7: เพิ่มการควบคุมเนื้อหาภายในส่วนการทำซ้ำ
 สร้าง`StructuredDocumentTag` วัตถุด้วย`SdtType.PlainText`

  เพื่อแสดงการควบคุมเนื้อหาชื่อเรื่องและผู้แต่ง ตั้งค่าการแมป XML สำหรับการควบคุมเนื้อหาแต่ละรายการโดยใช้`SetMapping` วิธีการของ`XmlMapping` คุณสมบัติ. ในตัวอย่างนี้ เราแมปตัวควบคุมชื่อเรื่องกับ`/books[1]/book[1]/title[1]` และผู้เขียนควบคุมการ`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร
 บันทึกเอกสารที่แก้ไขไปยังไดเร็กทอรีที่ระบุโดยใช้`Save`วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx"

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการสร้างส่วนที่ทำซ้ำตารางที่แมปกับส่วน Xml แบบกำหนดเองโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

แค่นั้นแหละ! คุณได้สร้างตารางโดยมีส่วนการทำซ้ำที่แมปกับ CustomXmlPart ในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET สำเร็จแล้ว