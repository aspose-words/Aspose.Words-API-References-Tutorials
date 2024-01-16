---
title: ลายน้ำเอกสารและการตั้งค่าหน้า
linktitle: ลายน้ำเอกสารและการตั้งค่าหน้า
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีใส่ลายน้ำและตั้งค่าการกำหนดค่าเพจด้วย Aspose.Words สำหรับ Java คู่มือที่ครอบคลุมพร้อมซอร์สโค้ด
type: docs
weight: 13
url: /th/java/document-styling/document-watermarking-page-setup/
---
## การแนะนำ

ในขอบเขตของการจัดการเอกสาร Aspose.Words สำหรับ Java ย่อมาจากเครื่องมืออันทรงพลัง ช่วยให้นักพัฒนาสามารถควบคุมการประมวลผลเอกสารในทุกด้าน ในคู่มือที่ครอบคลุมนี้ เราจะเจาะลึกความซับซ้อนของการใส่ลายน้ำในเอกสารและการตั้งค่าหน้าโดยใช้ Aspose.Words สำหรับ Java ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพียงแค่ก้าวเข้าสู่โลกแห่งการประมวลผลเอกสาร Java คำแนะนำทีละขั้นตอนนี้จะช่วยให้คุณมีความรู้และซอร์สโค้ดที่คุณต้องการ

## ลายน้ำเอกสาร

### การเพิ่มลายน้ำ

การเพิ่มลายน้ำให้กับเอกสารอาจมีความสำคัญต่อการสร้างแบรนด์หรือรักษาความปลอดภัยให้กับเนื้อหาของคุณ Aspose.Words สำหรับ Java ทำให้งานนี้ตรงไปตรงมา มีวิธีดังนี้:

```java
// โหลดเอกสาร
Document doc = new Document("document.docx");

// สร้างลายน้ำ
Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.getTextPath().setText("Confidential");
watermark.setWidth(300);
watermark.setHeight(100);

// วางตำแหน่งลายน้ำ
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.setWrapType(WrapType.NONE);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);

// ใส่ลายน้ำ
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// บันทึกเอกสาร
doc.save("document_with_watermark.docx");
```

### การปรับแต่งลายน้ำ

คุณสามารถปรับแต่งลายน้ำเพิ่มเติมได้โดยการปรับแบบอักษร ขนาด สี และการหมุน ความยืดหยุ่นนี้ช่วยให้มั่นใจว่าลายน้ำของคุณตรงกับสไตล์ของเอกสารของคุณได้อย่างราบรื่น

## การตั้งค่าหน้า

### ขนาดหน้าและการวางแนว

การตั้งค่าหน้าเป็นส่วนสำคัญในการจัดรูปแบบเอกสาร Aspose.Words สำหรับ Java ให้การควบคุมขนาดหน้าและการวางแนวอย่างสมบูรณ์:

```java
// โหลดเอกสาร
Document doc = new Document("document.docx");

// ตั้งค่าขนาดหน้าเป็น A4
doc.getFirstSection().getPageSetup().setPageWidth(595.0);
doc.getFirstSection().getPageSetup().setPageHeight(842.0);

// เปลี่ยนการวางแนวหน้าเป็นแนวนอน
doc.getFirstSection().getPageSetup().setOrientation(Orientation.LANDSCAPE);

// บันทึกเอกสารที่แก้ไข
doc.save("formatted_document.docx");
```

### ระยะขอบและการกำหนดหมายเลขหน้า

การควบคุมระยะขอบและการกำหนดหมายเลขหน้าอย่างแม่นยำถือเป็นสิ่งสำคัญสำหรับเอกสารระดับมืออาชีพ บรรลุเป้าหมายนี้ด้วย Aspose.Words สำหรับ Java:

