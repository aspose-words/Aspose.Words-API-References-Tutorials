---
title: การสร้างสารบัญใน Aspose.Words สำหรับ Java
linktitle: การสร้างสารบัญ
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีสร้างและปรับแต่งสารบัญ (TOC) โดยใช้ Aspose.Words สำหรับ Java สร้างเอกสารที่เป็นระเบียบและเป็นมืออาชีพได้อย่างง่ายดาย
type: docs
weight: 21
url: /th/java/document-manipulation/generating-table-of-contents/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการสร้างสารบัญใน Aspose.Words สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างสารบัญ (TOC) โดยใช้ Aspose.Words สำหรับ Java TOC เป็นคุณสมบัติที่สำคัญสำหรับการสร้างเอกสารที่มีการจัดระเบียบ เราจะกล่าวถึงวิธีปรับแต่งรูปลักษณ์และเค้าโครงของ TOC

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่า Aspose.Words สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว

## ขั้นตอนที่ 1: สร้างเอกสารใหม่

ขั้นแรก เรามาสร้างเอกสารใหม่เพื่อใช้งานกัน

```java
Document doc = new Document();
```

## ขั้นตอนที่ 2: ปรับแต่งสไตล์ TOC

หากต้องการปรับแต่งรูปลักษณ์ของ TOC คุณสามารถแก้ไขสไตล์ที่เกี่ยวข้องได้ ในตัวอย่างนี้ เราจะกำหนดให้รายการ TOC ระดับแรกเป็นตัวหนา

```java
doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_1).getFont().setBold(true);
```

## ขั้นตอนที่ 3: เพิ่มเนื้อหาลงในเอกสารของคุณ

คุณสามารถเพิ่มเนื้อหาของคุณลงในเอกสารได้ เนื้อหานี้จะถูกนำมาใช้เพื่อสร้าง TOC

## ขั้นตอนที่ 4: สร้าง TOC

หากต้องการสร้าง TOC ให้แทรกฟิลด์ TOC ในตำแหน่งที่ต้องการในเอกสารของคุณ ฟิลด์นี้จะถูกเติมโดยอัตโนมัติตามส่วนหัวและสไตล์ในเอกสารของคุณ

```java
// แทรกฟิลด์ TOC ในตำแหน่งที่ต้องการในเอกสารของคุณ
FieldToc fieldToc = new FieldToc();
doc.getFirstSection().getBody().getFirstParagraph().appendChild(fieldToc);
```

## ขั้นตอนที่ 5: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารด้วย TOC

```java
doc.save("your_output_path_here");
```

## การปรับแต่งแท็บหยุดใน TOC

คุณยังสามารถปรับแต่งแท็บหยุดใน TOC ของคุณเพื่อควบคุมเค้าโครงหมายเลขหน้าได้ ต่อไปนี้คือวิธีที่คุณสามารถเปลี่ยนแท็บหยุด:

```java
Document doc = new Document("Table of contents.docx");

for (Paragraph para : (Iterable<Paragraph>) doc.getChildNodes(NodeType.PARAGRAPH, true))
{
    if (para.getParagraphFormat().getStyle().getStyleIdentifier() >= StyleIdentifier.TOC_1 &&
        para.getParagraphFormat().getStyle().getStyleIdentifier() <= StyleIdentifier.TOC_9)
    {
        //รับแท็บแรกที่ใช้ในย่อหน้านี้ ซึ่งจัดแนวหมายเลขหน้า
        TabStop tab = para.getParagraphFormat().getTabStops().get(0);
        
        // นำแท็บเก่าออก
        para.getParagraphFormat().getTabStops().removeByPosition(tab.getPosition());
        
        // แทรกแท็บใหม่ในตำแหน่งที่แก้ไข (เช่น 50 หน่วยทางด้านซ้าย)
        para.getParagraphFormat().getTabStops().add(tab.getPosition() - 50.0, tab.getAlignment(), tab.getLeader());
    }
}

doc.save("output.docx");
```

ตอนนี้คุณมีสารบัญแบบกำหนดเองในเอกสารของคุณพร้อมแถบหยุดที่ปรับเปลี่ยนสำหรับการจัดตำแหน่งหมายเลขหน้า


## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีสร้างสารบัญ (TOC) โดยใช้ Aspose.Words สำหรับ Java ซึ่งเป็นไลบรารีอันทรงพลังสำหรับการทำงานกับเอกสาร Word TOC ที่มีโครงสร้างที่ดีเป็นสิ่งจำเป็นสำหรับการจัดระเบียบและการนำทางเอกสารที่มีความยาว และ Aspose.Words ก็มีเครื่องมือในการสร้างและปรับแต่ง TOC ได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนการจัดรูปแบบของรายการ TOC ได้อย่างไร

 คุณสามารถแก้ไขสไตล์ที่เกี่ยวข้องกับระดับ TOC ได้โดยใช้`doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_X)`โดยที่ X คือระดับ TOC

### ฉันจะเพิ่มระดับลงใน TOC ของฉันได้อย่างไร

หากต้องการเพิ่มระดับใน TOC ของคุณ คุณสามารถแก้ไขฟิลด์ TOC และระบุจำนวนระดับที่ต้องการได้

### ฉันสามารถเปลี่ยนตำแหน่งแท็บหยุดสำหรับรายการ TOC ที่ระบุได้หรือไม่

ได้ ดังที่แสดงในตัวอย่างโค้ดด้านบน คุณสามารถเปลี่ยนตำแหน่งแท็บหยุดสำหรับรายการ TOC ที่ระบุได้โดยการวนซ้ำแต่ละย่อหน้าและแก้ไขแท็บหยุดตามลำดับ