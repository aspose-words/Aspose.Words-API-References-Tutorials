---
title: ช่วงแท็กเอกสารที่มีโครงสร้างเริ่มต้นการแมป XML
linktitle: ช่วงแท็กเอกสารที่มีโครงสร้างเริ่มต้นการแมป XML
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตั้งค่าการแมป XML สำหรับช่วงแท็กเอกสารที่มีโครงสร้างเริ่มต้นในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

บทช่วยสอนนี้จะอธิบายวิธีตั้งค่าการแมป XML สำหรับช่วงแท็กเอกสารที่มีโครงสร้างเริ่มต้นในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET การแมป XML ช่วยให้คุณสามารถแสดงส่วนเฉพาะของแหล่งข้อมูล XML ภายในตัวควบคุมเนื้อหา

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารและสร้างส่วน XML
 โหลดเอกสาร Word โดยใช้ไฟล์`Document`Constructor โดยส่งเส้นทางไปยังเอกสารเป็นพารามิเตอร์ สร้างส่วน XML ที่มีข้อมูลที่คุณต้องการแสดงภายในแท็กเอกสารที่มีโครงสร้าง

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## ขั้นตอนที่ 3: ตั้งค่าการแมป XML สำหรับแท็กเอกสารที่มีโครงสร้าง
ดึงข้อมูลช่วงแท็กเอกสารที่มีโครงสร้างเริ่มต้นจากเอกสาร จากนั้น ตั้งค่าการแมป XML สำหรับแท็กเอกสารที่มีโครงสร้างเพื่อแสดงส่วนเฉพาะของส่วน XML ที่กำหนดเองโดยใช้นิพจน์ XPath

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
 บันทึกเอกสารที่แก้ไขไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx"

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับช่วงแท็กเอกสารที่มีโครงสร้างเริ่มการแมป Xml โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// สร้างส่วน XML ที่มีข้อมูลและเพิ่มลงในคอลเลกชัน CustomXmlPart ของเอกสาร
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// สร้าง StructuredDocumentTag ที่จะแสดงเนื้อหาของ CustomXmlPart ของเราในเอกสาร
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// หากเราตั้งค่าการแมปสำหรับ StructuredDocumentTag ของเรา
	//โดยจะแสดงเฉพาะส่วนหนึ่งของ CustomXmlPart ที่ XPath ชี้ไป
	// XPath นี้จะชี้ไปที่เนื้อหาองค์ประกอบ "<text>" ที่สองขององค์ประกอบ "<root>" แรกของ CustomXmlPart ของเรา
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

แค่นั้นแหละ! คุณได้ตั้งค่าการแมป XML สำหรับช่วงแท็กเอกสารที่มีโครงสร้างเริ่มต้นในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว