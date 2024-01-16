---
title: แทรกฟิลด์โดยใช้ตัวสร้างฟิลด์
linktitle: แทรกฟิลด์โดยใช้ตัวสร้างฟิลด์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกฟิลด์ที่กำหนดเองลงในเอกสาร Word ของคุณด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fields/insert-field-using-field-builder/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่าง ซึ่งใช้ฟีเจอร์ "แทรกฟิลด์โดยใช้ FieldBuilder" ของ Aspose.Words สำหรับ .NET อย่าลืมปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในโค้ดที่ให้มา คุณต้องระบุไดเร็กทอรีของเอกสารของคุณ แทนที่ค่า "YOUR DOCUMENT DIRECTORY" ด้วยเส้นทางที่เหมาะสมไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสาร

เราเริ่มต้นด้วยการสร้างเอกสารใหม่

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 3: สร้างฟิลด์ IF โดยใช้ FieldBuilder

เราใช้คลาส FieldBuilder เพื่อสร้างฟิลด์ IF โดยมีฟิลด์ MERGEFIELD สองฟิลด์ที่ซ้อนกัน ในตัวอย่างนี้ ฟิลด์ IF จะแสดงชื่อและนามสกุลตามเงื่อนไข

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## ขั้นตอนที่ 4: การแทรกฟิลด์ IF ลงในเอกสาร

 เราใช้`BuildAndInsert()` วิธีการสร้างและแทรกฟิลด์ IF ในตำแหน่งเฉพาะในเอกสาร

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกฟิลด์โดยใช้ FieldBuilder กับ Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// การสร้างเอกสาร
Document doc = new Document();

// การสร้างฟิลด์ IF โดยใช้ FieldBuilder
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// แทรกฟิลด์ IF ลงในเอกสาร
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

ในตัวอย่างนี้ เราได้สร้างเอกสารใหม่ สร้างฟิลด์ IF โดยมีฟิลด์ MERGEFIELD ที่ซ้อนกัน จากนั้นแทรกฟิลด์นั้นลงในเอกสารในตำแหน่งที่ระบุ จากนั้นเอกสารจะถูกบันทึกด้วยชื่อไฟล์เฉพาะ

### คำถามที่พบบ่อย

#### ถาม: ตัวสร้างฟิลด์ใน Aspose.Words คืออะไร

ตอบ: ตัวสร้างฟิลด์ใน Aspose.Words เป็นเครื่องมืออันทรงพลังสำหรับการสร้างและจัดการฟิลด์ในเอกสาร Word โดยนำเสนอคุณสมบัติขั้นสูงสำหรับการสร้างและปรับแต่งฟิลด์ รวมถึงการแทรกโค้ดฟิลด์และการจัดการตัวเลือกการจัดรูปแบบ

#### ถาม: ฟิลด์ประเภทใดที่สามารถแทรกได้โดยใช้ตัวสร้างฟิลด์

ตอบ: ตัวสร้างฟิลด์ใน Aspose.Words ช่วยให้คุณสามารถแทรกฟิลด์ประเภทต่างๆ ลงในเอกสาร Word ได้ ต่อไปนี้คือตัวอย่างบางส่วนของประเภทฟิลด์ที่ใช้กันทั่วไป:

- MERGEFIELD: ใช้เพื่อรวมข้อมูลจากแหล่งภายนอก
- DATE: แสดงวันที่ปัจจุบัน
- PAGE: แสดงหมายเลขหน้าปัจจุบัน
- IF: อนุญาตให้กำหนดเงื่อนไขการแสดงเนื้อหาตามเงื่อนไข
- TOC: สร้างสารบัญโดยอัตโนมัติตามสไตล์ชื่อเอกสาร

#### ถาม: จะปรับแต่งฟิลด์ที่แทรกด้วยตัวสร้างฟิลด์ได้อย่างไร

ตอบ: ตัวสร้างฟิลด์เสนอตัวเลือกการปรับแต่งสำหรับฟิลด์ที่แทรก คุณสามารถใช้วิธีและคุณสมบัติตัวสร้างฟิลด์เพื่อตั้งค่าตัวเลือก เช่น การจัดรูปแบบฟิลด์ อาร์กิวเมนต์ สวิตช์ และค่าเริ่มต้น ตัวอย่างเช่น คุณสามารถตั้งค่ารูปแบบวันที่ รูปแบบตัวเลข ตัวคั่นหลักพัน เป็นต้น
  