```java
// โหลดเอกสาร
Document doc = new Document("document.docx");

// ตั้งค่าระยะขอบ
doc.getFirstSection().getPageSetup().setLeftMargin(72.0);
doc.getFirstSection().getPageSetup().setRightMargin(72.0);
doc.getFirstSection().getPageSetup().setTopMargin(72.0);
doc.getFirstSection().getPageSetup().setBottomMargin(72.0);

// เปิดใช้งานการกำหนดหมายเลขหน้า
doc.getFirstSection().getPageSetup().setDifferentFirstPageHeaderFooter(true);
HeaderFooter firstPageHeader = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_FIRST);
firstPageHeader.appendParagraph("First Page Header");

// บันทึกเอกสารที่จัดรูปแบบ
doc.save("formatted_document.docx");
```

## คำถามที่พบบ่อย

### ฉันจะลบลายน้ำออกจากเอกสารได้อย่างไร

หากต้องการลบลายน้ำออกจากเอกสาร คุณสามารถวนซ้ำรูปร่างของเอกสารและลบลายน้ำออกได้ นี่เป็นตัวอย่าง:

```java
Document doc = new Document("document_with_watermark.docx");

for (Shape shape : doc.getChildNodes(NodeType.SHAPE, true).<Shape>toArray()) {
    if (shape.getText().contains("Confidential")) {
        shape.remove();
    }
}

doc.save("document_without_watermark.docx");
```

### ฉันสามารถเพิ่มลายน้ำหลายลายลงในเอกสารเดียวได้หรือไม่

ได้ คุณสามารถเพิ่มลายน้ำได้หลายลายลงในเอกสารโดยการสร้างวัตถุรูปร่างเพิ่มเติมและจัดตำแหน่งตามต้องการ

### ฉันจะเปลี่ยนขนาดหน้าให้ถูกกฎหมายในแนวนอนได้อย่างไร

หากต้องการตั้งค่าขนาดหน้ากระดาษให้ถูกกฎหมายในแนวนอน ให้แก้ไขความกว้างและความสูงของหน้าดังนี้:

```java
doc.getFirstSection().getPageSetup().setPageWidth(842.0);
doc.getFirstSection().getPageSetup().setPageHeight(595.0);
```

### แบบอักษรเริ่มต้นสำหรับลายน้ำคืออะไร?

แบบอักษรเริ่มต้นสำหรับลายน้ำคือ Calibri โดยมีขนาดตัวอักษร 36

### ฉันจะเพิ่มหมายเลขหน้าโดยเริ่มจากหน้าใดหน้าหนึ่งได้อย่างไร

คุณสามารถทำได้โดยการตั้งค่าหมายเลขหน้าเริ่มต้นในเอกสารของคุณดังนี้:

```java
doc.getFirstSection().getPageSetup().setPageStartingNumber(5);
```

### ฉันจะจัดข้อความให้อยู่กึ่งกลางในส่วนหัวหรือส่วนท้ายได้อย่างไร

คุณสามารถจัดกึ่งกลางข้อความในส่วนหัวหรือส่วนท้ายได้โดยใช้วิธี setAlignment บนวัตถุย่อหน้าภายในส่วนหัวหรือส่วนท้าย

## บทสรุป

ในคู่มือที่ครอบคลุมนี้ เราได้สำรวจศิลปะของการใส่ลายน้ำในเอกสารและการตั้งค่าหน้าโดยใช้ Aspose.Words สำหรับ Java ด้วยตัวอย่างซอร์สโค้ดและข้อมูลเชิงลึกที่ให้มา ขณะนี้คุณมีเครื่องมือในการจัดการและจัดรูปแบบเอกสารของคุณอย่างประณีต Aspose.Words สำหรับ Java ช่วยให้คุณสร้างเอกสารระดับมืออาชีพที่มีแบรนด์ซึ่งปรับให้เหมาะกับข้อกำหนดเฉพาะของคุณ

การเรียนรู้การจัดการเอกสารเป็นทักษะที่มีค่าสำหรับนักพัฒนา และ Aspose.Words สำหรับ Java คือเพื่อนคู่ใจที่คุณไว้วางใจในการเดินทางครั้งนี้ เริ่มสร้างเอกสารที่น่าทึ่งวันนี้!