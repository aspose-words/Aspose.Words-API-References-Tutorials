---
title: แปลงฟิลด์ในย่อหน้า
linktitle: แปลงฟิลด์ในย่อหน้า
second_title: Aspose.Words API การประมวลผลเอกสาร
description: แปลงฟิลด์ IF เป็นข้อความธรรมดาในย่อหน้าด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fields/convert-fields-in-paragraph/
---

ต่อไปนี้เป็นบทช่วยสอนที่สาธิตวิธีการใช้คุณสมบัติการแปลงฟิลด์เป็นย่อหน้าด้วย Aspose.Words สำหรับ .NET รหัสนี้จะแปลงฟิลด์ประเภท IF ทั้งหมดที่พบในย่อหน้าสุดท้ายของเอกสารเป็นข้อความธรรมดา ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจและเรียกใช้โค้ดนี้

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Words สำหรับ .NET และตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อนที่จะเริ่มต้น

## ขั้นตอนที่ 1: นำเข้าข้อมูลอ้างอิง

หากต้องการใช้ Aspose.Words ในโปรเจ็กต์ของคุณ คุณจะต้องเพิ่มข้อมูลอ้างอิงที่จำเป็น ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words ในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ก่อนที่คุณจะสามารถแปลงฟิลด์ได้ คุณต้องโหลดเอกสารที่มีฟิลด์ที่จะแปลงก่อน อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีที่มีเอกสาร ต่อไปนี้เป็นวิธีอัปโหลดเอกสาร:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Linked fields.docx");
```

แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: การแปลงฟิลด์เป็นข้อความ

เมื่อโหลดเอกสารแล้ว เราสามารถดำเนินการแปลงฟิลด์ประเภทเป็นข้อความธรรมดาได้ ในตัวอย่างนี้ เรากำหนดเป้าหมายเฉพาะฟิลด์ที่มีอยู่ในย่อหน้าสุดท้ายของเอกสารเท่านั้น นี่คือรหัสที่ทำการแปลงนี้:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

รหัสนี้ใช้การรวมกันของวิธี LINQ เพื่อกรองฟิลด์ในย่อหน้าสุดท้ายของเอกสาร จากนั้นแปลงเป็นข้อความธรรมดาโดยการเรียก`Unlink()` วิธี.

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข

 เมื่อแปลงฟิลด์แล้ว คุณสามารถบันทึกเอกสารที่แก้ไขได้ ใช้`Save()` วิธีการนี้ นี่คือตัวอย่าง:

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับการสำรองข้อมูล

### ตัวอย่างซอร์สโค้ดสำหรับการแปลงฟิลด์ในย่อหน้าโดยใช้ Aspose.Words สำหรับ .NET

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Linked fields.docx");

// แปลงฟิลด์ IF ให้เป็นข้อความธรรมดาในย่อหน้าสุดท้ายของเอกสาร
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// บันทึกเอกสารที่แก้ไข
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### คำถามที่พบบ่อย

#### ถาม: ฟิลด์ Conversion ใน Aspose.Words คืออะไร

ตอบ: ฟิลด์การแปลงใน Aspose.Words เป็นประเภทของฟิลด์ที่แปลงค่าหรือนิพจน์เป็นรูปแบบหรือชนิดข้อมูลอื่น ตัวอย่างเช่น คุณสามารถใช้ฟิลด์ Conversion เพื่อแปลงวันที่เป็นรูปแบบเฉพาะ ตัวเลขเป็นข้อความ หรือดำเนินการแปลงประเภทอื่นๆ

#### ถาม: จะแทรกฟิลด์การแปลงในย่อหน้าด้วย Aspose.Words ได้อย่างไร

ตอบ: หากต้องการแทรกฟิลด์ Conversion ในย่อหน้าด้วย Aspose.Words คุณสามารถทำตามขั้นตอนเหล่านี้:

1. นำเข้าคลาสเอกสารจากเนมสเปซ Aspose.Words
2. สร้างอินสแตนซ์ของเอกสารโดยการโหลดเอกสารที่มีอยู่ของคุณ
3. รับย่อหน้าที่คุณต้องการแทรกฟิลด์การแปลง
4. ใช้เมธอด InsertField เพื่อแทรกฟิลด์การแปลงด้วยไวยากรณ์ที่ถูกต้อง

#### ถาม: Aspose.Words รองรับรูปแบบการแปลงใดบ้าง

ตอบ: Aspose.Words รองรับรูปแบบการแปลงที่หลากหลายในช่องต่างๆ รวมถึงรูปแบบวันที่ รูปแบบตัวเลข รูปแบบข้อความ รูปแบบสกุลเงิน รูปแบบเปอร์เซ็นต์ และอื่นๆ คุณสามารถตรวจสอบเอกสารประกอบของ Aspose.Words เพื่อดูรายการรูปแบบการแปลงที่มีอยู่ทั้งหมด

#### ถาม: จะอัปเดตฟิลด์การแปลงในเอกสาร Word ด้วย Aspose.Words ได้อย่างไร

ตอบ: หากต้องการอัปเดตฟิลด์การแปลงในเอกสาร Word ด้วย Aspose.Words คุณสามารถใช้เมธอด UpdateFields ได้ วิธีนี้จะวนซ้ำเอกสารและอัปเดตช่องทั้งหมด รวมถึงช่องการแปลง โดยคำนวณค่าใหม่ตามข้อมูลปัจจุบัน