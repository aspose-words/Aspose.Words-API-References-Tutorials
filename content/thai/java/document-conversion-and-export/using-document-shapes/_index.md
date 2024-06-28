---
title: การใช้รูปร่างเอกสารใน Aspose.Words สำหรับ Java
linktitle: การใช้รูปร่างเอกสาร
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: ปลดล็อกพลังของรูปร่างเอกสารใน Aspose.Words สำหรับ Java เรียนรู้วิธีสร้างเอกสารที่ดึงดูดสายตาด้วยตัวอย่างทีละขั้นตอน
type: docs
weight: 14
url: /th/java/document-conversion-and-export/using-document-shapes/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการใช้รูปร่างเอกสารใน Aspose.Words สำหรับ Java

ในคู่มือที่ครอบคลุมนี้ เราจะเจาะลึกโลกของรูปร่างเอกสารใน Aspose.Words สำหรับ Java รูปร่างเป็นองค์ประกอบสำคัญในการสร้างเอกสารเชิงโต้ตอบที่มีภาพน่าสนใจ ไม่ว่าคุณจะต้องเพิ่มคำบรรยาย ปุ่ม รูปภาพ หรือลายน้ำ Aspose.Words สำหรับ Java ก็มีเครื่องมือที่จะช่วยให้คุณดำเนินการได้อย่างมีประสิทธิภาพ เรามาสำรวจวิธีการใช้รูปร่างเหล่านี้ทีละขั้นตอนพร้อมตัวอย่างซอร์สโค้ด

## เริ่มต้นใช้งานรูปร่างเอกสาร

 ก่อนที่เราจะพูดถึงโค้ด เรามาตั้งค่าสภาพแวดล้อมของเรากันก่อน ตรวจสอบให้แน่ใจว่าคุณได้รวม Aspose.Words สำหรับ Java เข้ากับโปรเจ็กต์ของคุณแล้ว หากคุณยังไม่ได้ดาวน์โหลด คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose[ดาวน์โหลด Aspose.Words สำหรับ Java](https://releases.aspose.com/words/java/)

## การเพิ่มรูปร่างให้กับเอกสาร

### การแทรก GroupShape

 ก`GroupShape` ช่วยให้คุณสามารถจัดกลุ่มรูปร่างต่างๆ ไว้ด้วยกัน ต่อไปนี้คือวิธีที่คุณสามารถสร้างและแทรก`GroupShape`-

```java
Document doc = new Document();
doc.ensureMinimum();

GroupShape groupShape = new GroupShape(doc);
Shape accentBorderShape = new Shape(doc, ShapeType.ACCENT_BORDER_CALLOUT_1);
accentBorderShape.setWidth(100.0);
accentBorderShape.setHeight(100.0);

groupShape.appendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ACTION_BUTTON_BEGINNING);
actionButtonShape.setLeft(100.0);
actionButtonShape.setWidth(100.0);
actionButtonShape.setHeight(200.0);

groupShape.appendChild(actionButtonShape);

groupShape.setWidth(200.0);
groupShape.setHeight(200.0);
groupShape.setCoordSize(new Dimension(200, 200));

DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertNode(groupShape);

doc.save("Your Directory Path" + "WorkingWithShapes.AddGroupShape.docx");
```

### การแทรกรูปร่างกล่องข้อความ

 หากต้องการแทรกรูปร่างกล่องข้อความ คุณสามารถใช้`insertShape` วิธีการดังแสดงในตัวอย่างด้านล่าง:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertShape(ShapeType.TEXT_BOX, RelativeHorizontalPosition.PAGE, 100.0,
    RelativeVerticalPosition.PAGE, 100.0, 50.0, 50.0, WrapType.NONE);

shape.setRotation(30.0);
builder.writeln();

shape = builder.insertShape(ShapeType.TEXT_BOX, 50.0, 50.0);
shape.setRotation(30.0);

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.DOCX);
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);

