---
title: เปลี่ยนชื่อเขตข้อมูลผสาน
linktitle: เปลี่ยนชื่อเขตข้อมูลผสาน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีเปลี่ยนชื่อเขตข้อมูลผสานในเอกสารโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fields/rename-merge-fields/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่างซึ่งใช้คุณลักษณะการเปลี่ยนชื่อฟิลด์ผสานของ Aspose.Words สำหรับ .NET ปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในโค้ดที่ให้มา คุณต้องระบุไดเร็กทอรีของเอกสารของคุณ แทนที่ค่า "YOUR DOCUMENT DIRECTORY" ด้วยเส้นทางที่เหมาะสมไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสารและการแทรกเขตข้อมูลผสาน

เราเริ่มต้นด้วยการสร้างเอกสารใหม่และใช้`DocumentBuilder` เพื่อแทรกเขตข้อมูลผสาน

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## ขั้นตอนที่ 3: การเปลี่ยนชื่อเขตข้อมูลผสาน

เราวนซ้ำแต่ละฟิลด์ในช่วงเอกสาร และหากเป็นฟิลด์ที่ผสาน เราจะเปลี่ยนชื่อฟิลด์โดยการเพิ่ม "-เปลี่ยนชื่อ" คำต่อท้าย

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

 ในที่สุดเราก็เรียกว่า`Save()` วิธีการบันทึกเอกสารที่แก้ไข

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการเปลี่ยนชื่อฟิลด์ผสานด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสารและแทรกเขตข้อมูลผสาน
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// เปลี่ยนชื่อเขตข้อมูลผสาน
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// บันทึกเอกสาร
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

ทำตามขั้นตอนเหล่านี้เพื่อเปลี่ยนชื่อเขตข้อมูลผสานในเอกสารของคุณโดยใช้ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเปลี่ยนชื่อฟิลด์ที่ผสานในเอกสาร Word โดยใช้ Aspose.Words for .NET ได้อย่างไร

 ตอบ: หากต้องการเปลี่ยนชื่อฟิลด์ที่ผสานในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถวนซ้ำฟิลด์ในเอกสารโดยใช้`FieldMergingArgs` คลาสและใช้`FieldMergingArgs.FieldName` วิธีการเปลี่ยนชื่อฟิลด์

#### ถาม: เป็นไปได้ไหมที่จะเปลี่ยนชื่อเฉพาะบางฟิลด์ที่ผสานในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET

ตอบ: ได้ คุณสามารถเปลี่ยนชื่อเฉพาะบางฟิลด์ที่ผสานในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET ได้ คุณสามารถกรองฟิลด์ที่จะเปลี่ยนชื่อโดยใช้เกณฑ์เฉพาะ เช่น ชื่อฟิลด์หรือคุณสมบัติอื่นๆ ที่เกี่ยวข้อง จากนั้นคุณสามารถเปลี่ยนชื่อฟิลด์ที่เกี่ยวข้องได้โดยใช้`FieldMergingArgs.FieldName` วิธี.

#### ถาม: ฉันจะตรวจสอบได้อย่างไรว่าฟิลด์ที่ผสานถูกเปลี่ยนชื่อในเอกสาร Word ด้วย Aspose.Words for .NET สำเร็จหรือไม่

 ตอบ: หากต้องการตรวจสอบว่าฟิลด์ที่ผสานถูกเปลี่ยนชื่อในเอกสาร Word ด้วย Aspose.Words for .NET สำเร็จหรือไม่ คุณสามารถใช้`FieldMergedArgs` คลาสและการเข้าถึง`FieldMergedArgs.IsMerged` คุณสมบัติเพื่อตรวจสอบว่าฟิลด์ถูกเปลี่ยนชื่อด้วย Hit หรือไม่

#### ถาม: อะไรคือผลที่ตามมาของการเปลี่ยนชื่อฟิลด์ที่ผสานในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET

ตอบ: เมื่อคุณเปลี่ยนชื่อเขตข้อมูลที่ผสานในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET จะเปลี่ยนชื่อของเขตข้อมูลในเอกสาร ซึ่งอาจส่งผลกระทบต่อฟังก์ชันการทำงานหรือกระบวนการอื่นๆ ที่ขึ้นอยู่กับชื่อเขตข้อมูล อย่าลืมคำนึงถึงผลที่ตามมาที่อาจเกิดขึ้นเหล่านี้ก่อนเปลี่ยนชื่อช่องที่ผสาน

#### ถาม: เป็นไปได้หรือไม่ที่จะคืนค่าชื่อเดิมของฟิลด์ที่ผสานหลังจากเปลี่ยนชื่อเป็น Aspose.Words สำหรับ .NET

ตอบ: ได้ คุณสามารถเรียกคืนชื่อเดิมของฟิลด์ที่ผสานได้หลังจากเปลี่ยนชื่อเป็น Aspose.Words สำหรับ .NET คุณสามารถจัดเก็บชื่อเดิมของเขตข้อมูลไว้ในตัวแปรหรือรายการ จากนั้นใช้ข้อมูลนั้นเพื่อเรียกคืนชื่อเดิมได้ หากจำเป็น