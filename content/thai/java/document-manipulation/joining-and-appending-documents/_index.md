---
title: การรวมและผนวกเอกสารใน Aspose.Words สำหรับ Java
linktitle: การเข้าร่วมและแนบเอกสาร
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีเข้าร่วมและผนวกเอกสารอย่างง่ายดายโดยใช้ Aspose.Words สำหรับ Java รักษาการจัดรูปแบบ จัดการส่วนท้ายของส่วนหัว และอื่นๆ
type: docs
weight: 30
url: /th/java/document-manipulation/joining-and-appending-documents/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการเข้าร่วมและการผนวกเอกสารใน Aspose.Words สำหรับ Java

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการเข้าร่วมและผนวกเอกสารโดยใช้ไลบรารี Aspose.Words สำหรับ Java คุณจะได้เรียนรู้วิธีผสานเอกสารหลายชุดได้อย่างราบรื่นโดยยังคงรูปแบบและโครงสร้างไว้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่า Aspose.Words สำหรับ Java API ในโปรเจ็กต์ Java ของคุณแล้ว

## ตัวเลือกการเข้าร่วมเอกสาร

### ผนวกอย่างง่าย

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### ผนวกด้วยตัวเลือกรูปแบบการนำเข้า

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### ผนวกเข้ากับเอกสารเปล่า

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### ต่อท้ายด้วยการแปลงหมายเลขหน้า

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // แปลงช่อง NUMPAGES ช่อง
dstDoc.updatePageLayout(); // ปรับปรุงเค้าโครงหน้าให้เลขถูกต้อง
```

## การจัดการการตั้งค่าหน้าต่างๆ

เมื่อผนวกเอกสารด้วยการตั้งค่าหน้าที่แตกต่างกัน:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// ตรวจสอบให้แน่ใจว่าการตั้งค่าการตั้งค่าหน้าตรงกับเอกสารปลายทาง
```

## การรวมเอกสารด้วยสไตล์ที่แตกต่าง

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## พฤติกรรมสไตล์สมาร์ท

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## การแทรกเอกสารด้วย DocumentBuilder

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## การรักษาหมายเลขแหล่งที่มา

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## การจัดการกล่องข้อความ

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## การจัดการส่วนหัวและส่วนท้าย

### การเชื่อมโยงส่วนหัวและส่วนท้าย

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### การยกเลิกการเชื่อมโยงส่วนหัวและส่วนท้าย

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## บทสรุป

Aspose.Words สำหรับ Java มีเครื่องมือที่ยืดหยุ่นและมีประสิทธิภาพสำหรับการเข้าร่วมและผนวกเอกสาร ไม่ว่าคุณจะต้องรักษาการจัดรูปแบบ จัดการการตั้งค่าหน้าต่างๆ หรือจัดการส่วนหัวและส่วนท้าย ทดลองใช้เทคนิคเหล่านี้เพื่อตอบสนองความต้องการในการประมวลผลเอกสารเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะรวมเอกสารที่มีสไตล์ต่างกันได้อย่างราบรื่นได้อย่างไร

 หากต้องการรวมเอกสารที่มีสไตล์ต่างกัน ให้ใช้`ImportFormatMode.USE_DESTINATION_STYLES` เมื่อต่อท้าย

### ฉันสามารถคงหมายเลขหน้าไว้เมื่อผนวกเอกสารได้หรือไม่

 ใช่ คุณสามารถรักษาหมายเลขหน้าไว้ได้โดยใช้`convertNumPageFieldsToPageRef` วิธีการและการอัพเดตเค้าโครงหน้า

### พฤติกรรมสไตล์อัจฉริยะคืออะไร?

 Smart Style Behavior ช่วยรักษาสไตล์ที่สอดคล้องกันเมื่อผนวกเอกสาร ใช้กับ`ImportFormatOptions` เพื่อผลลัพธ์ที่ดีกว่า

### ฉันจะจัดการกล่องข้อความเมื่อผนวกเอกสารได้อย่างไร

ชุด`importFormatOptions.setIgnoreTextBoxes(false)` เพื่อรวมกล่องข้อความในระหว่างการต่อท้าย

### จะทำอย่างไรถ้าฉันต้องการเชื่อมโยง/ยกเลิกการเชื่อมโยงส่วนหัวและส่วนท้ายระหว่างเอกสาร?

 คุณสามารถเชื่อมโยงส่วนหัวและส่วนท้ายด้วย`linkToPrevious(true)` หรือยกเลิกการเชื่อมโยงกับ`linkToPrevious(false)` ตามความจำเป็น.