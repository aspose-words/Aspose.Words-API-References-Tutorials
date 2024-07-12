---
title: แทรกฟิลด์ TOA โดยไม่มีตัวสร้างเอกสาร
linktitle: แทรกฟิลด์ TOA โดยไม่มีตัวสร้างเอกสาร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการแทรกฟิลด์ TOA โดยไม่ต้องใช้ตัวสร้างเอกสารโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fields/insert-toafield-without-document-builder/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่าง ซึ่งใช้ฟีเจอร์ "การแทรกฟิลด์ TOA" ของ Aspose.Words สำหรับ .NET ปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในโค้ดที่ให้มา คุณต้องระบุไดเร็กทอรีของเอกสารของคุณ แทนที่ค่า "YOUR DOCUMENT DIRECTORY" ด้วยเส้นทางที่เหมาะสมไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสารและย่อหน้า

เราเริ่มต้นด้วยการสร้างเอกสารใหม่และเตรียมใช้งานย่อหน้า

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## ขั้นตอนที่ 3: การแทรกฟิลด์ TA

เราใช้คลาส FieldTA เพื่อแทรกฟิลด์ TA ลงในย่อหน้า

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## ขั้นตอนที่ 4: การเพิ่มย่อหน้าลงในเนื้อหาของเอกสาร

เราเพิ่มย่อหน้าที่มีฟิลด์ TA ลงในเนื้อหาของเอกสาร

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## ขั้นตอนที่ 5: การสร้างย่อหน้าสำหรับฟิลด์ TOA

เราสร้างย่อหน้าใหม่สำหรับฟิลด์ TOA

```csharp
para = new Paragraph(doc);
```

## ขั้นตอนที่ 6: การแทรกฟิลด์ TOA

เราใช้คลาส FieldToa เพื่อแทรกฟิลด์ TOA ลงในย่อหน้า

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## ขั้นตอนที่ 7: การเพิ่มย่อหน้าลงในเนื้อหาของเอกสาร

เราเพิ่มย่อหน้าที่มีฟิลด์ TOA ลงในเนื้อหาของเอกสาร

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## ขั้นตอนที่ 8: อัปเดตฟิลด์ TOA

 ในที่สุดเราก็เรียกว่า`Update()` วิธีการอัพเดตฟิลด์ TOA

```csharp
fieldToa.Update();
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกฟิลด์ TOA โดยไม่มีตัวสร้างเอกสารด้วย Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// เราต้องการแทรกฟิลด์ TA และ TOA เช่นนี้:
// { TA \c 1 \l "ค่า 0" }
// { ทีโอเอ \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### คำถามที่พบบ่อย

#### ถาม: จะปรับแต่งลักษณะที่ปรากฏของฟิลด์ TOA ที่แทรกในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: คุณสามารถปรับแต่งลักษณะที่ปรากฏของฟิลด์ TOA ที่แทรกไว้ได้โดยใช้คุณสมบัติของ`FieldTOA` วัตถุเพื่อระบุตัวเลือกการจัดรูปแบบ

#### ถาม: ฉันสามารถเพิ่มฟิลด์ TOA หลายฟิลด์ในเอกสาร Word เดียวโดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มฟิลด์ TOA หลายฟิลด์ในเอกสาร Word เดียวได้โดยใช้ Aspose.Words สำหรับ .NET เพียงทำซ้ำขั้นตอนการแทรกสำหรับแต่ละฟิลด์

#### ถาม: ฉันจะตรวจสอบได้อย่างไรว่าฟิลด์ TOA แทรกลงในเอกสาร Word ด้วย Aspose.Words for .NET ได้สำเร็จหรือไม่

ตอบ: หากต้องการตรวจสอบว่าแทรกช่อง TOA สำเร็จหรือไม่ คุณสามารถเรียกดูเนื้อหาเอกสารและค้นหาอินสแตนซ์ของช่อง TOA ได้

#### ถาม: การแทรกฟิลด์ TOA โดยไม่ใช้ DocumentBuilder ส่งผลต่อการจัดรูปแบบเอกสาร Word ด้วย Aspose.Words สำหรับ .NET หรือไม่

ตอบ: การแทรกฟิลด์ TOA โดยไม่ใช้ DocumentBuilder จะไม่ส่งผลโดยตรงต่อการจัดรูปแบบของเอกสาร Word อย่างไรก็ตาม ตัวเลือกการจัดรูปแบบฟิลด์ TOA อาจส่งผลต่อการจัดรูปแบบโดยรวมของเอกสาร