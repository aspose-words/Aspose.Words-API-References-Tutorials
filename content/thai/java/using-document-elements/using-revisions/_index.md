---
title: การใช้การแก้ไขใน Aspose.Words สำหรับ Java
linktitle: การใช้การแก้ไข
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้การใช้ Aspose.Words สำหรับการแก้ไข Java อย่างมีประสิทธิภาพ คำแนะนำทีละขั้นตอนสำหรับนักพัฒนา เพิ่มประสิทธิภาพการจัดการเอกสารของคุณ
type: docs
weight: 22
url: /th/java/using-document-elements/using-revisions/
---

หากคุณเป็นนักพัฒนา Java ที่ต้องการทำงานกับเอกสารและจำเป็นต้องใช้การควบคุมการแก้ไข Aspose.Words สำหรับ Java มีชุดเครื่องมืออันทรงพลังเพื่อช่วยให้คุณจัดการการแก้ไขได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการใช้การแก้ไขใน Aspose.Words สำหรับ Java ทีละขั้นตอน 

## 1. รู้เบื้องต้นเกี่ยวกับ Aspose.Words สำหรับ Java

Aspose.Words สำหรับ Java เป็น Java API ที่มีประสิทธิภาพซึ่งช่วยให้คุณสามารถสร้าง แก้ไข และจัดการเอกสาร Word โดยไม่จำเป็นต้องใช้ Microsoft Word มีประโยชน์อย่างยิ่งเมื่อคุณต้องการดำเนินการแก้ไขภายในเอกสารของคุณ

## 2. การตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ

ก่อนที่เราจะเจาะลึกการใช้ Aspose.Words สำหรับ Java คุณต้องตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อน ตรวจสอบให้แน่ใจว่าคุณมีเครื่องมือการพัฒนา Java ที่จำเป็นและติดตั้งไลบรารี Aspose.Words สำหรับ Java แล้ว

## 3. การสร้างเอกสารใหม่

