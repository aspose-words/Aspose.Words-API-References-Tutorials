---
title: ขอบเขตที่แก้ไขได้ไม่จำกัดในเอกสาร Word
linktitle: ขอบเขตที่แก้ไขได้ไม่จำกัดในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างพื้นที่ที่แก้ไขได้ไม่จำกัดในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/document-protection/unrestricted-editable-regions/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนในการใช้ฟีเจอร์พื้นที่ที่แก้ไขได้ไม่จำกัดของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณกำหนดพื้นที่ในเอกสาร Word ที่สามารถแก้ไขเนื้อหาได้โดยไม่มีข้อจำกัด แม้ว่าส่วนที่เหลือของเอกสารจะเป็นแบบอ่านอย่างเดียวก็ตาม ทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: การโหลดเอกสารและการตั้งค่าการป้องกัน

เริ่มต้นด้วยการโหลดเอกสารที่มีอยู่:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

ป้องกันเอกสารโดยการตั้งค่าประเภทการป้องกันและรหัสผ่านแบบอ่านอย่างเดียว

## ขั้นตอนที่ 2: สร้างพื้นที่ที่สามารถแก้ไขได้

เริ่มต้นด้วยการสร้างพื้นที่ที่สามารถแก้ไขได้โดยใช้ออบเจ็กต์ EditableRangeStart และ EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// วัตถุ EditableRange ถูกสร้างขึ้นสำหรับ EditableRangeStart ที่เราเพิ่งสร้างขึ้น
EditableRange editableRange = edRangeStart.EditableRange;

// วางบางสิ่งไว้ในช่วงที่แก้ไขได้
builder.Writeln("Paragraph inside first editable range");

// ช่วงที่แก้ไขได้จะมีรูปแบบที่ดีหากมีจุดเริ่มต้นและจุดสิ้นสุด
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## ขั้นตอนที่ 3: เพิ่มเนื้อหานอกพื้นที่ที่แก้ไขได้

คุณสามารถเพิ่มเนื้อหานอกพื้นที่ที่แก้ไขได้ ซึ่งจะยังคงเป็นแบบอ่านอย่างเดียว:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารที่แก้ไข:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องเพื่อบันทึกเอกสารด้วยพื้นที่ที่สามารถแก้ไขได้

### ตัวอย่างซอร์สโค้ดสำหรับภูมิภาคที่แก้ไขได้ไม่จำกัดโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับพื้นที่ที่แก้ไขได้ไม่จำกัดโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// อัปโหลดเอกสารและทำให้เป็นแบบอ่านอย่างเดียว
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// เริ่มช่วงที่แก้ไขได้
EditableRangeStart edRangeStart = builder.StartEditableRange();
// วัตถุ EditableRange ถูกสร้างขึ้นสำหรับ EditableRangeStart ที่เราเพิ่งสร้างขึ้น
EditableRange editableRange = edRangeStart.EditableRange;

// วางบางสิ่งไว้ในช่วงที่แก้ไขได้
builder.Writeln("Paragraph inside first editable range");

// ช่วงที่แก้ไขได้จะมีรูปแบบที่ดีหากมีจุดเริ่มต้นและจุดสิ้นสุด
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถสร้างพื้นที่ที่แก้ไขได้ไม่จำกัดในเอกสาร Word ของคุณด้วย Aspose.Words for .NET

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างขอบเขตที่แก้ไขได้ไม่จำกัดในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถกำหนดพื้นที่เฉพาะภายในเอกสารที่ผู้ใช้สามารถแก้ไขเนื้อหาได้อย่างอิสระในขณะที่ยังคงให้ส่วนที่เหลือของเอกสารเป็นแบบอ่านอย่างเดียว Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติที่มีประสิทธิภาพสำหรับการป้องกันและการปรับแต่งเอกสาร ทำให้คุณสามารถควบคุมความสามารถในการแก้ไขเอกสาร Word ของคุณได้

### คำถามที่พบบ่อยสำหรับขอบเขตที่แก้ไขได้ไม่จำกัดในเอกสารเวิร์ด

#### ถาม: ขอบเขตที่สามารถแก้ไขได้แบบไม่จำกัดใน Aspose.Words สำหรับ .NET คืออะไร

