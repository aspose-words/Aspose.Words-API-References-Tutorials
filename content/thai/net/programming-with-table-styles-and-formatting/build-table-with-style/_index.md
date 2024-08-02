---
title: สร้างโต๊ะอย่างมีสไตล์
linktitle: สร้างโต๊ะอย่างมีสไตล์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างและจัดรูปแบบตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนที่ครอบคลุมนี้
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/build-table-with-style/
---
## การแนะนำ

การสร้างเอกสารที่มีสไตล์และเป็นมืออาชีพมักต้องการมากกว่าแค่ข้อความธรรมดา ตารางเป็นวิธีที่ยอดเยี่ยมในการจัดระเบียบข้อมูล แต่การทำให้ตารางดูน่าสนใจนั้นเป็นความท้าทายที่แตกต่างไปจากเดิมอย่างสิ้นเชิง ป้อน Aspose.Words สำหรับ .NET! ในบทช่วยสอนนี้ เราจะเจาะลึกถึงวิธีสร้างตารางอย่างมีสไตล์ เพื่อทำให้เอกสาร Word ของคุณดูสวยงามและเป็นมืออาชีพ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะอธิบายคำแนะนำทีละขั้นตอน เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการ:

1.  Aspose.Words สำหรับ .NET: หากคุณยังไม่ได้ดาวน์โหลด ให้ดาวน์โหลดและติดตั้ง[Aspose.Words สำหรับ .NET](https://releases.aspose.com/words/net/).
2. สภาพแวดล้อมการพัฒนา: คุณควรมีการตั้งค่าสภาพแวดล้อมการพัฒนา Visual Studio เป็นตัวเลือกที่ยอดเยี่ยมสำหรับบทช่วยสอนนี้
3. ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับการเขียนโปรแกรม C# จะช่วยให้คุณปฏิบัติตามได้ง่ายขึ้น

## นำเข้าเนมสเปซ

ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่จำเป็น สิ่งนี้จะทำให้คุณสามารถเข้าถึงคลาสและวิธีการที่จำเป็นในการจัดการเอกสาร Word

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## ขั้นตอนที่ 1: สร้างเอกสารใหม่และ DocumentBuilder

 ก่อนอื่น คุณต้องสร้างเอกสารใหม่และก`DocumentBuilder` วัตถุ. นี้`DocumentBuilder` จะช่วยคุณสร้างตารางในเอกสารของคุณ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: เริ่มสร้างตาราง

ตอนนี้เรามีเอกสารและตัวสร้างพร้อมแล้ว เรามาเริ่มสร้างตารางกันดีกว่า

```csharp
Table table = builder.StartTable();
```

## ขั้นตอนที่ 3: แทรกแถวแรก

ตารางที่ไม่มีแถวเป็นเพียงโครงสร้างว่างเปล่า เราจำเป็นต้องแทรกอย่างน้อยหนึ่งแถวก่อนจึงจะสามารถตั้งค่าการจัดรูปแบบตารางได้

```csharp
builder.InsertCell();
```

## ขั้นตอนที่ 4: ตั้งค่าสไตล์ตาราง

 เมื่อแทรกเซลล์แรกแล้ว ก็ถึงเวลาเพิ่มสไตล์ให้กับตารางของเรา เราจะใช้`StyleIdentifier` เพื่อใช้สไตล์ที่กำหนดไว้ล่วงหน้า

```csharp
// ตั้งค่าสไตล์ตารางที่ใช้ตามตัวระบุสไตล์เฉพาะ
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## ขั้นตอนที่ 5: กำหนดตัวเลือกสไตล์

ตัวเลือกสไตล์ตารางจะกำหนดว่าส่วนใดของตารางจะถูกจัดสไตล์ ตัวอย่างเช่น เราสามารถเลือกจัดสไตล์คอลัมน์แรก แถบแถว และแถวแรกได้

```csharp
// ใช้คุณลักษณะที่ควรจัดรูปแบบตามสไตล์
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## ขั้นตอนที่ 6: ปรับตารางให้พอดีกับเนื้อหา

 เพื่อให้แน่ใจว่าโต๊ะของเราดูเรียบร้อยและเป็นระเบียบ เราสามารถใช้`AutoFit` วิธีปรับตารางให้พอดีกับเนื้อหา

```csharp
table.AutoFit(AutoFitBehavior.AutoFitToContents);
```

## ขั้นตอนที่ 7: ใส่ข้อมูลลงในตาราง

ตอนนี้ได้เวลากรอกข้อมูลลงในตารางของเราแล้ว เราจะเริ่มต้นด้วยแถวส่วนหัวแล้วเพิ่มข้อมูลตัวอย่างบางส่วน

### การแทรกแถวส่วนหัว

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writeln("Quantity (kg)");
builder.EndRow();
```

#### การแทรกแถวข้อมูล

```csharp
builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writeln("40");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();
```

## ขั้นตอนที่ 8: บันทึกเอกสาร

หลังจากใส่ข้อมูลทั้งหมดแล้ว ขั้นตอนสุดท้ายคือการบันทึกเอกสาร

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## บทสรุป

และคุณก็ได้แล้ว! คุณได้สร้างตารางที่มีสไตล์ในเอกสาร Word โดยใช้ Aspose.Words for .NET สำเร็จแล้ว ไลบรารีอันทรงพลังนี้ทำให้ง่ายต่อการปรับแต่งเอกสาร Word โดยอัตโนมัติให้ตรงกับความต้องการที่แท้จริงของคุณ ไม่ว่าคุณจะสร้างรายงาน ใบแจ้งหนี้ หรือเอกสารประเภทอื่น ๆ Aspose.Words ก็พร้อมรองรับคุณ

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการเอกสาร Word โดยทางโปรแกรมโดยใช้ C#

### ฉันสามารถใช้ Aspose.Words สำหรับ .NET เพื่อจัดรูปแบบตารางที่มีอยู่ได้หรือไม่
ได้ Aspose.Words สำหรับ .NET สามารถใช้จัดรูปแบบตารางใหม่และตารางที่มีอยู่ในเอกสาร Word ของคุณได้

### ฉันต้องมีใบอนุญาตเพื่อใช้ Aspose.Words สำหรับ .NET หรือไม่
 ใช่ Aspose.Words สำหรับ .NET จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานเต็มรูปแบบ คุณจะได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) หรือซื้อเต็ม[ที่นี่](https://purchase.aspose.com/buy).

### ฉันสามารถทำให้เอกสารประเภทอื่นเป็นอัตโนมัติด้วย Aspose.Words สำหรับ .NET ได้หรือไม่
อย่างแน่นอน! Aspose.Words สำหรับ .NET รองรับเอกสารหลายประเภท รวมถึง DOCX, PDF, HTML และอื่นๆ

### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน
 คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมได้ที่[หน้าเอกสาร Aspose.Words สำหรับ .NET](https://reference.aspose.com/words/net/).