---
title: ตารางที่จัดรูปแบบแล้ว
linktitle: ตารางที่จัดรูปแบบแล้ว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างและจัดรูปแบบตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนโดยละเอียดนี้
type: docs
weight: 10
url: /th/net/programming-with-tables/formatted-table/
---
## การแนะนำ

การสร้างและการจัดรูปแบบตารางในเอกสาร Word โดยทางโปรแกรมอาจดูเหมือนเป็นงานที่น่ากังวล แต่ด้วย Aspose.Words สำหรับ .NET จะทำให้ตรงไปตรงมาและจัดการได้ง่าย ในบทช่วยสอนนี้ เราจะอธิบายวิธีสร้างตารางที่จัดรูปแบบในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะครอบคลุมทุกอย่างตั้งแต่การตั้งค่าสภาพแวดล้อมของคุณไปจนถึงการบันทึกเอกสารของคุณด้วยตารางที่มีรูปแบบสวยงาม

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกโค้ด โปรดตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการ:

1. Aspose.Words สำหรับ .NET Library: ดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/net/).
2. สภาพแวดล้อมการพัฒนา: IDE เช่น Visual Studio
3. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework บนเครื่องของคุณ

## นำเข้าเนมสเปซ

ก่อนที่จะเขียนโค้ดจริง คุณต้องนำเข้าเนมสเปซที่จำเป็นก่อน:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

ขั้นแรก คุณต้องกำหนดเส้นทางที่จะบันทึกเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงที่คุณต้องการบันทึกเอกสาร

## ขั้นตอนที่ 2: เริ่มต้นเอกสารและ DocumentBuilder

ตอนนี้ เริ่มต้นเอกสารใหม่และวัตถุ DocumentBuilder

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 ที่`DocumentBuilder` เป็นคลาสตัวช่วยที่ทำให้กระบวนการสร้างเอกสารง่ายขึ้น

## ขั้นตอนที่ 3: เริ่มตาราง

 จากนั้นให้เริ่มสร้างตารางโดยใช้`StartTable` วิธี.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

จำเป็นต้องแทรกเซลล์เพื่อเริ่มตาราง

## ขั้นตอนที่ 4: ใช้การจัดรูปแบบทั้งตาราง

คุณสามารถใช้การจัดรูปแบบที่ส่งผลต่อทั้งตารางได้ ตัวอย่างเช่น การตั้งค่าการเยื้องซ้าย:

```csharp
table.LeftIndent = 20.0;
```

## ขั้นตอนที่ 5: จัดรูปแบบแถวส่วนหัว

ตั้งค่าความสูง การจัดตำแหน่ง และคุณสมบัติอื่นๆ สำหรับแถวส่วนหัว

```csharp
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");
```

ในขั้นตอนนี้ เราทำให้แถวส่วนหัวโดดเด่นด้วยการตั้งค่าสีพื้นหลัง ขนาดตัวอักษร และการจัดแนว

## ขั้นตอนที่ 6: แทรกเซลล์ส่วนหัวเพิ่มเติม

แทรกเซลล์เพิ่มเติมสำหรับแถวส่วนหัว:

```csharp
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");
builder.EndRow();
```

## ขั้นตอนที่ 7: จัดรูปแบบแถวเนื้อหา

หลังจากตั้งค่าส่วนหัวแล้ว ให้จัดรูปแบบเนื้อหาของตาราง:

```csharp
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;
```

## ขั้นตอนที่ 8: แทรกแถวเนื้อหา

แทรกแถวเนื้อหาด้วยเนื้อหา:

```csharp
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Row 1, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 1, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 1, Cell 3 Content");
builder.EndRow();
```

ทำซ้ำสำหรับแถวเพิ่มเติม:

```csharp
builder.InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Row 2, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 2, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 2, Cell 3 Content.");
builder.EndRow();
builder.EndTable();
```

## ขั้นตอนที่ 9: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารลงในไดเร็กทอรีที่ระบุ:

```csharp
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

เพื่อสร้างและบันทึกเอกสาร Word ด้วยตารางที่จัดรูปแบบแล้ว

## บทสรุป

และคุณก็ได้แล้ว! เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถสร้างตารางที่มีการจัดรูปแบบอย่างดีในเอกสาร Word โดยใช้ Aspose.Words for .NET ไลบรารีอันทรงพลังนี้ทำให้การจัดการเอกสาร Word โดยทางโปรแกรมเป็นเรื่องง่าย ช่วยคุณประหยัดเวลาและความพยายาม

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words for .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการสร้าง แก้ไข และแปลงเอกสาร Word โดยทางโปรแกรม

### ฉันสามารถใช้สีที่ต่างกันสำหรับแถวที่ต่างกันได้หรือไม่
ได้ คุณสามารถใช้การจัดรูปแบบที่แตกต่างกัน รวมถึงสี กับแถวหรือเซลล์ต่างๆ ได้

### Aspose.Words สำหรับ .NET ฟรีหรือไม่
 Aspose.Words สำหรับ .NET เป็นไลบรารีแบบชำระเงิน แต่คุณสามารถรับได้[ทดลองใช้ฟรี](https://releases.aspose.com/).

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Words สำหรับ .NET ได้อย่างไร
 คุณสามารถรับการสนับสนุนจาก[กำหนดฟอรัมชุมชน](https://forum.aspose.com/c/words/8).

### ฉันสามารถสร้างเอกสารประเภทอื่นด้วย Aspose.Words สำหรับ .NET ได้หรือไม่
ใช่ Aspose.Words สำหรับ .NET รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, HTML และ TXT