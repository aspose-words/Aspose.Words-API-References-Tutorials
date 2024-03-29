---
title: แปลงฟิลด์ในร่างกาย
linktitle: แปลงฟิลด์ในร่างกาย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้ Aspose.Words สำหรับ .NET เพื่อแปลงช่องเพจเป็นข้อความในเนื้อหาของเอกสาร Word
type: docs
weight: 10
url: /th/net/working-with-fields/convert-fields-in-body/
---

ในบทช่วยสอนทีละขั้นตอนนี้ เราจะอธิบายวิธีใช้คุณสมบัติ ConvertFieldsInBody ของ Aspose.Words สำหรับ .NET โดยใช้ซอร์สโค้ด C# ที่ให้มา คุณลักษณะนี้ช่วยให้คุณสามารถแปลงฟิลด์เฉพาะในเนื้อความของเอกสารของคุณให้เป็นข้อความธรรมดา ทำให้ประมวลผลเอกสารของคุณได้ง่ายขึ้น ทำตามขั้นตอนด้านล่างเพื่อใช้คุณสมบัตินี้อย่างมีประสิทธิภาพ

## ขั้นตอนที่ 1: ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Words สำหรับ .NET และมีเอกสารที่พร้อมสำหรับการประมวลผล ตรวจสอบให้แน่ใจว่าคุณมีเส้นทางไดเรกทอรีไปยังเอกสารของคุณ

## ขั้นตอนที่ 2: ใส่เอกสาร

เริ่มต้นด้วยการประกาศตัวแปรสำหรับเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ จากนั้นใช้ตัวแปรนั้นเพื่อเริ่มต้นออบเจ็กต์ Document จากเอกสารที่ระบุ ในตัวอย่างของเรา เอกสารชื่อ "Linked fields.docx"

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Linked fields.docx");
```

## ขั้นตอนที่ 3: แปลงฟิลด์หน้าเป็นข้อความธรรมดา

 เมื่อโหลดเอกสารแล้ว เราก็ไปยังขั้นตอนการแปลงได้เลย หากต้องการแปลงช่องหน้าเป็นข้อความธรรมดาในส่วนเนื้อหาของส่วนแรก คุณสามารถใช้`Range.Fields` วิธีการรับฟิลด์ทั้งหมดในช่วงที่ระบุ จากนั้นกรองฟิลด์ประเภทออก`FieldType.FieldPage` . จากนั้นคุณสามารถใช้`ForEach` วิธีการวนซ้ำแต่ละฟิลด์และเรียก`Unlink()` วิธีแปลงเป็นข้อความธรรมดา

```csharp
// ส่งพารามิเตอร์ที่เหมาะสมเพื่อแปลงฟิลด์หน้าเป็นข้อความธรรมดาในเนื้อหาของส่วนแรก
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข

เมื่อคุณแปลงฟิลด์หน้าเป็นข้อความธรรมดาแล้ว คุณสามารถบันทึกเอกสารที่แก้ไขได้โดยใช้`Save()` วิธีการและระบุเส้นทางและชื่อของไฟล์ที่ส่งออก ในตัวอย่างของเรา เราบันทึกเป็น "WorkingWithFields.ConvertFieldsInBody.docx"

```csharp
// บันทึกเอกสารที่แก้ไข
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการแปลงฟิลด์ในเนื้อหาด้วย Aspose.Words สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดแบบเต็มสำหรับการแปลงฟิลด์ลงในเนื้อหาโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Linked fields.docx");

// ส่งพารามิเตอร์ที่เหมาะสมเพื่อแปลงฟิลด์หน้าเป็นข้อความธรรมดาในเนื้อหาของส่วนแรก
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### คำถามที่พบบ่อย

#### ถาม: Aspose.Words เข้ากันได้กับ Microsoft Word เวอร์ชันต่างๆ หรือไม่

ตอบ: ได้ Aspose.Words เข้ากันได้กับ Microsoft Word เวอร์ชันต่างๆ รวมถึง Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 และ Word 2019

#### ถาม: Aspose.Words สามารถจัดการโครงสร้างฟิลด์ที่ซับซ้อนได้หรือไม่

ตอบ: แน่นอน! Aspose.Words ให้การสนับสนุนอย่างกว้างขวางสำหรับโครงสร้างฟิลด์ที่ซับซ้อน รวมถึงฟิลด์ที่ซ้อนกัน การคำนวณ และนิพจน์ตามเงื่อนไข คุณสามารถใช้ประโยชน์จาก API อันทรงพลังเพื่อทำงานกับโครงสร้างฟิลด์ประเภทใดก็ได้

#### ถาม: Aspose.Words รองรับการดำเนินการอัปเดตภาคสนามหรือไม่

ตอบ: ได้ Aspose.Words ช่วยให้คุณสามารถอัปเดตฟิลด์โดยทางโปรแกรมได้ คุณสามารถอัปเดตค่าฟิลด์ รีเฟรชการคำนวณ และดำเนินการอื่นๆ ที่เกี่ยวข้องกับฟิลด์โดยใช้ API ได้อย่างง่ายดาย

#### ถาม: ฉันสามารถแปลงฟิลด์เป็นข้อความธรรมดาโดยใช้ Aspose.Words ได้หรือไม่

ตอบ: แน่นอน! Aspose.Words จัดเตรียมวิธีการแปลงฟิลด์เป็นข้อความธรรมดา สิ่งนี้มีประโยชน์เมื่อคุณต้องการแยกเนื้อหาโดยไม่มีการจัดรูปแบบหรือฟังก์ชันที่เกี่ยวข้องกับฟิลด์

#### ถาม: เป็นไปได้ไหมที่จะสร้างเอกสาร Word ด้วยฟิลด์ไดนามิกโดยใช้ Aspose.Words

ตอบ: แน่นอน! Aspose.Words นำเสนอคุณสมบัติที่แข็งแกร่งในการสร้างเอกสาร Word พร้อมฟิลด์ไดนามิก คุณสามารถสร้างเทมเพลตที่มีฟิลด์ที่กำหนดไว้ล่วงหน้าและเติมข้อมูลแบบไดนามิก ซึ่งเป็นโซลูชันการสร้างเอกสารที่ยืดหยุ่นและมีประสิทธิภาพ