---
title: การใช้ลายน้ำกับเอกสารใน Aspose.Words สำหรับ Java
linktitle: การใช้ลายน้ำกับเอกสาร
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีเพิ่มลายน้ำให้กับเอกสารใน Aspose.Words สำหรับ Java ปรับแต่งลายน้ำข้อความและรูปภาพสำหรับเอกสารที่ดูเป็นมืออาชีพ
type: docs
weight: 15
url: /th/java/document-conversion-and-export/using-watermarks-to-documents/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการเพิ่มลายน้ำให้กับเอกสารใน Aspose.Words สำหรับ Java

ในบทช่วยสอนนี้ เราจะสำรวจวิธีเพิ่มลายน้ำให้กับเอกสารโดยใช้ Aspose.Words สำหรับ Java API ลายน้ำเป็นวิธีที่มีประโยชน์ในการติดป้ายกำกับเอกสารด้วยข้อความหรือกราฟิกเพื่อระบุสถานะ การรักษาความลับ หรือข้อมูลอื่นๆ ที่เกี่ยวข้อง เราจะกล่าวถึงทั้งลายน้ำข้อความและรูปภาพในคู่มือนี้

## การตั้งค่า Aspose.Words สำหรับ Java

ก่อนที่เราจะเริ่มเพิ่มลายน้ำให้กับเอกสาร เราต้องตั้งค่า Aspose.Words สำหรับ Java ก่อน ทำตามขั้นตอนเหล่านี้เพื่อเริ่มต้น:

1.  ดาวน์โหลด Aspose.Words สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/words/java/).
2. เพิ่มไลบรารี Aspose.Words สำหรับ Java ให้กับโปรเจ็กต์ Java ของคุณ
3. นำเข้าคลาสที่จำเป็นในโค้ด Java ของคุณ

ตอนนี้เราได้ตั้งค่าห้องสมุดแล้ว เรามาเพิ่มลายน้ำกันต่อ

## การเพิ่มลายน้ำข้อความ

ลายน้ำข้อความเป็นตัวเลือกทั่วไปเมื่อคุณต้องการเพิ่มข้อมูลที่เป็นข้อความลงในเอกสารของคุณ ต่อไปนี้คือวิธีที่คุณสามารถเพิ่มลายน้ำข้อความโดยใช้ Aspose.Words สำหรับ Java:

```java
//สร้างอินสแตนซ์เอกสาร
Document doc = new Document("Document.docx");

// กำหนดตัวเลือกลายน้ำข้อความ
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

// ตั้งค่าข้อความและตัวเลือกลายน้ำ
doc.getWatermark().setText("Test", options);

// บันทึกเอกสารที่มีลายน้ำ
doc.save("DocumentWithWatermark.docx");
```

## การเพิ่มลายน้ำรูปภาพ

นอกจากลายน้ำข้อความแล้ว คุณยังสามารถเพิ่มลายน้ำรูปภาพลงในเอกสารของคุณได้ ต่อไปนี้เป็นวิธีเพิ่มลายน้ำรูปภาพ:

```java
//สร้างอินสแตนซ์เอกสาร
Document doc = new Document("Document.docx");

// โหลดรูปภาพสำหรับใส่ลายน้ำ
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

// กำหนดขนาดและตำแหน่งของลายน้ำ
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

// เพิ่มลายน้ำให้กับเอกสาร
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// บันทึกเอกสารที่มีลายน้ำ
doc.save("DocumentWithImageWatermark.docx");
```

## การปรับแต่งลายน้ำ

คุณสามารถปรับแต่งลายน้ำได้โดยการปรับรูปลักษณ์และตำแหน่ง สำหรับลายน้ำข้อความ คุณสามารถเปลี่ยนแบบอักษร ขนาด สี และเค้าโครงได้ สำหรับลายน้ำรูปภาพ คุณสามารถปรับขนาดและตำแหน่งได้ตามที่แสดงในตัวอย่างก่อนหน้านี้

## การลบลายน้ำ

หากต้องการลบลายน้ำออกจากเอกสาร คุณสามารถใช้รหัสต่อไปนี้:

```java
//สร้างอินสแตนซ์เอกสาร
Document doc = new Document("DocumentWithWatermark.docx");

// ลบลายน้ำ
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

// บันทึกเอกสารโดยไม่มีลายน้ำ
doc.save("DocumentWithoutWatermark.docx");
```


## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเพิ่มลายน้ำให้กับเอกสารโดยใช้ Aspose.Words สำหรับ Java ไม่ว่าคุณจะต้องการเพิ่มลายน้ำข้อความหรือรูปภาพ Aspose.Words ก็มีเครื่องมือในการปรับแต่งและจัดการได้อย่างมีประสิทธิภาพ คุณยังสามารถลบลายน้ำเมื่อไม่จำเป็นอีกต่อไป เพื่อให้มั่นใจว่าเอกสารของคุณสะอาดและเป็นมืออาชีพ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนแบบอักษรของลายน้ำข้อความได้อย่างไร

 หากต้องการเปลี่ยนแบบอักษรของลายน้ำข้อความ ให้แก้ไข`setFontFamily` ทรัพย์สินใน`TextWatermarkOptions`. ตัวอย่างเช่น:

```java
options.setFontFamily("Times New Roman");
```

### ฉันสามารถเพิ่มลายน้ำหลายลายลงในเอกสารเดียวได้หรือไม่

 ใช่ คุณสามารถเพิ่มลายน้ำได้หลายลายลงในเอกสารโดยการสร้างลายน้ำหลายลาย`Shape` วัตถุที่มีการตั้งค่าต่างกันและเพิ่มลงในเอกสาร

### เป็นไปได้ไหมที่จะหมุนลายน้ำ?

 ใช่ คุณสามารถหมุนลายน้ำได้โดยการตั้งค่า`setRotation` ทรัพย์สินใน`Shape` วัตถุ. ค่าบวกจะหมุนลายน้ำตามเข็มนาฬิกา และค่าลบจะหมุนทวนเข็มนาฬิกา

### ฉันจะทำให้ลายน้ำเป็นแบบกึ่งโปร่งใสได้อย่างไร

 หากต้องการทำให้ลายน้ำเป็นแบบกึ่งโปร่งใส ให้ตั้งค่า`setSemitransparent`ทรัพย์สินเพื่อ`true` ใน`TextWatermarkOptions`.

### ฉันสามารถเพิ่มลายน้ำให้กับส่วนใดส่วนหนึ่งของเอกสารได้หรือไม่

ได้ คุณสามารถเพิ่มลายน้ำให้กับส่วนเฉพาะของเอกสารได้โดยการวนซ้ำส่วนต่างๆ และเพิ่มลายน้ำไปยังส่วนที่ต้องการ