เริ่มต้นด้วยการสร้างเอกสาร Word ใหม่โดยใช้ Aspose.Words สำหรับ Java ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
string outPath = "Your Output Directory";
Document doc = new Document();
Body body = doc.getFirstSection().getBody();
Paragraph para = body.getFirstParagraph();
```

## 4. การเพิ่มเนื้อหาลงในเอกสาร

ตอนนี้คุณมีเอกสารเปล่าแล้ว คุณสามารถเพิ่มเนื้อหาลงไปได้ ในตัวอย่างนี้ เราจะเพิ่มสามย่อหน้า:

```java
para.appendChild(new Run(doc, "Paragraph 1. "));
body.appendParagraph("Paragraph 2. ");
body.appendParagraph("Paragraph 3. ");
```

## 5. การเริ่มต้นการติดตามการแก้ไข

หากต้องการติดตามการแก้ไขในเอกสารของคุณ คุณสามารถใช้รหัสต่อไปนี้:

```java
doc.startTrackRevisions("John Doe", new Date());
```

## 6. การแก้ไข

มาแก้ไขโดยเพิ่มอีกย่อหน้า:

```java
para = body.appendParagraph("Paragraph 4. ");
```

## 7. การยอมรับและปฏิเสธการแก้ไข

คุณสามารถยอมรับหรือปฏิเสธการแก้ไขในเอกสารของคุณได้โดยใช้ Aspose.Words สำหรับ Java สามารถจัดการการแก้ไขได้อย่างง่ายดายใน Microsoft Word หลังจากสร้างเอกสารแล้ว

## 8. การหยุดการติดตามการแก้ไข

หากต้องการหยุดการติดตามการแก้ไข ให้ใช้รหัสต่อไปนี้:

```java
doc.stopTrackRevisions();
```

## 9. การบันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารของคุณ:

```java
doc.save(outPath + "WorkingWithRevisions.AcceptRevisions.docx");
```

## 10. บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงพื้นฐานของการใช้การแก้ไขใน Aspose.Words สำหรับ Java คุณได้เรียนรู้วิธีสร้างเอกสาร เพิ่มเนื้อหา เริ่มต้นและหยุดการติดตามการแก้ไข และบันทึกเอกสารของคุณ

ตอนนี้คุณมีเครื่องมือที่จำเป็นในการจัดการการแก้ไขในแอปพลิเคชัน Java ของคุณอย่างมีประสิทธิภาพโดยใช้ Aspose.Words สำหรับ Java

## กรอกซอร์สโค้ดให้สมบูรณ์
```java
string outPath = "Your Output Directory";
Document doc = new Document();
Body body = doc.getFirstSection().getBody();
Paragraph para = body.getFirstParagraph();
// เพิ่มข้อความในย่อหน้าแรก จากนั้นเพิ่มอีกสองย่อหน้า
para.appendChild(new Run(doc, "Paragraph 1. "));
body.appendParagraph("Paragraph 2. ");
body.appendParagraph("Paragraph 3. ");
//เรามีสามย่อหน้า ซึ่งไม่มีรายการใดที่ถือเป็นการแก้ไขประเภทใดๆ
// หากเราเพิ่ม/ลบเนื้อหาใดๆ ในเอกสารขณะติดตามการแก้ไข
// สิ่งเหล่านี้จะแสดงในเอกสารและสามารถยอมรับ/ปฏิเสธได้
doc.startTrackRevisions("John Doe", new Date());
// ย่อหน้านี้เป็นเพียงการแก้ไขและจะมีการตั้งค่าสถานะตาม "IsInsertRevision"
para = body.appendParagraph("Paragraph 4. ");
Assert.assertTrue(para.isInsertRevision());
// รับคอลเลกชันย่อหน้าของเอกสารและลบย่อหน้า
ParagraphCollection paragraphs = body.getParagraphs();
Assert.assertEquals(4, paragraphs.getCount());
para = paragraphs.get(2);
para.remove();
// เนื่องจากเรากำลังติดตามการแก้ไข ย่อหน้านั้นยังคงอยู่ในเอกสาร โดยจะมีการตั้งค่า "IsDeleteRevision"
// และจะแสดงเป็นการแก้ไขใน Microsoft Word จนกว่าเราจะยอมรับหรือปฏิเสธการแก้ไขทั้งหมด
Assert.assertEquals(4, paragraphs.getCount());
Assert.assertTrue(para.isDeleteRevision());
// ย่อหน้าการแก้ไขการลบจะถูกลบออกเมื่อเรายอมรับการเปลี่ยนแปลง
doc.acceptAllRevisions();
Assert.assertEquals(3, paragraphs.getCount());
Assert.assertEquals(para.getRuns().getCount(), 0); //คือ Is.Empty
// การหยุดการติดตามการแก้ไขทำให้ข้อความนี้ปรากฏเป็นข้อความปกติ
// การแก้ไขจะไม่นับเมื่อมีการเปลี่ยนแปลงเอกสาร
doc.stopTrackRevisions();
// บันทึกเอกสาร
doc.save(outPath + "WorkingWithRevisions.AcceptRevisions.docx");
  
```

## คำถามที่พบบ่อย

### 1. ฉันสามารถใช้ Aspose.Words สำหรับ Java กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่

ไม่ Aspose.Words สำหรับ Java ได้รับการออกแบบมาโดยเฉพาะสำหรับการพัฒนา Java

### 2. Aspose.Words สำหรับ Java เข้ากันได้กับ Microsoft Word ทุกเวอร์ชันหรือไม่

ใช่ Aspose.Words สำหรับ Java ได้รับการออกแบบให้เข้ากันได้กับ Microsoft Word เวอร์ชันต่างๆ

### 3. ฉันสามารถติดตามการแก้ไขในเอกสาร Word ที่มีอยู่ได้หรือไม่

ได้ คุณสามารถใช้ Aspose.Words สำหรับ Java เพื่อติดตามการแก้ไขในเอกสาร Word ที่มีอยู่ได้

### 4. มีข้อกำหนดสิทธิ์การใช้งานสำหรับการใช้ Aspose.Words สำหรับ Java หรือไม่

 ใช่ คุณจะต้องได้รับใบอนุญาตเพื่อใช้ Aspose.Words สำหรับ Java ในโปรเจ็กต์ของคุณ คุณสามารถ[เข้าถึงใบอนุญาตได้ที่นี่](https://purchase.aspose.com/buy).

### 5. ฉันจะรับการสนับสนุนสำหรับ Aspose.Words สำหรับ Java ได้ที่ไหน

 หากมีคำถามหรือปัญหาใด ๆ คุณสามารถเยี่ยมชมได้ที่[Aspose.Words สำหรับฟอรัมสนับสนุน Java](https://forum.aspose.com/).

เริ่มต้นใช้งาน Aspose.Words สำหรับ Java วันนี้และปรับปรุงกระบวนการจัดการเอกสารของคุณ
