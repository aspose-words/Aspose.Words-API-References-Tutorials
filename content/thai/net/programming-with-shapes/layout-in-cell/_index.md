---
title: เค้าโครงในเซลล์
linktitle: เค้าโครงในเซลล์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตั้งค่าเค้าโครงในเซลล์โดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำที่ครอบคลุมนี้ เหมาะสำหรับนักพัฒนาที่ต้องการปรับแต่งเอกสาร Word
type: docs
weight: 10
url: /th/net/programming-with-shapes/layout-in-cell/
---
## การแนะนำ

หากคุณเคยต้องการปรับแต่งเค้าโครงของเซลล์ตารางในเอกสาร Word โดยทางโปรแกรม แสดงว่าคุณมาถูกที่แล้ว วันนี้ เราจะมาเจาะลึกถึงวิธีการตั้งค่าเค้าโครงในเซลล์โดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายตัวอย่างที่เป็นประโยชน์โดยแจกแจงรายละเอียดทีละขั้นตอนเพื่อให้คุณสามารถปฏิบัติตามได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะพูดถึงโค้ด เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการแล้ว:

1.  Aspose.Words for .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Words for .NET แล้ว หากคุณยังไม่ได้คุณสามารถ[ดาวน์โหลดได้ที่นี่](https://releases.aspose.com/words/net/).
2. สภาพแวดล้อมการพัฒนา: คุณจะต้องมีสภาพแวดล้อมการพัฒนาที่ตั้งค่าด้วย .NET Visual Studio เป็นตัวเลือกที่ยอดเยี่ยมหากคุณกำลังมองหาคำแนะนำ
3. ความรู้พื้นฐานของ C#: แม้ว่าฉันจะอธิบายแต่ละขั้นตอน แต่ความเข้าใจพื้นฐานเกี่ยวกับ C# จะช่วยให้คุณปฏิบัติตามได้ง่ายขึ้น
4.  Document Directory: เตรียมเส้นทางไดเรกทอรีที่คุณจะบันทึกเอกสารของคุณ เราจะเรียกสิ่งนี้ว่า`YOUR DOCUMENT DIRECTORY`.

## นำเข้าเนมสเปซ

ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณกำลังนำเข้าเนมสเปซที่จำเป็นในโครงการของคุณ:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

เรามาแบ่งกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้

## ขั้นตอนที่ 1: สร้างเอกสารใหม่

 ขั้นแรก เราจะสร้างเอกสาร Word ใหม่และเริ่มต้น`DocumentBuilder` วัตถุเพื่อช่วยเราสร้างเนื้อหาของเรา

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: เริ่มตารางและตั้งค่ารูปแบบแถว

เราจะเริ่มสร้างตารางและระบุกฎความสูงและความสูงของแถว

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## ขั้นตอนที่ 3: แทรกเซลล์และเติมเนื้อหา

ต่อไปเราวนซ้ำเพื่อแทรกเซลล์ลงในตาราง ทุกๆ 7 เซลล์ เราจะจบแถวเพื่อสร้างเซลล์ใหม่

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## ขั้นตอนที่ 4: เพิ่มรูปร่างลายน้ำ

 ตอนนี้เรามาเพิ่มลายน้ำให้กับเอกสารของเรา เราจะสร้างก`Shape` วัตถุและกำหนดคุณสมบัติของมัน

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // แสดงรูปร่างภายนอกเซลล์ตารางหากจะวางลงในเซลล์
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## ขั้นตอนที่ 5: ปรับแต่งลักษณะลายน้ำ

เราจะปรับแต่งลักษณะที่ปรากฏของลายน้ำเพิ่มเติมโดยการตั้งค่าคุณสมบัติสีและข้อความ

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## ขั้นตอนที่ 6: ใส่ลายน้ำลงในเอกสาร

เราจะค้นหาการทำงานครั้งสุดท้ายในเอกสารและใส่ลายน้ำที่ตำแหน่งนั้น

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## ขั้นตอนที่ 7: ปรับเอกสารให้เหมาะสมสำหรับ Word 2010

เพื่อให้มั่นใจถึงความเข้ากันได้ เราจะปรับเอกสารให้เหมาะสมสำหรับ Word 2010

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร

สุดท้าย เราจะบันทึกเอกสารของเราลงในไดเร็กทอรีที่ระบุ

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## บทสรุป

และคุณก็ได้แล้ว! คุณสร้างเอกสาร Word สำเร็จด้วยเค้าโครงตารางที่กำหนดเองและเพิ่มลายน้ำโดยใช้ Aspose.Words สำหรับ .NET บทช่วยสอนนี้มีวัตถุประสงค์เพื่อให้คำแนะนำที่ชัดเจนทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจแต่ละส่วนของกระบวนการ ด้วยทักษะเหล่านี้ คุณสามารถสร้างเอกสาร Word ที่ซับซ้อนและปรับแต่งได้มากขึ้นโดยทางโปรแกรม

## คำถามที่พบบ่อย

### ฉันสามารถใช้แบบอักษรอื่นสำหรับข้อความลายน้ำได้หรือไม่
 ใช่ คุณสามารถเปลี่ยนแบบอักษรได้โดยการตั้งค่า`watermark.TextPath.FontFamily` คุณสมบัติให้กับแบบอักษรที่คุณต้องการ

### ฉันจะปรับตำแหน่งของลายน้ำได้อย่างไร?
 คุณสามารถแก้ไข`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , และ`VerticalAlignment` คุณสมบัติในการปรับตำแหน่งของลายน้ำ

### เป็นไปได้ไหมที่จะใช้รูปภาพแทนข้อความเป็นลายน้ำ?
 อย่างแน่นอน! คุณสามารถสร้าง`Shape` กับประเภท`ShapeType.Image` และตั้งค่ารูปภาพโดยใช้`ImageData.SetImage` วิธี.

### ฉันสามารถสร้างตารางที่มีความสูงของแถวต่างกันได้หรือไม่
ได้ คุณสามารถตั้งค่าความสูงที่แตกต่างกันสำหรับแต่ละแถวได้โดยการเปลี่ยน`RowFormat.Height` คุณสมบัติก่อนที่จะแทรกเซลล์ลงในแถวนั้น

### ฉันจะลบลายน้ำออกจากเอกสารได้อย่างไร
 คุณสามารถลบลายน้ำได้โดยค้นหามันในคอลเลกชันรูปร่างของเอกสารแล้วเรียก`Remove` วิธี.