ตอบ: ขอบเขตที่แก้ไขได้ไม่จำกัดใน Aspose.Words สำหรับ .NET คือพื้นที่ภายในเอกสาร Word ซึ่งเนื้อหาสามารถแก้ไขได้โดยไม่มีข้อจำกัดใดๆ แม้ว่าส่วนที่เหลือของเอกสารจะถูกตั้งค่าเป็นแบบอ่านอย่างเดียวก็ตาม ภูมิภาคเหล่านี้มีวิธีกำหนดส่วนเฉพาะของเอกสารที่ผู้ใช้สามารถปรับเปลี่ยนได้ในขณะที่ยังคงการปกป้องเอกสารโดยรวมไว้

#### ถาม: ฉันจะสร้างขอบเขตที่สามารถแก้ไขได้แบบไม่จำกัดโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการสร้างขอบเขตที่แก้ไขได้ไม่จำกัดในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:
1.  โหลดเอกสารที่มีอยู่โดยใช้`Document` ชั้นเรียน
2.  ตั้งค่าการป้องกันเอกสารเป็นแบบอ่านอย่างเดียวโดยใช้`Protect` วิธีการของ`Document` วัตถุ วัตถุ
3.  ใช้`DocumentBuilder` คลาสเพื่อสร้างช่วงที่แก้ไขได้โดยการเพิ่ม`EditableRangeStart` วัตถุและ`EditableRangeEnd` วัตถุ วัตถุ
4.  เพิ่มเนื้อหาในช่วงที่แก้ไขได้โดยใช้`DocumentBuilder`.
5.  บันทึกเอกสารที่แก้ไขโดยใช้`Save` วิธีการของ`Document` วัตถุ วัตถุ

#### ถาม: ฉันสามารถมีขอบเขตที่แก้ไขได้แบบไม่จำกัดหลายส่วนในเอกสาร Word ได้หรือไม่

ตอบ: ได้ คุณสามารถมีขอบเขตที่สามารถแก้ไขได้แบบไม่จำกัดหลายขอบเขตในเอกสาร Word เพื่อให้บรรลุเป้าหมายนี้ คุณสามารถสร้างชุดได้หลายชุด`EditableRangeStart` และ`EditableRangeEnd` วัตถุที่ใช้`DocumentBuilder` ชั้นเรียน ออบเจ็กต์แต่ละชุดจะกำหนดขอบเขตที่แก้ไขได้แยกต่างหาก ซึ่งผู้ใช้สามารถแก้ไขเนื้อหาได้โดยไม่มีข้อจำกัดใดๆ

#### ถาม: ฉันสามารถซ้อนขอบเขตที่แก้ไขได้ภายในกันและกันได้หรือไม่

 ตอบ: ไม่ได้ คุณไม่สามารถซ้อนขอบเขตที่แก้ไขได้ภายในกันโดยใช้ Aspose.Words สำหรับ .NET แต่ละภูมิภาคที่แก้ไขได้กำหนดโดย`EditableRangeStart` และ`EditableRangeEnd` คู่ควรเป็นอิสระและไม่ทับซ้อนกันหรือซ้อนกันภายในภูมิภาคอื่นที่แก้ไขได้ ไม่รองรับขอบเขตที่แก้ไขได้แบบซ้อนกัน

#### ถาม: ฉันสามารถลบการป้องกันแบบอ่านอย่างเดียวออกจากเอกสารภายในขอบเขตที่แก้ไขได้หรือไม่

ตอบ: ไม่ได้ คุณไม่สามารถลบการป้องกันแบบอ่านอย่างเดียวออกจากเอกสารภายในขอบเขตที่แก้ไขได้ การป้องกันแบบอ่านอย่างเดียวจะถูกนำไปใช้กับเอกสารทั้งหมด และไม่สามารถลบออกได้ภายในขอบเขตที่แก้ไขได้เฉพาะ วัตถุประสงค์ของขอบเขตที่แก้ไขได้คือการอนุญาตให้มีการแก้ไขเนื้อหาในขณะที่ทำให้เอกสารโดยรวมเป็นแบบอ่านอย่างเดียว