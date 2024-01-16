---
title: ใช้เส้นขอบและการแรเงากับย่อหน้าในเอกสาร Word
linktitle: ใช้เส้นขอบและการแรเงากับย่อหน้าในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้เส้นขอบและการแรเงากับย่อหน้าในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
ในบทช่วยสอนนี้ เราจะแสดงให้คุณเห็นถึงวิธีการใช้เส้นขอบและการแรเงากับย่อหน้าในเอกสาร word โดยใช้ฟังก์ชันของ Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและใช้การเปลี่ยนแปลงการจัดรูปแบบ

## ขั้นตอนที่ 1: การสร้างและกำหนดค่าเอกสาร

ในการเริ่มต้น ให้สร้างเอกสารใหม่และออบเจ็กต์ DocumentBuilder ที่เกี่ยวข้อง มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การกำหนดค่าเส้นขอบ

ตอนนี้เรามากำหนดค่าเส้นขอบของย่อหน้าโดยระบุสไตล์เส้นขอบสำหรับแต่ละด้าน มีวิธีดังนี้:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## ขั้นตอนที่ 3: การตั้งค่า Infill

ตอนนี้เราจะกำหนดค่าการเติมย่อหน้าโดยการระบุพื้นผิวและสีเติม มีวิธีดังนี้:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## ขั้นตอนที่ 4: เพิ่มเนื้อหา

เราจะเพิ่มเนื้อหาที่จัดรูปแบบลงในย่อหน้า มีวิธีดังนี้:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## ขั้นตอนที่ 3: บันทึกเอกสาร

 หลังจากแทรกฟิลด์แบบฟอร์มป้อนข้อความแล้ว ให้บันทึกเอกสารไปยังตำแหน่งที่ต้องการโดยใช้`Save` วิธี. ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์ที่เหมาะสม:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### ตัวอย่างซอร์สโค้ดสำหรับการใช้เส้นขอบและการแรเงากับย่อหน้าโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับฟีเจอร์ Apply Borders และการแรเงาไปยังย่อหน้าด้วย Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้เส้นขอบและการแรเงากับย่อหน้าในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET โดยการกำหนดค่าย่อหน้า`Borders` และ`Shading` คุณสมบัติ เราสามารถกำหนดลักษณะเส้นขอบ สีของเส้น และสีเติมสำหรับย่อหน้าได้ Aspose.Words สำหรับ .NET มีความสามารถในการจัดรูปแบบที่มีประสิทธิภาพเพื่อปรับแต่งลักษณะที่ปรากฏของย่อหน้าและปรับปรุงการแสดงภาพเอกสารของคุณ

### คำถามที่พบบ่อย

#### ถาม: ฉันจะใช้เส้นขอบและการแรเงากับย่อหน้าในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: เมื่อต้องการใช้เส้นขอบและการแรเงากับย่อหน้าในเอกสาร Word โดยใช้ Aspose.Words for .NET ให้ทำตามขั้นตอนเหล่านี้:
1.  สร้างเอกสารใหม่และก`DocumentBuilder` วัตถุ.
2.  กำหนดค่าเส้นขอบย่อหน้าโดยเข้าไปที่`Borders` ทรัพย์สินของ`ParagraphFormat` และกำหนดรูปแบบเส้นขอบให้แต่ละด้าน
3.  กำหนดค่าการเติมย่อหน้าโดยเข้าไปที่`Shading` ทรัพย์สินของ`ParagraphFormat` และระบุพื้นผิวและสีเติม
4.  เพิ่มเนื้อหาลงในย่อหน้าโดยใช้`Write` วิธีการของ`DocumentBuilder`.
5.  บันทึกเอกสารโดยใช้`Save` วิธี.

#### ถาม: ฉันจะกำหนดรูปแบบเส้นขอบสำหรับแต่ละด้านของย่อหน้าได้อย่างไร

 ตอบ: หากต้องการกำหนดรูปแบบเส้นขอบให้กับแต่ละด้านของย่อหน้า คุณสามารถเข้าไปที่`Borders` ทรัพย์สินของ`ParagraphFormat` และตั้งค่า`LineStyle` ทรัพย์สินของแต่ละคน`BorderType` (เช่น,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). คุณสามารถระบุรูปแบบเส้นต่างๆ ได้ เช่น`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`ฯลฯ

#### ถาม: ฉันจะระบุพื้นผิวและสีเติมสำหรับการแรเงาย่อหน้าได้อย่างไร

 ตอบ: หากต้องการระบุพื้นผิวและเติมสีสำหรับการแรเงาย่อหน้า คุณสามารถเข้าถึงได้`Shading` ทรัพย์สินของ`ParagraphFormat` และตั้งค่า`Texture` คุณสมบัติเป็นดัชนีพื้นผิวที่ต้องการ (เช่น`TextureIndex.TextureDiagonalCross` ). คุณยังสามารถตั้งค่า`BackgroundPatternColor` และ`ForegroundPatternColor` คุณสมบัติเพื่อให้ได้สีที่ต้องการโดยใช้`System.Drawing.Color` ระดับ.