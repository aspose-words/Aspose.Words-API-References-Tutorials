---
title: ขยายการจัดรูปแบบบนเซลล์และแถวจากสไตล์
linktitle: ขยายการจัดรูปแบบบนเซลล์และแถวจากสไตล์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการขยายการจัดรูปแบบไปยังเซลล์และแถวจากสไตล์ตารางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อขยายการจัดรูปแบบไปยังเซลล์และแถวจากสไตล์โดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีนำการจัดรูปแบบตารางไปใช้กับเซลล์และแถวที่ต้องการในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET


## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือที่ตั้งเอกสาร Word ของคุณ แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารที่มีอยู่
 ถัดไป คุณต้องโหลดเอกสาร Word ที่มีอยู่ลงในอินสแตนซ์ของ`Document` ระดับ.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## ขั้นตอนที่ 3: ไปที่เซลล์แรกของตารางแรก
 ในการเริ่มต้น เราต้องนำทางไปยังเซลล์แรกของตารางแรกในเอกสาร เราใช้`GetChild()` และ`FirstRow.FirstCell` วิธีการรับการอ้างอิงไปยังเซลล์แรก

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## ขั้นตอนที่ 4: แสดงการจัดรูปแบบเซลล์เริ่มต้น
ก่อนที่จะขยายสไตล์ของตาราง เราจะแสดงสีพื้นหลังปัจจุบันของเซลล์ ซึ่งควรเว้นว่างไว้เนื่องจากการจัดรูปแบบปัจจุบันถูกจัดเก็บไว้ในรูปแบบของตาราง

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## ขั้นตอนที่ 5: ขยายสไตล์ตารางเป็นการจัดรูปแบบโดยตรง
 ตอนนี้เราขยายรูปแบบตารางเพื่อจัดรูปแบบโดยตรงโดยใช้เอกสาร`ExpandTableStylesToDirectFormatting()` วิธี.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## ขั้นตอนที่ 6: แสดงการจัดรูปแบบเซลล์หลังการขยายสไตล์
ตอนนี้เราแสดงสีพื้นหลังของเซลล์หลังจากขยายสไตล์ตาราง ควรใช้สีพื้นหลังสีน้ำเงินจากสไตล์ตาราง

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### ซอร์สโค้ดตัวอย่างสำหรับขยายการจัดรูปแบบบนเซลล์และแถวจากสไตล์โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// รับเซลล์แรกของตารางแรกในเอกสาร
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// ขั้นแรกให้พิมพ์สีของการแรเงาของเซลล์
	// ซึ่งควรว่างเปล่าเนื่องจากการแรเงาปัจจุบันถูกจัดเก็บไว้ในรูปแบบตาราง
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// ตอนนี้พิมพ์การแรเงาเซลล์หลังจากขยายสไตล์ตาราง
	// ควรใช้สีลวดลายพื้นหลังสีน้ำเงินจากสไตล์ตาราง
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีขยายการจัดรูปแบบไปยังเซลล์และแถวจากสไตล์ตารางโดยใช้ Aspose.Words สำหรับ .NET เมื่อทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถนำการจัดรูปแบบสไตล์ตารางไปใช้กับเซลล์และแถวที่ต้องการในเอกสาร Word ของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับแต่งเค้าโครงและการนำเสนอเอกสาร Word ของคุณเพิ่มเติมได้