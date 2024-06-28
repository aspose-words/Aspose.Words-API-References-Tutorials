---
title: แทรกฟิลด์บล็อกที่อยู่จดหมายเวียนโดยใช้ DOM
linktitle: แทรกฟิลด์บล็อกที่อยู่จดหมายเวียนโดยใช้ DOM
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกฟิลด์บล็อกที่อยู่จดหมายเวียนลงในเอกสาร Word ของคุณด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่าง ซึ่งใช้ฟีเจอร์ "แทรกฟิลด์บล็อกที่อยู่จดหมายเวียน" ของ Aspose.Words สำหรับ .NET อย่าลืมปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในโค้ดที่ให้มา คุณต้องระบุไดเร็กทอรีของเอกสารของคุณ แทนที่ค่า "YOUR DOCUMENT DIRECTORY" ด้วยเส้นทางที่เหมาะสมไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสารและ DocumentBuilder

เราเริ่มต้นด้วยการสร้างเอกสารใหม่และเตรียมใช้งาน DocumentBuilder

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: เลื่อนเคอร์เซอร์ไปที่ย่อหน้า

 เราใช้ DocumentBuilder's`MoveTo()` วิธีการเลื่อนเคอร์เซอร์ไปที่ย่อหน้าที่เราต้องการแทรกฟิลด์บล็อกที่อยู่จดหมายเวียน

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## ขั้นตอนที่ 4: การแทรกฟิลด์บล็อกที่อยู่จดหมายเวียน

 เราใช้ DocumentBuilder's`InsertField()` วิธีการแทรกช่องบล็อกที่อยู่จดหมายเวียนลงในย่อหน้า

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

จากนั้นเรากำหนดค่าคุณสมบัติของฟิลด์บล็อกที่อยู่โดยระบุตัวเลือกที่เหมาะสม เช่น การรวมชื่อประเทศ/ภูมิภาค การจัดรูปแบบที่อยู่ตามประเทศ/ภูมิภาค ชื่อประเทศ/ภูมิภาคที่ยกเว้น รูปแบบชื่อและที่อยู่ และตัวระบุภาษา

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 ในที่สุดเราก็เรียกว่า`Update()` วิธีการอัพเดตสนาม

```csharp
field. Update();
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกฟิลด์บล็อกที่อยู่จดหมายเวียนด้วย Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// เราต้องการแทรกบล็อกที่อยู่จดหมายเวียนดังนี้:
// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"ทดสอบ 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { แอดเดรสบล็อก\c1" }
field.IncludeCountryOrRegionName = "1";

// { บล็อกที่อยู่ \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { ADDRESSBLOCK \\c 1 \\d \\e ทดสอบ 2 }
field.ExcludedCountryOrRegionName = "Test2";

// { ADDRESSBLOCK \\c 1 \\d \\e ทดสอบ 2 \\f ทดสอบ 3 }
field.NameAndAddressFormat = "Test3";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"ทดสอบ 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### คำถามที่พบบ่อย

#### ถาม: ฉันจะปรับแต่งรูปแบบของที่อยู่ทางไปรษณีย์ในเอกสาร Word ด้วย Aspose.Words for .NET ได้อย่างไร

 ตอบ: คุณสามารถปรับแต่งรูปแบบของที่อยู่ทางไปรษณีย์ในเอกสาร Word ด้วย Aspose.Words for .NET ได้โดยใช้คุณสมบัติของ`FieldAddressBlock`วัตถุ วัตถุ คุณสามารถตั้งค่าตัวเลือกการจัดรูปแบบ เช่น สไตล์ที่อยู่ ตัวคั่น รายการเสริม ฯลฯ เพื่อให้ได้รูปแบบที่ต้องการ

#### ถาม: ฉันจะระบุแหล่งข้อมูลสำหรับฟิลด์ที่อยู่ทางไปรษณีย์ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการระบุแหล่งข้อมูลสำหรับฟิลด์ที่อยู่ทางไปรษณีย์ใน Aspose.Words สำหรับ .NET คุณสามารถใช้`FieldAddressBlock.StartAddress` และ`FieldAddressBlock.EndAddress` คุณสมบัติ. คุณสมบัติเหล่านี้ใช้เพื่อกำหนดช่วงที่อยู่ในแหล่งข้อมูลภายนอก เช่น ไฟล์ CSV ฐานข้อมูล ฯลฯ

#### ถาม: ฉันสามารถรวมองค์ประกอบเสริมในช่องที่อยู่ทางไปรษณีย์ด้วย Aspose.Words for .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถรวมองค์ประกอบเสริมในช่องที่อยู่ทางไปรษณีย์ด้วย Aspose.Words สำหรับ .NET ได้ คุณสามารถกำหนดองค์ประกอบทางเลือกได้โดยใช้`FieldAddressBlock.OmitOptional` วิธีการระบุว่าจะรวมหรือไม่รวมองค์ประกอบเสริม เช่น ชื่อผู้รับ ชื่อบริษัท เป็นต้น

#### ถาม: การแทรกฟิลด์ที่อยู่ทางไปรษณีย์โดยใช้ DOM ส่งผลต่อโครงสร้างเอกสาร Word ด้วย Aspose.Words สำหรับ .NET หรือไม่

ตอบ: การแทรกฟิลด์ที่อยู่ทางไปรษณีย์โดยใช้ DOM จะไม่ส่งผลโดยตรงต่อโครงสร้างของเอกสาร Word อย่างไรก็ตาม จะเพิ่มองค์ประกอบฟิลด์ใหม่ให้กับเนื้อหาเอกสาร คุณสามารถจัดการโครงสร้างเอกสารได้โดยการเพิ่ม ลบ หรือแก้ไของค์ประกอบที่มีอยู่ตามความต้องการของคุณ