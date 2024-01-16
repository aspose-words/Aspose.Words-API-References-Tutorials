---
title: แทรกเขตข้อมูลผสานโดยใช้ DOM
linktitle: แทรกเขตข้อมูลผสานโดยใช้ DOM
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกฟิลด์ผสานฟิลด์แบบกำหนดเองลงในเอกสาร Word ของคุณด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-fields/insert-merge-field-using-dom/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่างซึ่งใช้ฟีเจอร์ "แทรกฟิลด์ผสานฟิลด์" ของ Aspose.Words สำหรับ .NET อย่าลืมปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

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

 เราใช้`MoveTo()` วิธีการ DocumentBuilder เพื่อย้ายเคอร์เซอร์ไปยังย่อหน้าที่เราต้องการแทรกฟิลด์ผสานฟิลด์

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## ขั้นตอนที่ 4: การแทรกฟิลด์ผสานฟิลด์

 เราใช้ DocumentBuilder's`InsertField()` วิธีการแทรกฟิลด์ผสานฟิลด์ลงในย่อหน้า

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

จากนั้นเรากำหนดค่าคุณสมบัติของฟิลด์ผสานฟิลด์โดยการระบุตัวเลือกที่เหมาะสม เช่น ชื่อฟิลด์ ข้อความก่อนและหลังฟิลด์ และตัวเลือกการจัดรูปแบบแนวตั้ง

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 ในที่สุดเราก็เรียกว่า`Update()` วิธีการอัพเดตสนาม

```csharp
field. Update();
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกฟิลด์ผสานฟิลด์ด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสารและ DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ย้ายเคอร์เซอร์ไปที่ย่อหน้า
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// แทรกฟิลด์ผสานฟิลด์
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// อัพเดทสนามครับ.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

ในตัวอย่างนี้ เราได้สร้างเอกสารใหม่ ย้ายเคอร์เซอร์ไปยังย่อหน้าที่ต้องการ จากนั้นแทรกฟิลด์ผสานฟิลด์ลงในเอกสาร

### คำถามที่พบบ่อย

#### ถาม: ฉันจะแทรกเขตข้อมูลผสานในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET กับ DOM ได้อย่างไร

ตอบ: หากต้องการแทรกเขตข้อมูลผสานในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET พร้อมด้วย DOM คุณสามารถทำตามขั้นตอนเหล่านี้:

1. นำทางไปยังย่อหน้าที่คุณต้องการแทรกเขตข้อมูลผสาน
2.  สร้างก`FieldMergeField` วัตถุ.
3. ตั้งค่าคุณสมบัติเขตข้อมูลผสาน เช่น ชื่อเขตข้อมูลและตัวเลือกการจัดรูปแบบ
4.  เพิ่มฟิลด์ผสานลงในย่อหน้าโดยใช้`Paragraph.AppendChild` วิธี.

#### ถาม: ฉันจะระบุแหล่งข้อมูลสำหรับฟิลด์ผสานใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการระบุแหล่งข้อมูลสำหรับเขตข้อมูลผสานใน Aspose.Words สำหรับ .NET คุณสามารถใช้`FieldMergeField.FieldName` วิธีการตั้งชื่อเขตข้อมูลผสาน ซึ่งเป็นชื่อของเขตข้อมูลในแหล่งข้อมูลภายนอก เช่น ไฟล์ CSV ฐานข้อมูล ฯลฯ คุณยังสามารถใช้`FieldMergeField.Text` วิธีการตั้งค่าเขตข้อมูลผสานโดยตรง

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเขตข้อมูลผสานในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของเขตข้อมูลผสานในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET ได้ คุณสามารถตั้งค่าตัวเลือกการจัดรูปแบบ เช่น ตัวพิมพ์ แบบอักษร สี ฯลฯ โดยใช้คุณสมบัติของ`FieldMergeField` วัตถุ.

#### ถาม: ฉันจะตรวจสอบได้อย่างไรว่าแทรกเขตข้อมูลผสานในเอกสาร Word ด้วย Aspose.Words for .NET ได้สำเร็จหรือไม่

 ตอบ: หากต้องการตรวจสอบว่าแทรกเขตข้อมูลผสานสำเร็จหรือไม่ คุณสามารถเรียกดูเนื้อหาเอกสารและค้นหาอินสแตนซ์ของเขตข้อมูลผสานได้ คุณสามารถใช้วิธีการและคุณสมบัติของการ`Document` วัตถุเพื่อเข้าถึงย่อหน้า ฟิลด์ และองค์ประกอบอื่นๆ ของเอกสาร

#### ถาม: การแทรกเขตข้อมูลผสานโดยใช้ DOM ส่งผลต่อโครงสร้างเอกสาร Word ด้วย Aspose.Words สำหรับ .NET หรือไม่

ตอบ: การแทรกเขตข้อมูลผสานโดยใช้ DOM จะไม่ส่งผลโดยตรงต่อโครงสร้างของเอกสาร Word อย่างไรก็ตาม จะเพิ่มองค์ประกอบฟิลด์ใหม่ให้กับเนื้อหาเอกสาร คุณสามารถจัดการโครงสร้างเอกสารได้โดยการเพิ่ม ลบ หรือแก้ไของค์ประกอบที่มีอยู่ตามความต้องการของคุณ