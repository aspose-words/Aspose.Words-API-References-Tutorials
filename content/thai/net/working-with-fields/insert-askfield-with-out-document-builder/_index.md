---
title: แทรก ASKField โดยไม่มีตัวสร้างเอกสาร
linktitle: แทรก ASKField โดยไม่มีตัวสร้างเอกสาร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกฟิลด์ ASK ลงในเอกสาร Word ของคุณด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-fields/insert-askfield-with-out-document-builder/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่าง ซึ่งใช้ฟีเจอร์ "แทรกฟิลด์ ASK โดยไม่มี DocumentBuilder" ของ Aspose.Words สำหรับ .NET อย่าลืมปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในโค้ดที่ให้มา คุณต้องระบุไดเร็กทอรีของเอกสารของคุณ แทนที่ค่า "YOUR DOCUMENT DIRECTORY" ด้วยเส้นทางที่เหมาะสมไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสารและย่อหน้า

เราเริ่มต้นด้วยการสร้างเอกสารใหม่และดึงย่อหน้าแรก

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## ขั้นตอนที่ 3: การแทรกฟิลด์ ASK

 เราใช้`AppendField()` วิธีการแทรกฟิลด์ ASK ลงในย่อหน้า

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

จากนั้นเรากำหนดค่าคุณสมบัติต่างๆ ของฟิลด์ ASK โดยระบุค่าที่ต้องการ

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 ในที่สุดเราก็เรียกว่า`Update()` วิธีการอัพเดตสนาม

```csharp
field. Update();
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกฟิลด์ ASK โดยไม่มี DocumentBuilder ด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// การสร้างเอกสาร
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// แทรกฟิลด์ ASK
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

ในตัวอย่างนี้ เราสร้างเอกสารใหม่ แทรกฟิลด์ ASK โดยไม่ใช้ DocumentBuilder กำหนดค่าคุณสมบัติต่างๆ ของฟิลด์ และบันทึกเอกสารด้วยชื่อไฟล์ที่ระบุ

นี่เป็นการสรุปคำแนะนำของเราเกี่ยวกับการใช้ฟีเจอร์ "แทรกฟิลด์ ASK โดยไม่มี DocumentBuilder" กับ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: ฟิลด์ ASK ใน Aspose.Words คืออะไร

ตอบ: ช่อง ASK ใน Aspose.Words ใช้เพื่อถามคำถามผู้ใช้เมื่อเปิดเอกสาร มักใช้เพื่อขอข้อมูลเฉพาะหรือข้อเสนอแนะซึ่งอาจแตกต่างกันไปในผู้ใช้แต่ละคน

#### ถาม: วิธีแทรกฟิลด์ ASK ในเอกสาร Word โดยไม่ใช้ Document Builder ใน Aspose.Words

ตอบ: หากต้องการแทรกฟิลด์ ASK ในเอกสาร Word โดยไม่ต้องใช้ Document Builder ใน Aspose.Words คุณสามารถทำตามขั้นตอนเหล่านี้:

1. นำเข้าคลาสเอกสารและฟิลด์จากเนมสเปซ Aspose.Words.Fields
2. สร้างอินสแตนซ์ของเอกสารโดยการโหลดเอกสารที่มีอยู่ของคุณ
3. ใช้เมธอด InsertField เพื่อแทรกฟิลด์ ASK โดยการระบุชื่อคำถาม
4. บันทึกเอกสาร

#### ถาม: ฉันจะได้รับการตอบสนองของผู้ใช้สำหรับช่อง ASK ในเอกสาร Word ได้อย่างไร

ตอบ: หากต้องการรับการตอบสนองของผู้ใช้สำหรับฟิลด์ ASK ในเอกสาร Word คุณสามารถใช้เมธอด GetFieldNames ที่มีอยู่ในคลาส Document ได้ วิธีนี้จะส่งคืนรายการชื่อของฟิลด์ที่มีอยู่ในเอกสาร จากนั้นคุณสามารถตรวจสอบได้ว่ามีชื่อฟิลด์ ASK อยู่ในรายการหรือไม่ และดึงข้อมูลการตอบกลับที่เกี่ยวข้องได้

#### ถาม: ช่อง ASK สามารถใช้เพื่อขอข้อมูลเพิ่มเติมจากผู้ใช้ได้หรือไม่

ตอบ: ได้ ช่อง ASK สามารถใช้เพื่อขอข้อมูลหลายรายการจากผู้ใช้ได้ คุณสามารถแทรกช่อง ASK หลายช่องลงในเอกสารของคุณได้ โดยแต่ละช่องจะมีคำถามที่แตกต่างกัน เมื่อเปิดเอกสาร ผู้ใช้จะได้รับคำตอบที่เกี่ยวข้อง