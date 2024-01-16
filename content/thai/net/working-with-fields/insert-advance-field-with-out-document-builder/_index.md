---
title: แทรกฟิลด์ขั้นสูงโดยไม่มีตัวสร้างเอกสาร
linktitle: แทรกฟิลด์ขั้นสูงโดยไม่มีตัวสร้างเอกสาร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกฟิลด์ขั้นสูงลงในเอกสาร Word ของคุณด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่าง ซึ่งใช้ฟีเจอร์ "การแทรกฟิลด์ขั้นสูงโดยไม่มี DocumentBuilder" ของ Aspose.Words สำหรับ .NET อย่าลืมปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

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

## ขั้นตอนที่ 3: การแทรกฟิลด์ขั้นสูง

 เราใช้`AppendField()` วิธีการแทรกฟิลด์ขั้นสูงลงในย่อหน้า

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

จากนั้นเรากำหนดค่าคุณสมบัติต่างๆ ของฟิลด์ขั้นสูงโดยระบุค่าที่ต้องการ

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 ในที่สุดเราก็เรียกว่า`Update()` วิธีการอัพเดตสนาม

```csharp
field. Update();
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกฟิลด์ขั้นสูงโดยไม่มี DocumentBuilder ด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// การสร้างเอกสาร
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// แทรกฟิลด์ขั้นสูง
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

ในตัวอย่างนี้ เราสร้างเอกสารใหม่ แทรกฟิลด์ขั้นสูงโดยไม่ใช้ DocumentBuilder กำหนดค่าคุณสมบัติฟิลด์ต่างๆ และบันทึกเอกสารด้วยชื่อไฟล์ที่ระบุ

นี่เป็นการสรุปคำแนะนำของเราเกี่ยวกับวิธีใช้ฟีเจอร์ "แทรกฟิลด์ขั้นสูงโดยไม่มี DocumentBuilder" กับ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: ฟิลด์ขั้นสูงใน Aspose.Words คืออะไร

ตอบ: ฟิลด์ขั้นสูงใน Aspose.Words เป็นฟิลด์ประเภทพิเศษที่ช่วยให้คุณสามารถคำนวณ รวมเงื่อนไข และดำเนินการที่ซับซ้อนในเอกสาร Word ได้ ให้ความยืดหยุ่นอย่างมากในการสร้างฟิลด์แบบไดนามิกและแบบกำหนดเอง

#### ถาม: จะแทรกฟิลด์ขั้นสูงในเอกสาร Word โดยไม่ต้องใช้ Document Builder ใน Aspose.Words ได้อย่างไร

ตอบ: หากต้องการแทรกฟิลด์ขั้นสูงในเอกสาร Word โดยไม่ต้องใช้ Document Builder ใน Aspose.Words คุณสามารถทำตามขั้นตอนเหล่านี้:

1. นำเข้าคลาสเอกสารและฟิลด์จากเนมสเปซ Aspose.Words.Fields
2. สร้างอินสแตนซ์ของเอกสารโดยการโหลดเอกสารที่มีอยู่ของคุณ
3. ใช้เมธอด InsertField เพื่อแทรกเขตข้อมูลขั้นสูงโดยการระบุโค้ดเขตข้อมูลขั้นสูง
4. บันทึกเอกสาร

#### ถาม: จะรับผลลัพธ์ของฟิลด์ขั้นสูงในเอกสาร Word ได้อย่างไร

ตอบ: หากต้องการรับผลลัพธ์ของเขตข้อมูลขั้นสูงในเอกสาร Word คุณสามารถใช้คุณสมบัติผลลัพธ์ที่มีอยู่ในคลาสเขตข้อมูลได้ คุณสมบัตินี้ส่งกลับผลลัพธ์จากการคำนวณของเขตข้อมูล

#### ถาม: ฉันสามารถแก้ไขสูตรของฟิลด์ขั้นสูงหลังจากแทรกลงในเอกสาร Word ได้หรือไม่

ตอบ: ได้ คุณสามารถแก้ไขสูตรของฟิลด์ขั้นสูงได้หลังจากแทรกลงในเอกสาร Word แล้ว คุณสามารถทำได้โดยการเข้าถึงคุณสมบัติ FieldCode ของคลาส Field และอัปเดตสูตรโดยการแก้ไขข้อความของสูตร