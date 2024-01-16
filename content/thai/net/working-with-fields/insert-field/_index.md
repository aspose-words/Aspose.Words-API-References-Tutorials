---
title: แทรกฟิลด์
linktitle: แทรกฟิลด์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกฟิลด์ลงในเอกสาร Word ของคุณด้วย Aspose.Words for .NET ปรับแต่งเอกสารของคุณด้วยฟิลด์ไดนามิก
type: docs
weight: 10
url: /th/net/working-with-fields/insert-field/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่าง ซึ่งใช้ฟีเจอร์ "แทรกฟิลด์" ของ Aspose.Words สำหรับ .NET อย่าลืมปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

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

## ขั้นตอนที่ 3: การแทรกฟิลด์

 เราใช้`InsertField()` วิธีการของ DocumentBuilder เพื่อแทรกฟิลด์ลงในเอกสาร ในตัวอย่างนี้ เราแทรกเขตข้อมูลผสาน (MERGEFIELD) ด้วยชื่อเขตข้อมูล "MyFieldName" และรูปแบบการผสาน

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกฟิลด์ด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสารและ DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกฟิลด์
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

ในตัวอย่างนี้ เราได้สร้างเอกสารใหม่ เริ่มต้น DocumentBuilder แล้วแทรกฟิลด์ผสานที่มีชื่อฟิลด์ "MyFieldName" และรูปแบบผสาน จากนั้นเอกสารจะถูกบันทึกด้วยชื่อไฟล์ที่ระบุ

นี่เป็นการสรุปคำแนะนำของเราเกี่ยวกับการใช้ฟีเจอร์ "แทรกฟิลด์" กับ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: เขตข้อมูลใน Word คืออะไร

ตอบ: ช่องใน Word เป็นองค์ประกอบที่ช่วยให้คุณสามารถแทรกและจัดการข้อมูลแบบไดนามิกในเอกสารได้ สามารถใช้แสดงข้อมูลตัวแปร เช่น วันที่ เลขหน้า ตาราง สูตรทางคณิตศาสตร์ เป็นต้น

#### ถาม: จะแทรกฟิลด์ในเอกสาร Word ได้อย่างไร

ตอบ: หากต้องการแทรกฟิลด์ในเอกสาร Word คุณสามารถทำตามขั้นตอนเหล่านี้:

1. วางเคอร์เซอร์ของคุณในตำแหน่งที่คุณต้องการแทรกฟิลด์
2. ไปที่แท็บ "แทรก" ใน Ribbon
3. คลิกปุ่ม "ฟิลด์" ในกลุ่ม "ข้อความ" เพื่อเปิดกล่องโต้ตอบฟิลด์
4. เลือกประเภทของฟิลด์ที่คุณต้องการแทรกจากรายการแบบเลื่อนลง
5. กำหนดค่าตัวเลือกฟิลด์ตามต้องการ
6. คลิกปุ่ม "ตกลง" เพื่อแทรกฟิลด์ลงในเอกสารของคุณ

#### ถาม: ประเภทฟิลด์ที่ใช้กันทั่วไปใน Word คืออะไร

ตอบ: Word มีประเภทเขตข้อมูลที่หลากหลายที่คุณสามารถใช้ในเอกสารของคุณได้ ต่อไปนี้เป็นประเภทฟิลด์ที่ใช้กันทั่วไปบางส่วน:

- วันที่และเวลา: แสดงวันที่และเวลาปัจจุบัน
- หมายเลขหน้า: แสดงหมายเลขหน้าปัจจุบัน
- สารบัญ: สร้างสารบัญโดยอัตโนมัติตามสไตล์ของชื่อของคุณ
- การคำนวณ: ทำการคำนวณทางคณิตศาสตร์โดยใช้สูตร
- ข้อความเติม: สร้างข้อความแบบสุ่มเพื่อเติมเอกสารของคุณ

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของฟิลด์ใน Word ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของฟิลด์ใน Word ได้โดยใช้ตัวเลือกการจัดรูปแบบที่มีอยู่ ตัวอย่างเช่น คุณสามารถเปลี่ยนแบบอักษร ขนาด สี และลักษณะของข้อความในช่องได้ คุณยังสามารถใช้เอฟเฟ็กต์การจัดรูปแบบ เช่น ตัวหนา ตัวเอียง และขีดเส้นใต้ได้
  