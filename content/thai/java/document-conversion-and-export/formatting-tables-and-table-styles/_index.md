---
title: การจัดรูปแบบตารางและสไตล์ตารางใน Aspose.Words สำหรับ Java
linktitle: การจัดรูปแบบตารางและสไตล์ตาราง
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีจัดรูปแบบตารางและใช้สไตล์ตารางใน Aspose.Words สำหรับ Java สำรวจคำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อการจัดรูปแบบตารางที่มีประสิทธิภาพ ปรับปรุงเค้าโครงเอกสารของคุณด้วย Aspose.Words
type: docs
weight: 17
url: /th/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการจัดรูปแบบตารางและสไตล์ตารางใน Aspose.Words สำหรับ Java

ตารางมีบทบาทสำคัญในการจัดโครงสร้างและจัดระเบียบข้อมูลในเอกสาร Aspose.Words สำหรับ Java มีคุณสมบัติอันทรงพลังสำหรับการจัดรูปแบบตารางและการใช้สไตล์ตารางเพื่อปรับปรุงรูปลักษณ์ของเอกสารของคุณให้สวยงามยิ่งขึ้น ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจแง่มุมต่างๆ ของการจัดรูปแบบตารางและการนำสไตล์ตารางไปใช้โดยใช้ Aspose.Words สำหรับ Java

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกรายละเอียด ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Words สำหรับ Java เข้ากับโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose:[ดาวน์โหลด Aspose.Words สำหรับ Java](https://releases.aspose.com/words/java/).

## รับระยะห่างระหว่างตารางและข้อความโดยรอบ

ในการเริ่มต้น เรามาสำรวจวิธีการดึงระยะห่างระหว่างตารางและข้อความโดยรอบในเอกสารกัน

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## ใช้เส้นขอบเค้าร่างกับตาราง

คุณสามารถจัดแนวตารางให้กึ่งกลางหน้า ล้างเส้นขอบที่มีอยู่ และตั้งค่าเส้นขอบเค้าร่างแบบกำหนดเองด้วยโค้ดนี้:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## สร้างตารางที่มีเส้นขอบ

ข้อมูลโค้ดนี้สาธิตวิธีสร้างตารางและกำหนดเส้นขอบสำหรับทั้งตารางและเซลล์:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## แก้ไขการจัดรูปแบบแถว

เรียนรู้วิธีแก้ไขการจัดรูปแบบของแถวเฉพาะภายในตาราง:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## ใช้การจัดรูปแบบแถว

ตัวอย่างนี้สาธิตวิธีการใช้การจัดรูปแบบกับทั้งแถวในตาราง:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## ตั้งค่าการเติมเซลล์

สำรวจวิธีตั้งค่าช่องว่างภายในสำหรับแต่ละเซลล์ในตาราง:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## แก้ไขการจัดรูปแบบเซลล์

ค้นพบวิธีแก้ไขการจัดรูปแบบของเซลล์เฉพาะภายในตาราง:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## จัดรูปแบบตารางและเซลล์ด้วยเส้นขอบที่ต่างกัน

เรียนรู้วิธีตั้งค่าเส้นขอบที่แตกต่างกันสำหรับแต่ละเซลล์ในตาราง:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// กำหนดเส้นขอบของตาราง
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// ตั้งค่าการแรเงาเซลล์สำหรับแต่ละเซลล์
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// เพิ่มเนื้อหาลงในเซลล์
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// ล้างการจัดรูปแบบเซลล์สำหรับแถวถัดไป
builder.getCellFormat().clearFormatting();
// สร้างเส้นขอบให้ใหญ่ขึ้นสำหรับเซลล์แรกของแถวนี้
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## ตั้งชื่อตารางและคำอธิบาย

เพิ่มชื่อและคำอธิบายลงในตารางของคุณ:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## ขั้นตอนที่ 10: อนุญาตให้มีระยะห่างระหว่างเซลล์

อนุญาตให้มีการเว้นระยะห่างเซลล์และตั้งค่าให้กับตาราง:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## ขั้นตอนที่ 11: สร้างตารางอย่างมีสไตล์

สร้างตารางด้วยสไตล์ที่กำหนดไว้ล่วงหน้า:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## ขั้นตอนที่ 12: ขยายการจัดรูปแบบในเซลล์และแถวจากสไตล์

เรียนรู้วิธีขยายสไตล์ตารางเพื่อใช้การจัดรูปแบบกับเซลล์และแถว:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## ขั้นตอนที่ 13: สร้างสไตล์ตาราง

สร้างสไตล์ตารางแบบกำหนดเองด้วยการจัดรูปแบบเฉพาะ:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## ขั้นตอนที่ 14: กำหนดการจัดรูปแบบตามเงื่อนไข

ใช้การจัดรูปแบบตามเงื่อนไขกับแถวในตาราง:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## ขั้นตอนที่ 15: ตั้งค่าการจัดรูปแบบ TableCell

ตั้งค่าการจัดรูปแบบเฉพาะสำหรับแต่ละเซลล์:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## ขั้นตอนที่ 16: ตั้งค่าการจัดรูปแบบ TableRow

ใช้การจัดรูปแบบกับทั้งแถวในตาราง:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## บทสรุป

Aspose.Words สำหรับ Java ช่วยให้คุณสามารถจัดรูปแบบตารางและใช้สไตล์ตารางได้อย่างแม่นยำ ตั้งแต่การแก้ไขการจัดรูปแบบเซลล์แต่ละเซลล์ไปจนถึงการสร้างสไตล์ตารางแบบกำหนดเอง คุณมีเครื่องมือในการทำให้เอกสารของคุณดูน่าดึงดูดและเป็นระเบียบ

## คำถามที่พบบ่อย

### ฉันจะดาวน์โหลด Aspose.Words สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Words สำหรับ Java ได้จากเว็บไซต์ Aspose:[ดาวน์โหลด Aspose.Words สำหรับ Java](https://releases.aspose.com/words/java/).

### ฉันสามารถใช้เส้นขอบที่แตกต่างกันกับแต่ละเซลล์ภายในตารางได้หรือไม่

ได้ คุณสามารถตั้งค่าเส้นขอบที่แตกต่างกันสำหรับแต่ละเซลล์ภายในตารางได้โดยใช้ Aspose.Words สำหรับ Java ดังที่แสดงในคู่มือนี้

### จุดประสงค์ของการตั้งชื่อตารางและคำอธิบายคืออะไร?

การตั้งชื่อตารางและคำอธิบายจะช่วยเพิ่มการเข้าถึงและการจัดระเบียบเอกสารของคุณ ทำให้ผู้อ่านและเทคโนโลยีช่วยเหลือเข้าใจเนื้อหาได้ง่ายขึ้น

### ฉันจะใช้การจัดรูปแบบตามเงื่อนไขกับแถวที่ต้องการในตารางได้อย่างไร

คุณสามารถใช้การจัดรูปแบบตามเงื่อนไขกับแถวที่ต้องการในตารางได้โดยการกำหนดลักษณะตารางแบบกำหนดเองด้วยกฎการจัดรูปแบบตามเงื่อนไข ดังที่แสดงในคู่มือนี้

### ฉันจะหาเอกสารและทรัพยากรเพิ่มเติมสำหรับ Aspose.Words สำหรับ Java ได้ที่ไหน

 สำหรับเอกสารประกอบที่ครอบคลุมและแหล่งข้อมูลเพิ่มเติม โปรดไปที่เอกสารประกอบ Aspose.Words สำหรับ Java:[Aspose.Words สำหรับเอกสาร Java](https://reference.aspose.com/words/java/).