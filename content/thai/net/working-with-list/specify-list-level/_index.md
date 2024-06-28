---
title: ระบุระดับรายการ
linktitle: ระบุระดับรายการ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีระบุระดับรายการในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-list/specify-list-level/
---

ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแสดงวิธีระบุระดับรายการในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง

 ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่า Aspose.Words สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Releases]https://releases.aspose.com/words/net/

## ขั้นตอนที่ 1: การสร้างเอกสารและเครื่องมือสร้างเอกสาร

ขั้นแรก สร้างเอกสารใหม่และตัวสร้างเอกสารที่เกี่ยวข้อง:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การสร้างและการใช้รายการลำดับเลข

จากนั้น สร้างรายการลำดับเลขตามหนึ่งในเทมเพลตรายการของ Microsoft Word และนำไปใช้กับย่อหน้าปัจจุบันในตัวสร้างเอกสาร:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## ขั้นตอนที่ 3: รายการข้อกำหนดระดับ

 ใช้ตัวสร้างเอกสาร`ListLevelNumber` คุณสมบัติเพื่อระบุระดับรายการและเพิ่มข้อความลงในย่อหน้า:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

ทำซ้ำขั้นตอนเหล่านี้เพื่อระบุระดับรายการและเพิ่มข้อความในแต่ละระดับ

## ขั้นตอนที่ 4: การสร้างและการใช้รายการสัญลักษณ์แสดงหัวข้อย่อย

คุณยังสร้างและใช้รายการสัญลักษณ์แสดงหัวข้อย่อยได้โดยใช้เทมเพลตรายการของ Microsoft Word รายการใดรายการหนึ่ง:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## ขั้นตอนที่ 5: การเพิ่มข้อความในระดับรายการสัญลักษณ์แสดงหัวข้อย่อย

 ใช้`ListLevelNumber` คุณสมบัติอีกครั้งเพื่อระบุระดับรายการสัญลักษณ์แสดงหัวข้อย่อยและเพิ่มข้อความ:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## ขั้นตอนที่ 6: หยุดการจัดรูปแบบรายการ

 หากต้องการหยุดการจัดรูปแบบรายการ ให้ตั้งค่า`null` ไปที่`List`คุณสมบัติของเครื่องสร้างเอกสาร:

```csharp
builder. ListFormat. List = null;
```

## ขั้นตอนที่ 7: บันทึกเอกสารที่แก้ไข

บันทึกเอกสารที่แก้ไข:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

ดังนั้น! คุณได้ระบุระดับรายการในเอกสาร Word เรียบร้อยแล้วโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดเพื่อระบุระดับรายการ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// สร้างรายการลำดับเลขโดยยึดตามเทมเพลตรายการ Microsoft Word รายการใดรายการหนึ่ง
//และนำไปใช้กับย่อหน้าปัจจุบันของตัวสร้างเอกสาร
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// มีเก้าระดับในรายการนี้ มาลองกันทั้งหมดเลย
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// สร้างรายการสัญลักษณ์แสดงหัวข้อย่อยโดยยึดตามเทมเพลตรายการ Microsoft Word รายการใดรายการหนึ่ง
//และนำไปใช้กับย่อหน้าปัจจุบันของตัวสร้างเอกสาร
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// นี่เป็นวิธีหยุดการจัดรูปแบบรายการ
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### คำถามที่พบบ่อย

#### ถาม: ฉันจะระบุระดับรายการใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการระบุระดับรายการใน Aspose.Words คุณต้องสร้างอินสแตนซ์ของ`List` ชั้นเรียนและมอบรายการลำดับเลขให้กับมัน จากนั้นคุณสามารถใช้`Paragraph.ListFormat.ListLevelNumber` คุณสมบัติเพื่อระบุระดับของแต่ละรายการ คุณสามารถเชื่อมโยงรายการนี้กับส่วนของเอกสารของคุณเพื่อให้รายการมีระดับที่ต้องการ

#### ถาม: เป็นไปได้ไหมที่จะเปลี่ยนรูปแบบการกำหนดหมายเลขของรายการใน Aspose.Words

 ตอบ: ได้ คุณสามารถเปลี่ยนรูปแบบลำดับเลขของรายการใน Aspose.Words ได้ ที่`ListLevel` class มีคุณสมบัติหลายประการสำหรับสิ่งนี้ เช่น`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`ฯลฯ คุณสามารถใช้คุณสมบัติเหล่านี้เพื่อตั้งค่ารูปแบบการกำหนดหมายเลขสำหรับรายการ เช่น เลขอารบิค เลขโรมัน ตัวอักษร ฯลฯ

#### ถาม: ฉันสามารถเพิ่มระดับเพิ่มเติมในรายการลำดับเลขใน Aspose.Words ได้หรือไม่

 ตอบ: ได้ คุณสามารถเพิ่มระดับเพิ่มเติมให้กับรายการลำดับเลขใน Aspose.Words ได้ ที่`ListLevel`class ช่วยให้คุณสามารถตั้งค่าคุณสมบัติการจัดรูปแบบสำหรับแต่ละระดับของรายการได้ คุณสามารถตั้งค่าตัวเลือกต่างๆ เช่น คำนำหน้า ส่วนต่อท้าย การจัดตำแหน่ง การเยื้อง ฯลฯ ซึ่งจะทำให้คุณสามารถสร้างรายการที่มีลำดับชั้นได้หลายระดับ


