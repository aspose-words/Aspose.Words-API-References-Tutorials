---
title: การสร้างส่วนการทำซ้ำตารางที่แมปกับส่วน Xml ที่กำหนดเอง
linktitle: การสร้างส่วนการทำซ้ำตารางที่แมปกับส่วน Xml ที่กำหนดเอง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างตารางด้วยส่วนที่ซ้ำกันซึ่งแมปกับ CustomXmlPart ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---
## การแนะนำ

ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการสร้างตารางที่มีส่วนซ้ำซึ่งแมปกับส่วน XML แบบกำหนดเองโดยใช้ Aspose.Words สำหรับ .NET สิ่งนี้มีประโยชน์อย่างยิ่งสำหรับการสร้างเอกสารแบบไดนามิกตามข้อมูลที่มีโครงสร้าง

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์กำหนด](https://releases.aspose.com/words/net/).
2. ความเข้าใจพื้นฐานเกี่ยวกับ C# และ XML

## นำเข้าเนมสเปซ

ตรวจสอบให้แน่ใจว่าได้รวมเนมสเปซที่จำเป็นในโครงการของคุณ:

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Tables;
```

## ขั้นตอนที่ 1: เริ่มต้นเอกสารและ DocumentBuilder

 ขั้นแรก สร้างเอกสารใหม่และเริ่มต้น`DocumentBuilder`-

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: เพิ่มส่วน XML ที่กำหนดเอง

เพิ่มส่วน XML แบบกำหนดเองลงในเอกสาร XML นี้มีข้อมูลที่เราต้องการแมปกับตารางของเรา:

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
    "<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
    "<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
    "<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## ขั้นตอนที่ 3: สร้างโครงสร้างตาราง

 ต่อไปให้ใช้`DocumentBuilder` เพื่อสร้างส่วนหัวของตาราง:

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## ขั้นตอนที่ 4: สร้างส่วนที่ทำซ้ำ

 สร้างก`StructuredDocumentTag` (SDT) สำหรับส่วนที่ทำซ้ำและแมปกับข้อมูล XML:

```csharp
StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## ขั้นตอนที่ 5: สร้างรายการส่วนที่ทำซ้ำ

สร้าง SDT สำหรับรายการส่วนที่ทำซ้ำ และเพิ่มลงในส่วนที่ทำซ้ำ:

```csharp
StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## ขั้นตอนที่ 6: แมปข้อมูล XML กับเซลล์ตาราง

สร้าง SDT สำหรับชื่อเรื่องและผู้แต่ง แมปกับข้อมูล XML และผนวกเข้ากับแถว:

```csharp
StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารลงในไดเร็กทอรีที่ระบุ:

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

## บทสรุป

ด้วยการทำตามขั้นตอนเหล่านี้ คุณได้สร้างตารางที่มีส่วนที่ทำซ้ำซึ่งแมปกับส่วน XML แบบกำหนดเองได้สำเร็จโดยใช้ Aspose.Words สำหรับ .NET ช่วยให้สามารถสร้างเนื้อหาแบบไดนามิกตามข้อมูลที่มีโครงสร้าง ทำให้การสร้างเอกสารมีความยืดหยุ่นและมีประสิทธิภาพมากขึ้น

## คำถามที่พบบ่อย

### StructuredDocumentTag (SDT) คืออะไร
SDT หรือที่เรียกว่าการควบคุมเนื้อหา คือขอบเขตที่มีขอบเขตในเอกสารที่ใช้เพื่อเก็บข้อมูลที่มีโครงสร้าง

### ฉันสามารถใช้ข้อมูลประเภทอื่นในส่วน XML แบบกำหนดเองได้หรือไม่
ได้ คุณสามารถจัดโครงสร้างส่วน XML แบบกำหนดเองของคุณด้วยประเภทข้อมูลใดก็ได้และแมปตามนั้น

### ฉันจะเพิ่มแถวในส่วนการทำซ้ำได้อย่างไร
ส่วนการทำซ้ำจะจำลองโครงสร้างแถวสำหรับแต่ละรายการในเส้นทาง XML ที่แมปโดยอัตโนมัติ