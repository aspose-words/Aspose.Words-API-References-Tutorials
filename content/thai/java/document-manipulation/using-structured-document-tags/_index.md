---
title: การใช้แท็กเอกสารที่มีโครงสร้าง (SDT) ใน Aspose.Words สำหรับ Java
linktitle: การใช้แท็กเอกสารที่มีโครงสร้าง (SDT)
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีใช้แท็กเอกสารที่มีโครงสร้าง (SDT) ใน Aspose.Words สำหรับ Java พร้อมคำแนะนำที่ครอบคลุมนี้ สร้าง แก้ไข และเชื่อมโยง SDT กับข้อมูล XML แบบกำหนดเอง
type: docs
weight: 19
url: /th/java/document-manipulation/using-structured-document-tags/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการใช้แท็กเอกสารที่มีโครงสร้าง (SDT) ใน Aspose.Words สำหรับ Java

แท็กเอกสารที่มีโครงสร้าง (SDT) เป็นคุณสมบัติที่มีประสิทธิภาพใน Aspose.Words สำหรับ Java ที่ช่วยให้คุณสามารถสร้างและจัดการเนื้อหาที่มีโครงสร้างภายในเอกสารของคุณได้ ในคู่มือที่ครอบคลุมนี้ เราจะอธิบายแง่มุมต่างๆ ของการใช้ SDT ใน Aspose.Words สำหรับ Java ไม่ว่าคุณจะเป็นมือใหม่หรือนักพัฒนาที่มีประสบการณ์ คุณจะพบข้อมูลเชิงลึกอันมีค่าและตัวอย่างที่เป็นประโยชน์ในบทความนี้

## เริ่มต้นใช้งาน

ก่อนที่เราจะเจาะลึกรายละเอียด เรามาตั้งค่าสภาพแวดล้อมและสร้าง SDT พื้นฐานกันก่อน ในส่วนนี้ เราจะกล่าวถึงหัวข้อต่อไปนี้:

- การสร้างเอกสารใหม่
- การเพิ่มแท็กเอกสารที่มีโครงสร้าง
- กำลังบันทึกเอกสาร

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// สร้างแท็กเอกสารที่มีโครงสร้างประเภท CHECKBOX
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// บันทึกเอกสาร
doc.save("WorkingWithSDT.docx");
```

## การตรวจสอบสถานะปัจจุบันของช่องทำเครื่องหมาย SDT

เมื่อคุณเพิ่มช่องทำเครื่องหมาย SDT ลงในเอกสารแล้ว คุณอาจต้องการตรวจสอบสถานะปัจจุบันโดยทางโปรแกรม สิ่งนี้มีประโยชน์เมื่อคุณต้องการตรวจสอบอินพุตของผู้ใช้หรือดำเนินการเฉพาะตามสถานะช่องทำเครื่องหมาย

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // เลือกช่องทำเครื่องหมายแล้ว
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## การปรับเปลี่ยนการควบคุมเนื้อหา

ในส่วนนี้ เราจะสำรวจวิธีปรับเปลี่ยนการควบคุมเนื้อหาภายในเอกสารของคุณ เราจะครอบคลุมการควบคุมเนื้อหาสามประเภท: ข้อความธรรมดา รายการดรอปดาวน์ และรูปภาพ

### การปรับเปลี่ยนการควบคุมเนื้อหาข้อความธรรมดา

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // ล้างเนื้อหาที่มีอยู่
    sdtPlainText.removeAllChildren();

    // เพิ่มข้อความใหม่
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### การแก้ไขการควบคุมเนื้อหารายการแบบหล่นลง

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // เลือกรายการที่สองจากรายการ
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### การปรับเปลี่ยนการควบคุมเนื้อหารูปภาพ

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // แทนที่รูปภาพด้วยรูปภาพใหม่
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## การสร้างการควบคุมเนื้อหา ComboBox

ComboBox Content Control อนุญาตให้ผู้ใช้เลือกจากรายการตัวเลือกที่กำหนดไว้ล่วงหน้า มาสร้างหนึ่งในเอกสารของเรากัน

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## การทำงานกับการควบคุมเนื้อหา Rich Text

การควบคุมเนื้อหา Rich Text เหมาะอย่างยิ่งสำหรับการเพิ่มข้อความที่จัดรูปแบบลงในเอกสารของคุณ มาสร้างอันหนึ่งและตั้งค่าเนื้อหากันดีกว่า

```java
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RICH_TEXT, MarkupLevel.BLOCK);
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.setText("Hello World");
run.getFont().setColor(Color.GREEN);
para.getRuns().add(run);
sdtRichText.getChildNodes().add(para);
doc.getFirstSection().getBody().appendChild(sdtRichText);

doc.save("RichTextDocument.docx");
```

## การตั้งค่าสไตล์การควบคุมเนื้อหา

คุณสามารถใช้สไตล์กับตัวควบคุมเนื้อหาเพื่อปรับปรุงลักษณะที่ปรากฏของเอกสารของคุณได้ มาดูวิธีการตั้งค่าสไตล์ของตัวควบคุมเนื้อหา

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//ใช้สไตล์ที่กำหนดเอง
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## การเชื่อมโยง SDT กับข้อมูล XML แบบกำหนดเอง

ในบางสถานการณ์ คุณอาจต้องผูก SDT กับข้อมูล XML แบบกำหนดเองสำหรับการสร้างเนื้อหาแบบไดนามิก เรามาสำรวจวิธีการบรรลุเป้าหมายนี้กัน

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## การสร้างตารางที่มีส่วนที่ทำซ้ำซึ่งแมปกับข้อมูล XML แบบกำหนดเอง

ตารางที่มีส่วนที่ซ้ำกันจะมีประโยชน์อย่างยิ่งในการนำเสนอข้อมูลที่มีโครงสร้าง มาสร้างตารางดังกล่าวและแมปกับข้อมูล XML แบบกำหนดเองกัน

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
CustomXmlPart xmlPart = doc.getCustomXmlParts().add("Books", "<books>...</books>");
Table table = builder.startTable();
builder.insertCell();
builder.write("Title");
builder.insertCell();
builder.write("Author");
builder.endRow();
builder.endTable();

StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION, MarkupLevel.ROW);
repeatingSectionSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book", "");
table.appendChild(repeatingSectionSdt);

StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION_ITEM, MarkupLevel.ROW);
repeatingSectionSdt.appendChild(repeatingSectionItemSdt);

Row row = new Row(doc);
repeatingSectionItemSdt.appendChild(row);

StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
titleSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.appendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
authorSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.appendChild(authorSdt);

doc.save("RepeatingTableDocument.docx");
```

## การทำงานกับแท็กเอกสารที่มีโครงสร้างแบบหลายส่วน

แท็กเอกสารที่มีโครงสร้างสามารถขยายได้หลายส่วนในเอกสาร ในส่วนนี้ เราจะมาดูวิธีทำงานกับ SDT แบบหลายส่วน

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## บทสรุป

แท็กเอกสารที่มีโครงสร้างใน Aspose.Words สำหรับ Java มอบวิธีที่หลากหลายในการจัดการและจัดรูปแบบเนื้อหาภายในเอกสารของคุณ ไม่ว่าคุณจะต้องการสร้างเทมเพลต แบบฟอร์ม หรือเอกสารแบบไดนามิก SDT มอบความยืดหยุ่นและการควบคุมที่คุณต้องการ โดยการปฏิบัติตามตัวอย่างและแนวทางที่ให้ไว้ในบทความนี้ คุณจะสามารถควบคุมประสิทธิภาพของ SDT เพื่อปรับปรุงงานการประมวลผลเอกสารของคุณได้

## คำถามที่พบบ่อย

### วัตถุประสงค์ของแท็กเอกสารที่มีโครงสร้าง (SDT) คืออะไร?

แท็กเอกสารที่มีโครงสร้าง (SDT) มีวัตถุประสงค์ในการจัดระเบียบและจัดรูปแบบเนื้อหาภายในเอกสาร ทำให้ง่ายต่อการสร้างเทมเพลต แบบฟอร์ม และเอกสารที่มีโครงสร้าง

### ฉันจะตรวจสอบสถานะปัจจุบันของ Checkbox SDT ได้อย่างไร

 คุณสามารถตรวจสอบสถานะปัจจุบันของช่องทำเครื่องหมาย SDT ได้โดยใช้`setChecked` วิธีการดังแสดงในบทความ

### ฉันสามารถใช้สไตล์กับการควบคุมเนื้อหาได้หรือไม่

ได้ คุณสามารถใช้สไตล์กับการควบคุมเนื้อหาเพื่อปรับแต่งรูปลักษณ์ในเอกสารได้

### เป็นไปได้หรือไม่ที่จะผูก SDT กับข้อมูล XML ที่กำหนดเอง

ใช่ คุณสามารถผูก SDT กับข้อมูล XML แบบกำหนดเองได้ ซึ่งช่วยให้สามารถสร้างเนื้อหาแบบไดนามิกและการแมปข้อมูลได้

### การทำซ้ำส่วนที่อยู่ใน SDT คืออะไร

การทำซ้ำส่วนใน SDT ช่วยให้คุณสร้างตารางที่มีข้อมูลไดนามิก โดยสามารถทำซ้ำแถวตามข้อมูล XML ที่แมปได้