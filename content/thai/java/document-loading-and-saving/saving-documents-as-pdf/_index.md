---
title: บันทึกเอกสารเป็น PDF ใน Aspose.Words สำหรับ Java
linktitle: การบันทึกเอกสารเป็น PDF
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีบันทึกเอกสาร Word เป็น PDF โดยใช้ Aspose.Words สำหรับ Java ปรับแต่งแบบอักษร คุณสมบัติ และคุณภาพของภาพ คู่มือฉบับสมบูรณ์สำหรับการแปลง PDF
type: docs
weight: 22
url: /th/java/document-loading-and-saving/saving-documents-as-pdf/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการบันทึกเอกสารเป็น PDF ใน Aspose.Words สำหรับ Java

ในคำแนะนำทีละขั้นตอนนี้ เราจะมาดูวิธีบันทึกเอกสารเป็น PDF โดยใช้ Aspose.Words สำหรับ Java เราจะครอบคลุมแง่มุมต่างๆ ของการแปลง PDF และจัดเตรียมตัวอย่างโค้ดเพื่อทำให้กระบวนการง่ายขึ้น

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Words สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/java/).

## การแปลงเอกสารเป็น PDF

หากต้องการแปลงเอกสาร Word เป็น PDF คุณสามารถใช้ข้อมูลโค้ดต่อไปนี้:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 แทนที่`"input.docx"` พร้อมเส้นทางไปยังเอกสาร Word ของคุณและ`"output.pdf"` ด้วยเส้นทางไฟล์ PDF เอาต์พุตที่ต้องการ

## การควบคุมตัวเลือกการบันทึก PDF

 คุณสามารถควบคุมตัวเลือกการบันทึก PDF ต่างๆ ได้โดยใช้`PdfSaveOptions` ระดับ. ตัวอย่างเช่น คุณสามารถตั้งชื่อที่แสดงสำหรับเอกสาร PDF ได้ดังนี้:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## การฝังแบบอักษรในรูปแบบ PDF

หากต้องการฝังแบบอักษรใน PDF ที่สร้างขึ้น ให้ใช้รหัสต่อไปนี้:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## การปรับแต่งคุณสมบัติเอกสาร

คุณสามารถปรับแต่งคุณสมบัติของเอกสารในรูปแบบ PDF ที่สร้างขึ้นได้ ตัวอย่างเช่น:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## การส่งออกโครงสร้างเอกสาร

 หากต้องการส่งออกโครงสร้างเอกสาร ให้ตั้งค่า`exportDocumentStructure` ตัวเลือกในการ`true`: :

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## การบีบอัดภาพ

คุณสามารถควบคุมการบีบอัดภาพโดยใช้รหัสต่อไปนี้:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## การอัปเดตคุณสมบัติการพิมพ์ครั้งล่าสุด

หากต้องการอัปเดตคุณสมบัติ "พิมพ์ล่าสุด" ใน PDF ให้ใช้:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## การเรนเดอร์เอฟเฟกต์ DML 3D

สำหรับการเรนเดอร์เอฟเฟกต์ DML 3D ขั้นสูง ให้ตั้งค่าโหมดการเรนเดอร์:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## การประมาณค่ารูปภาพ

คุณสามารถเปิดใช้งานการแก้ไขภาพเพื่อปรับปรุงคุณภาพของภาพ:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## บทสรุป

Aspose.Words สำหรับ Java มีความสามารถที่ครอบคลุมในการแปลงเอกสาร Word เป็นรูปแบบ PDF พร้อมตัวเลือกที่ยืดหยุ่นและปรับแต่งได้ คุณสามารถควบคุมแง่มุมต่างๆ ของเอาต์พุต PDF รวมถึงแบบอักษร คุณสมบัติของเอกสาร การบีบอัดรูปภาพ และอื่นๆ

## คำถามที่พบบ่อย

### ฉันจะแปลงเอกสาร Word เป็น PDF โดยใช้ Aspose.Words สำหรับ Java ได้อย่างไร

หากต้องการแปลงเอกสาร Word เป็น PDF ให้ใช้รหัสต่อไปนี้:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 แทนที่`"input.docx"` พร้อมเส้นทางไปยังเอกสาร Word ของคุณและ`"output.pdf"` ด้วยเส้นทางไฟล์ PDF เอาต์พุตที่ต้องการ

### ฉันสามารถฝังแบบอักษรใน PDF ที่สร้างโดย Aspose.Words สำหรับ Java ได้หรือไม่

 ใช่ คุณสามารถฝังแบบอักษรใน PDF ได้โดยการตั้งค่า`setEmbedFullFonts` ตัวเลือกในการ`true` ใน`PdfSaveOptions`. นี่คือตัวอย่าง:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### ฉันจะปรับแต่งคุณสมบัติเอกสารใน PDF ที่สร้างขึ้นได้อย่างไร

 คุณสามารถปรับแต่งคุณสมบัติของเอกสารในรูปแบบ PDF ได้โดยใช้`setCustomPropertiesExport` ตัวเลือกใน`PdfSaveOptions`. ตัวอย่างเช่น:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### วัตถุประสงค์ของการบีบอัดรูปภาพใน Aspose.Words สำหรับ Java คืออะไร

 การบีบอัดรูปภาพช่วยให้คุณสามารถควบคุมคุณภาพและขนาดของรูปภาพใน PDF ที่สร้างขึ้นได้ คุณสามารถตั้งค่าโหมดการบีบอัดภาพโดยใช้`setImageCompression` ใน`PdfSaveOptions`.

### ฉันจะอัปเดตคุณสมบัติ "พิมพ์ล่าสุด" ใน PDF ได้อย่างไร

 คุณสามารถอัปเดตคุณสมบัติ "พิมพ์ล่าสุด" ใน PDF ได้โดยการตั้งค่า`setUpdateLastPrintedProperty` ถึง`true` ใน`PdfSaveOptions`. ซึ่งจะแสดงวันที่พิมพ์ครั้งล่าสุดในข้อมูลเมตา PDF

### ฉันจะปรับปรุงคุณภาพของภาพเมื่อแปลงเป็น PDF ได้อย่างไร

 หากต้องการปรับปรุงคุณภาพของภาพ ให้เปิดใช้งานการแก้ไขภาพโดยการตั้งค่า`setInterpolateImages` ถึง`true` ใน`PdfSaveOptions`. ซึ่งจะส่งผลให้รูปภาพใน PDF มีความนุ่มนวลและมีคุณภาพสูงขึ้น