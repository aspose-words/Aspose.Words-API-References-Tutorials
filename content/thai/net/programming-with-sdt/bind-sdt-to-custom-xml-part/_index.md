---
title: ผูก SDT กับส่วน Xml แบบกำหนดเอง
linktitle: ผูก SDT กับส่วน Xml แบบกำหนดเอง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผูก SDT กับส่วน Xml แบบกำหนดเองโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

บทช่วยสอนนี้สาธิตวิธีผูกแท็กเอกสารที่มีโครงสร้าง (SDT) กับส่วน Xml แบบกำหนดเองโดยใช้ Aspose.Words สำหรับ .NET SDT ช่วยให้คุณสามารถเพิ่มการควบคุมเนื้อหาที่มีโครงสร้างลงในเอกสาร Word และ CustomXmlParts มีวิธีในการจัดเก็บข้อมูล XML แบบกำหนดเองที่เกี่ยวข้องกับเอกสาร

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และ XML

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"`ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่คุณต้องการบันทึกเอกสาร

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารและ CustomXmlPart
 สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`CustomXmlPart` เพื่อจัดเก็บข้อมูล XML ที่กำหนดเอง XML ที่กำหนดเองควรอยู่ในรูปแบบ XML ที่ถูกต้อง ในตัวอย่างนี้ เราใช้สตริง XML แบบธรรมดา`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## ขั้นตอนที่ 3: เพิ่ม StructuredDocumentTag (SDT) ลงในเอกสาร
 เพิ่ม`StructuredDocumentTag` ไปยังเอกสารเพื่อใช้เป็นตัวควบคุมเนื้อหา ระบุ`SdtType` เช่น`PlainText` และ`MarkupLevel` เช่น`Block` เพื่อสร้าง SDT ระดับบล็อก

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## ขั้นตอนที่ 4: ตั้งค่าการแมป XML สำหรับ SDT
 แมป SDT กับ`CustomXmlPart` โดยใช้`SetMapping` วิธีการของ`XmlMapping` คุณสมบัติ. ระบุ`CustomXmlPart` นิพจน์ XPath เพื่อค้นหาโหนด XML ที่ต้องการ และคำนำหน้าเนมสเปซ หากจำเป็น ในตัวอย่างนี้ เราแมป SDT กับ`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## ขั้นตอนที่ 5: บันทึกเอกสาร
 บันทึกเอกสารที่แก้ไขไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithSdt.BindSDTtoCustomXmlPart.doc"

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Bind Sd Tto Custom Xml Part โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

แค่นั้นแหละ! คุณได้ผูก SDT กับ CustomXmlPart ในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET