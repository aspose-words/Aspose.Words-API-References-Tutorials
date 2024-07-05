---
title: การเพิ่มเนื้อหาโดยใช้ DocumentBuilder ใน Aspose.Words สำหรับ Java
linktitle: การเพิ่มเนื้อหาโดยใช้ DocumentBuilder
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: การสร้างเอกสารหลักด้วย Aspose.Words สำหรับ Java คำแนะนำทีละขั้นตอนในการเพิ่มข้อความ ตาราง รูปภาพ และอื่นๆ สร้างเอกสาร Word ที่น่าทึ่งได้อย่างง่ายดาย
type: docs
weight: 26
url: /th/java/document-manipulation/adding-content-using-documentbuilder/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการเพิ่มเนื้อหาโดยใช้ DocumentBuilder ใน Aspose.Words สำหรับ Java

ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีใช้ Aspose.Words สำหรับ DocumentBuilder ของ Java เพื่อเพิ่มเนื้อหาประเภทต่างๆ ลงในเอกสาร Word เราจะครอบคลุมถึงการแทรกข้อความ ตาราง กฎแนวนอน ฟิลด์แบบฟอร์ม HTML ไฮเปอร์ลิงก์ สารบัญ รูปภาพในบรรทัดและแบบลอย ย่อหน้า และอื่นๆ อีกมากมาย มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Words สำหรับ Java ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/java/).

## การเพิ่มข้อความ

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกย่อหน้าข้อความธรรมดา
builder.write("This is a simple text paragraph.");

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

## การเพิ่มตาราง

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// เริ่มโต๊ะ
Table table = builder.startTable();

// แทรกเซลล์และเนื้อหา
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// ปิดท้ายโต๊ะ
builder.endTable();

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

## การเพิ่มกฎแนวนอน

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกกฎแนวนอน
builder.insertHorizontalRule();

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

## การเพิ่มฟิลด์แบบฟอร์ม

### ช่องกรอกข้อความ

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกฟิลด์แบบฟอร์มการป้อนข้อความ
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

### ช่องทำเครื่องหมายช่องแบบฟอร์ม

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกฟิลด์แบบฟอร์มกล่องกาเครื่องหมาย
builder.insertCheckBox("CheckBox", true, true, 0);

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

### ฟิลด์ฟอร์มกล่องคำสั่งผสม

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// กำหนดรายการสำหรับกล่องคำสั่งผสม
String[] items = { "Option 1", "Option 2", "Option 3" };

// แทรกเขตข้อมูลฟอร์มกล่องคำสั่งผสม
builder.insertComboBox("DropDown", items, 0);

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

## การเพิ่ม HTML

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกเนื้อหา HTML
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

## การเพิ่มไฮเปอร์ลิงก์

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกไฮเปอร์ลิงก์
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com", เท็จ);
builder.getFont().clearFormatting();
builder.write(" for more information.");

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

## การเพิ่มสารบัญ

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกสารบัญ
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// เพิ่มเนื้อหาเอกสาร
// -

// อัพเดตสารบัญ
doc.updateFields();

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

## การเพิ่มรูปภาพ

### รูปภาพอินไลน์

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกรูปภาพในบรรทัด
builder.insertImage("path/to/your/image.png");

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

### รูปภาพลอยตัว

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกรูปภาพแบบลอย
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

## การเพิ่มย่อหน้า

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ตั้งค่าการจัดรูปแบบย่อหน้า
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// แทรกย่อหน้า
builder.writeln("This is a formatted paragraph.");

// บันทึกเอกสาร
doc.save("path/to/your/document.docx");
```

## ขั้นตอนที่ 10: การเลื่อนเคอร์เซอร์

 คุณสามารถควบคุมตำแหน่งเคอร์เซอร์ภายในเอกสารได้โดยใช้วิธีการต่างๆ เช่น`moveToParagraph`, `moveToCell`และอื่น ๆ. นี่คือตัวอย่าง:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ย้ายเคอร์เซอร์ไปยังย่อหน้าเฉพาะ
builder.moveToParagraph(2, 0);

// เพิ่มเนื้อหาที่ตำแหน่งเคอร์เซอร์ใหม่
builder.writeln("This is the 3rd paragraph.");
```

นี่คือการดำเนินการทั่วไปบางอย่างที่คุณสามารถทำได้โดยใช้ Aspose.Words สำหรับ DocumentBuilder ของ Java สำรวจเอกสารประกอบของไลบรารีเพื่อดูคุณสมบัติขั้นสูงและตัวเลือกการปรับแต่งเพิ่มเติม ขอให้มีความสุขกับการสร้างเอกสาร!


## บทสรุป

ในคู่มือที่ครอบคลุมนี้ เราได้สำรวจความสามารถของ Aspose.Words สำหรับ DocumentBuilder ของ Java เพื่อเพิ่มเนื้อหาประเภทต่างๆ ลงในเอกสาร Word เราได้ครอบคลุมถึงข้อความ ตาราง กฎแนวนอน ฟิลด์แบบฟอร์ม HTML ไฮเปอร์ลิงก์ สารบัญ รูปภาพ ย่อหน้า และการเลื่อนเคอร์เซอร์

## คำถามที่พบบ่อย

### ถาม: Aspose.Words สำหรับ Java คืออะไร

ตอบ: Aspose.Words สำหรับ Java เป็นไลบรารี Java ที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการเอกสาร Microsoft Word โดยทางโปรแกรม โดยมีคุณสมบัติที่หลากหลายสำหรับการสร้างเอกสาร การจัดรูปแบบ และการแทรกเนื้อหา

### ถาม: ฉันจะเพิ่มสารบัญลงในเอกสารได้อย่างไร

ตอบ: หากต้องการเพิ่มสารบัญ ให้ใช้`DocumentBuilder` เพื่อแทรกฟิลด์สารบัญลงในเอกสารของคุณ ตรวจสอบให้แน่ใจว่าได้อัปเดตฟิลด์ในเอกสารหลังจากเพิ่มเนื้อหาเพื่อเติมสารบัญ นี่คือตัวอย่าง:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกฟิลด์สารบัญ
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// เพิ่มเนื้อหาเอกสาร
// -

// อัพเดตสารบัญ
doc.updateFields();
```

### ถาม: ฉันจะแทรกรูปภาพลงในเอกสารโดยใช้ Aspose.Words สำหรับ Java ได้อย่างไร

 ตอบ: คุณสามารถแทรกรูปภาพทั้งแบบอินไลน์และแบบลอยได้โดยใช้`DocumentBuilder`- นี่คือตัวอย่างของทั้งสอง:

#### รูปภาพอินไลน์:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกรูปภาพในบรรทัด
builder.insertImage("path/to/your/image.png");
```

#### รูปภาพลอยตัว:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกรูปภาพแบบลอย
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### ถาม: ฉันสามารถจัดรูปแบบข้อความและย่อหน้าเมื่อเพิ่มเนื้อหาได้หรือไม่

 ตอบ: ได้ คุณสามารถจัดรูปแบบข้อความและย่อหน้าได้โดยใช้`DocumentBuilder`- คุณสามารถตั้งค่าคุณสมบัติแบบอักษร การจัดแนวย่อหน้า การเยื้อง และอื่นๆ ได้ นี่คือตัวอย่าง:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ตั้งค่าการจัดรูปแบบแบบอักษรและย่อหน้า
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// แทรกย่อหน้าที่มีการจัดรูปแบบ
builder.writeln("This is a formatted paragraph.");
```

### ถาม: ฉันจะเลื่อนเคอร์เซอร์ไปยังตำแหน่งเฉพาะภายในเอกสารได้อย่างไร

 ตอบ: คุณสามารถควบคุมตำแหน่งเคอร์เซอร์ได้โดยใช้วิธีการเช่น`moveToParagraph`, `moveToCell`และอื่น ๆ. นี่คือตัวอย่าง:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ย้ายเคอร์เซอร์ไปยังย่อหน้าเฉพาะ
builder.moveToParagraph(2, 0);

// เพิ่มเนื้อหาที่ตำแหน่งเคอร์เซอร์ใหม่
builder.writeln("This is the 3rd paragraph.");
```

ต่อไปนี้เป็นคำถามและคำตอบทั่วไปที่จะช่วยคุณเริ่มต้นใช้งาน Aspose.Words สำหรับ DocumentBuilder ของ Java หากคุณมีคำถามเพิ่มเติมหรือต้องการความช่วยเหลือเพิ่มเติม โปรดดูที่[เอกสารของห้องสมุด](https://reference.aspose.com/words/java/) หรือขอความช่วยเหลือจากชุมชน Aspose.Words และแหล่งข้อมูลสนับสนุน