---
title: รับชื่อฟิลด์จดหมายเวียน
linktitle: รับชื่อฟิลด์จดหมายเวียน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรับชื่อฟิลด์จดหมายเวียนในเอกสาร Word ของคุณด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-fields/get-mail-merge-field-names/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่าง ซึ่งใช้ฟีเจอร์ "รับชื่อเขตข้อมูลผสาน" ของ Aspose.Words สำหรับ .NET อย่าลืมปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในโค้ดที่ให้มา คุณต้องระบุไดเร็กทอรีของเอกสารของคุณ แทนที่ค่า "YOUR DOCUMENT DIRECTORY" ด้วยเส้นทางที่เหมาะสมไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ขั้นตอนแรกคือการโหลดเอกสารในตำแหน่งที่คุณต้องการรับชื่อเขตข้อมูลผสาน

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

อย่าลืมแทนที่ "ไฟล์เอกสารของคุณ" ด้วยชื่อไฟล์ของคุณเอง

## ขั้นตอนที่ 3: รับชื่อเขตข้อมูลผสาน

 เราใช้`GetFieldNames()` วิธีการรับอาร์เรย์ที่มีชื่อของเขตข้อมูลผสานที่มีอยู่ในเอกสาร

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 ที่`fieldNames` ขณะนี้ตัวแปรมีชื่อของเขตข้อมูลผสานแล้ว

### ตัวอย่างซอร์สโค้ดสำหรับรับชื่อฟิลด์ผสานด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// รับชื่อเขตข้อมูลผสาน
string[] fieldNames = doc.MailMerge.GetFieldNames();

// แสดงจำนวนเขตข้อมูลผสาน
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 ในตัวอย่างนี้ เราโหลดเอกสาร ได้รับชื่อเขตข้อมูลผสานโดยใช้`GetFieldNames()` และแสดงจำนวนช่องผสานที่มีอยู่ในเอกสาร

นี่เป็นการสรุปคำแนะนำของเราเกี่ยวกับการใช้ฟีเจอร์ "รับชื่อเขตข้อมูลผสาน" กับ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### คำถามที่ 1: จดหมายเวียนใน Aspose.Words คืออะไร

จดหมายเวียนใน Aspose.Words เป็นกระบวนการในการรวมข้อมูลจากแหล่งภายนอก (เช่น สเปรดชีต Excel หรือฐานข้อมูล) ด้วยเทมเพลตเอกสาร Word เพื่อสร้างเอกสารที่เป็นส่วนตัว สิ่งนี้อำนวยความสะดวกในการสร้างจดหมาย รายงาน และเอกสารอื่นที่คล้ายคลึงกันโดยอัตโนมัติ

#### Q2: ฉันจะได้รับรายการเขตข้อมูลจดหมายเวียนที่มีอยู่ในเอกสาร Word ได้อย่างไร

เมื่อต้องการรับรายการเขตข้อมูลจดหมายเวียนที่มีอยู่ในเอกสาร Word คุณสามารถทำตามขั้นตอนเหล่านี้:

1. นำเข้าคลาส Document และ MailMergeFieldNames จากเนมสเปซ Aspose.Words
2. สร้างอินสแตนซ์เอกสารโดยการโหลดเอกสาร Word ของคุณ
3. ใช้เมธอด GetMailMergeFieldNames ของวัตถุเอกสารเพื่อรับรายการเขตข้อมูลจดหมายเวียนที่พร้อมใช้งาน

นี่คือโค้ดตัวอย่างเพื่อแสดงกระบวนการ:

```csharp
// นำเข้าเนมสเปซที่จำเป็น
using Aspose.Words;
using Aspose.Words.MailMerging;

// โหลดเอกสารที่มีอยู่
Document document = new Document("FilePath");

// รับรายการเขตข้อมูลจดหมายเวียน
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// วนไปตามเขตข้อมูลจดหมายเวียนที่มีอยู่
foreach (string fieldName in fieldNames)
{
     // ทำอะไรสักอย่างกับชื่อฟิลด์
     Console.WriteLine(fieldName);
}
```
### คำถามที่พบบ่อย

#### ถาม: จดหมายเวียนใน Aspose.Words คืออะไร

ตอบ: จดหมายเวียนใน Aspose.Words เป็นกระบวนการในการผสานข้อมูลจากแหล่งภายนอก (เช่น สเปรดชีต Excel หรือฐานข้อมูล) ด้วยเทมเพลตเอกสาร Word เพื่อสร้างเอกสารที่เป็นส่วนตัว สิ่งนี้อำนวยความสะดวกในการสร้างจดหมาย รายงาน และเอกสารอื่นที่คล้ายคลึงกันโดยอัตโนมัติ

#### ถาม: ฉันจะรับรายการเขตข้อมูลจดหมายเวียนที่มีอยู่ในเอกสาร Word ได้อย่างไร

ตอบ: เมื่อต้องการรับรายการเขตข้อมูลจดหมายเวียนที่มีอยู่ในเอกสาร Word คุณสามารถทำตามขั้นตอนเหล่านี้:

1. นำเข้าคลาส Document และ MailMergeFieldNames จากเนมสเปซ Aspose.Words
2. สร้างอินสแตนซ์เอกสารโดยการโหลดเอกสาร Word ของคุณ
3. ใช้เมธอด GetMailMergeFieldNames ของวัตถุเอกสารเพื่อรับรายการเขตข้อมูลจดหมายเวียนที่พร้อมใช้งาน

#### ถาม: ฉันสามารถรับฟิลด์จดหมายเวียนจากแหล่งข้อมูลภายนอก เช่น สเปรดชีต Excel ได้หรือไม่

ตอบ: ได้ คุณสามารถรับเขตข้อมูลจดหมายเวียนได้จากแหล่งข้อมูลภายนอก เช่น สเปรดชีต Excel สำหรับสิ่งนี้ คุณสามารถใช้คุณสมบัติการผูกข้อมูลของ Aspose.Words เพื่อสร้างการเชื่อมต่อกับแหล่งข้อมูลและรับชื่อของฟิลด์ที่มีอยู่

#### ถาม: เป็นไปได้หรือไม่ที่จะกรองฟิลด์จดหมายเวียนตามเกณฑ์ที่กำหนด

ตอบ: ได้ คุณสามารถกรองฟิลด์จดหมายเวียนตามเกณฑ์ที่กำหนดได้ คุณสามารถใช้นิพจน์ทั่วไปหรือเงื่อนไขเฉพาะเพื่อกรองเขตข้อมูลจดหมายเวียน และรับเฉพาะเขตข้อมูลที่ตรงกับเกณฑ์เฉพาะของคุณเท่านั้น

#### ถาม: ฉันจะจัดการฟิลด์จดหมายเวียนใน Aspose.Words ได้อย่างไร

ตอบ: หากต้องการจัดการเขตข้อมูลจดหมายเวียนใน Aspose.Words คุณสามารถใช้วิธีการและคุณสมบัติที่ได้รับจากวัตถุ Document และ MailMergeField คุณสามารถเพิ่ม ลบ หรืออัปเดตฟิลด์จดหมายเวียน ตลอดจนดึงข้อมูลและแก้ไขค่าที่เกี่ยวข้องกับฟิลด์ได้