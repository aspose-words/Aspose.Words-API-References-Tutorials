---
title: สร้างตารางในเอกสาร Word
linktitle: สร้างตารางในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/add-content-using-documentbuilder/build-table/
---
ในบทช่วยสอนทีละขั้นตอนนี้ คุณจะได้เรียนรู้วิธีสร้างตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะแนะนำคุณตลอดกระบวนการและจัดเตรียมข้อมูลโค้ด C# ที่จำเป็นให้กับคุณ ในตอนท้ายของคู่มือนี้ คุณจะสามารถสร้างตารางที่มีการจัดรูปแบบและเนื้อหาแบบกำหนดเองได้โดยใช้คลาส DocumentBuilder

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Words สำหรับ .NET บนระบบของคุณ

## ขั้นตอนที่ 1: สร้างเอกสารใหม่
ในการเริ่มต้น ให้สร้างเอกสารใหม่โดยใช้คลาส Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: เริ่มตาราง
จากนั้น ใช้เมธอด StartTable ของคลาส DocumentBuilder เพื่อเริ่มสร้างตาราง:

```csharp
Table table = builder.StartTable();
```

## ขั้นตอนที่ 3: แทรกเซลล์และเพิ่มเนื้อหา
ตอนนี้คุณสามารถแทรกเซลล์ลงในตารางและเพิ่มเนื้อหาโดยใช้วิธีการ InsertCell และ Write ของคลาส DocumentBuilder ปรับแต่งการจัดรูปแบบเซลล์ตามต้องการ:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## ขั้นตอนที่ 4: สิ้นสุดแถว
หลังจากเพิ่มเนื้อหาลงในเซลล์ของแถวแรกแล้ว ให้ใช้วิธีการ EndRow ของคลาส DocumentBuilder เพื่อสิ้นสุดแถว:

```csharp
builder.EndRow();
```

## ขั้นตอนที่ 5: ปรับแต่งการจัดรูปแบบแถว
คุณสามารถปรับแต่งการจัดรูปแบบของแถวได้โดยการตั้งค่าคุณสมบัติของออบเจ็กต์ RowFormat และ CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## ขั้นตอนที่ 6: สิ้นสุดตาราง
หากต้องการทำให้ตารางสมบูรณ์ ให้ใช้วิธี EndTable ของคลาส DocumentBuilder:

```csharp
builder.EndTable();
```

### ตัวอย่างซอร์สโค้ดสำหรับการสร้างตารางโดยใช้ Aspose.Words สำหรับ .NET
นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการสร้างตารางโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีสร้างตารางในเอกสาร Word โดยใช้ Aspose.Words for .NET เรียบร้อยแล้ว เมื่อทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ดที่ให้มา คุณสามารถสร้างตารางด้วยการจัดรูปแบบแบบกำหนดเองได้แล้ว

### คำถามที่พบบ่อยสำหรับการสร้างตารางในเอกสาร word

#### ถาม: Aspose.Words สำหรับ .NET คืออะไร

ตอบ: Aspose.Words สำหรับ .NET เป็นไลบรารีการประมวลผลเอกสารที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง อ่าน แก้ไข และแปลงเอกสาร Microsoft Word ในแอปพลิเคชัน .NET โดยทางโปรแกรม มีคุณลักษณะมากมายในการทำงานกับเอกสาร Word เช่น การจัดการข้อความ การสร้างตาราง การป้องกันเอกสาร การจัดรูปแบบ และอื่นๆ

#### ถาม: ฉันจะสร้างตารางในเอกสาร Word โดยใช้ Aspose.Words for .NET ได้อย่างไร

ตอบ: เมื่อต้องการสร้างตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:
1.  สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`DocumentBuilder` วัตถุ.
2.  ใช้`StartTable` วิธีการของ`DocumentBuilder`คลาสเพื่อเริ่มสร้างตาราง
3.  แทรกเซลล์ลงในตารางและเพิ่มเนื้อหาโดยใช้`InsertCell` และ`Write` วิธีการของ`DocumentBuilder` ระดับ.
4.  จบแถวโดยใช้`EndRow` วิธีการของ`DocumentBuilder` ระดับ.
5.  ปรับแต่งการจัดรูปแบบแถวโดยการตั้งค่าคุณสมบัติของ`RowFormat` และ`CellFormat` วัตถุ
6.  ปิดท้ายตารางโดยใช้`EndTable` วิธีการของ`DocumentBuilder` ระดับ.
7. บันทึกเอกสาร

#### ถาม: ฉันจะปรับแต่งการจัดรูปแบบของตารางและเซลล์ได้อย่างไร

 ตอบ: คุณสามารถปรับแต่งการจัดรูปแบบของตารางและเซลล์ได้โดยการตั้งค่าคุณสมบัติต่างๆ ของ`RowFormat` และ`CellFormat` วัตถุ ตัวอย่างเช่น คุณสามารถปรับการจัดแนวเซลล์ การวางแนวข้อความในแนวตั้งและแนวนอน ความสูงของเซลล์ ความสูงของแถว และอื่นๆ ด้วยการใช้คุณสมบัติเหล่านี้ คุณสามารถทำให้ตารางและเนื้อหามีลักษณะที่ต้องการได้

#### ถาม: ฉันสามารถสร้างตารางที่ซับซ้อนด้วยเซลล์ที่ผสานและฟีเจอร์ขั้นสูงอื่นๆ ได้หรือไม่

 ตอบ: ใช่ Aspose.Words สำหรับ .NET มีคุณสมบัติขั้นสูงในการสร้างตารางที่ซับซ้อน รวมถึงการรองรับเซลล์ที่ผสาน ตารางที่ซ้อนกัน และเค้าโครงตารางที่ซับซ้อน คุณสามารถใช้`MergeCells` วิธีการรวมเซลล์`StartTable`วิธีสร้างตารางแบบซ้อน และวิธีการอื่นๆ เพื่อให้ได้โครงสร้างตารางที่ต้องการ

#### ถาม: Aspose.Words สำหรับ .NET เข้ากันได้กับรูปแบบเอกสาร Word ที่แตกต่างกันหรือไม่

ตอบ: ได้ Aspose.Words สำหรับ .NET เข้ากันได้กับรูปแบบเอกสาร Word ที่หลากหลาย รวมถึง DOC, DOCX, RTF และอื่นๆ รองรับทั้งรูปแบบเดิม (DOC) และรูปแบบที่ใช้ XML สมัยใหม่ (DOCX) และช่วยให้คุณสามารถทำงานกับเอกสารในรูปแบบที่แตกต่างกันได้โดยไม่มีปัญหาใด ๆ

#### ถาม: ฉันจะหาข้อมูลและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Words สำหรับ .NET ได้ที่ไหน

 ตอบ: คุณสามารถดูเอกสารประกอบและตัวอย่างโค้ดที่ครอบคลุมได้ที่[การอ้างอิง API](https://reference.aspose.com/words/net/). เอกสารนี้จะให้ข้อมูลโดยละเอียดเกี่ยวกับคุณลักษณะของไลบรารีและวิธีการใช้งานในแอปพลิเคชัน .NET ของคุณ