doc.save("Your Directory Path" + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## การจัดการคุณสมบัติของรูปร่าง

### การจัดการอัตราส่วนภาพ

คุณสามารถควบคุมได้ว่าอัตราส่วนภาพของรูปร่างจะถูกล็อคหรือไม่ วิธีปลดล็อกอัตราส่วนกว้างยาวของรูปร่างมีดังนี้

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
shape.setAspectRatioLocked(false);

doc.save("Your Directory Path" + "WorkingWithShapes.AspectRatioLocked.docx");
```

### การวางรูปร่างในเซลล์ตาราง

หากคุณต้องการวางรูปร่างภายในเซลล์ของตาราง คุณสามารถทำได้โดยใช้โค้ดต่อไปนี้:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.startTable();
builder.getRowFormat().setHeight(100.0);
builder.getRowFormat().setHeightRule(HeightRule.EXACTLY);

for (int i = 0; i < 31; i++) {
    if (i != 0 && i % 7 == 0)
        builder.endRow();

    builder.insertCell();
    builder.write("Cell contents");
}

builder.endTable();

Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.isLayoutInCell(true); // แสดงรูปร่างภายนอกเซลล์ตารางหากจะวางลงในเซลล์
watermark.setWidth(300.0);
watermark.setHeight(70.0);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setRotation(-40);
watermark.setFillColor(Color.GRAY);
watermark.setStrokeColor(Color.GRAY);
watermark.getTextPath().setText("watermarkText");
watermark.getTextPath().setFontFamily("Arial");
watermark.setName("WaterMark_{Guid.NewGuid()}");
watermark.setWrapType(WrapType.NONE);

Run run = (Run) doc.getChildNodes(NodeType.RUN, true).get(doc.getChildNodes(NodeType.RUN, true).getCount() - 1);
builder.moveTo(run);
builder.insertNode(watermark);

doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2010);
doc.save("Your Directory Path" + "WorkingWithShapes.LayoutInCell.docx");
```

## การทำงานกับรูปร่าง SmartArt

### การตรวจจับรูปร่าง SmartArt

คุณสามารถตรวจจับรูปร่าง SmartArt ในเอกสารได้โดยใช้รหัสต่อไปนี้:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
List<Shape> shapes = IterableUtils.toList(doc.getChildNodes(NodeType.SHAPE, true));
int count = (int) shapes.stream().filter(s -> s.hasSmartArt()).count();
System.out.println("The document has " + count + " shapes with SmartArt.");
```

### อัปเดตภาพวาด SmartArt

หากต้องการอัปเดตรูปวาด SmartArt ภายในเอกสาร ให้ใช้โค้ดต่อไปนี้:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true)) {
    if (shape.hasSmartArt())
        shape.updateSmartArtDrawing();
}
```

## บทสรุป

ในคู่มือนี้ เราได้สำรวจโลกของรูปร่างเอกสารใน Aspose.Words สำหรับ Java คุณได้เรียนรู้วิธีการเพิ่มรูปร่างต่างๆ ลงในเอกสารของคุณ จัดการคุณสมบัติ และทำงานกับรูปร่าง SmartArt ด้วยความรู้นี้ คุณสามารถสร้างเอกสารเชิงโต้ตอบและภาพที่น่าสนใจได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ Java คืออะไร

Aspose.Words for Java เป็นไลบรารี Java ที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และแปลงเอกสาร Word โดยทางโปรแกรม มีคุณสมบัติและเครื่องมือมากมายสำหรับการทำงานกับเอกสารในรูปแบบต่างๆ

### ฉันจะดาวน์โหลด Aspose.Words สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Words สำหรับ Java ได้จากเว็บไซต์ Aspose โดยไปที่ลิงก์นี้:[ดาวน์โหลด Aspose.Words สำหรับ Java](https://releases.aspose.com/words/java/)

### การใช้รูปร่างเอกสารมีประโยชน์อย่างไร

รูปร่างของเอกสารเพิ่มองค์ประกอบภาพและการโต้ตอบให้กับเอกสารของคุณ ทำให้น่าสนใจและให้ข้อมูลมากขึ้น ด้วยรูปร่าง คุณสามารถสร้างสาย ปุ่ม รูปภาพ ลายน้ำ และอื่นๆ อีกมากมาย ปรับปรุงประสบการณ์ผู้ใช้โดยรวม

### ฉันสามารถปรับแต่งรูปลักษณ์ของรูปร่างได้หรือไม่?

ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของรูปร่างได้โดยการปรับคุณสมบัติ เช่น ขนาด ตำแหน่ง การหมุน และการเติมสี Aspose.Words สำหรับ Java มีตัวเลือกมากมายสำหรับการปรับแต่งรูปร่าง

### Aspose.Words สำหรับ Java เข้ากันได้กับ SmartArt หรือไม่

ใช่ Aspose.Words สำหรับ Java รองรับรูปร่าง SmartArt ทำให้คุณสามารถทำงานกับไดอะแกรมและกราฟิกที่ซับซ้อนในเอกสารของคุณได้