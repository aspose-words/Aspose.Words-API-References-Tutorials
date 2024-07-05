---
title: การลบเนื้อหาออกจากเอกสารใน Aspose.Words สำหรับ Java
linktitle: การลบเนื้อหาออกจากเอกสาร
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีลบเนื้อหาออกจากเอกสาร Word ใน Java โดยใช้ Aspose.Words สำหรับ Java ลบตัวแบ่งหน้า ตัวแบ่งส่วน และอื่นๆ เพิ่มประสิทธิภาพการประมวลผลเอกสารของคุณ
type: docs
weight: 16
url: /th/java/document-manipulation/removing-content-from-documents/
---

## รู้เบื้องต้นเกี่ยวกับ Aspose.Words สำหรับ Java

ก่อนที่เราจะเจาะลึกเทคนิคการลบ เรามาแนะนำ Aspose.Words สำหรับ Java กันก่อน เป็น Java API ที่มีคุณสมบัติมากมายสำหรับการทำงานกับเอกสาร Word คุณสามารถสร้าง แก้ไข แปลง และจัดการเอกสาร Word ได้อย่างราบรื่นโดยใช้ไลบรารีนี้

## การลบตัวแบ่งหน้า

ตัวแบ่งหน้ามักใช้เพื่อควบคุมเค้าโครงของเอกสาร อย่างไรก็ตาม อาจมีบางกรณีที่คุณจำเป็นต้องลบออก ต่อไปนี้คือวิธีที่คุณสามารถลบตัวแบ่งหน้าโดยใช้ Aspose.Words สำหรับ Java:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);
for (Paragraph para : (Iterable<Paragraph>) paragraphs) {
    if (para.getParagraphFormat().getPageBreakBefore()) {
        para.getParagraphFormat().setPageBreakBefore(false);
    }
    for (Run run : para.getRuns()) {
        if (run.getText().contains(ControlChar.PAGE_BREAK)) {
            run.setText(run.getText().replace(ControlChar.PAGE_BREAK, ""));
        }
    }
}
doc.save("Your Directory Path" + "RemoveContent.RemovePageBreaks.docx");
```

ข้อมูลโค้ดนี้จะวนซ้ำย่อหน้าต่างๆ ในเอกสาร ตรวจสอบตัวแบ่งหน้าและลบออก

## การลบตัวแบ่งส่วน

ตัวแบ่งส่วนจะแบ่งเอกสารออกเป็นส่วนๆ โดยมีรูปแบบที่แตกต่างกัน หากต้องการลบตัวแบ่งส่วน ให้ทำตามขั้นตอนเหล่านี้:

```java
for (int i = doc.getSections().getCount() - 2; i >= 0; i--) {
    doc.getLastSection().prependContent(doc.getSections().get(i));
    doc.getSections().get(i).remove();
}
```

โค้ดนี้จะวนซ้ำส่วนต่างๆ ในลำดับย้อนกลับ รวมเนื้อหาของส่วนปัจจุบันเข้ากับส่วนสุดท้าย จากนั้นจึงลบส่วนที่คัดลอกออก

## การถอดส่วนท้าย

ส่วนท้ายในเอกสาร Word มักจะมีหมายเลขหน้า วันที่ หรือข้อมูลอื่นๆ หากคุณต้องการลบออก คุณสามารถใช้รหัสต่อไปนี้:

```java
Document doc = new Document("Your Directory Path" + "Header and footer types.docx");
for (Section section : doc.getSections()) {
    HeaderFooter footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_FIRST);
    footer.remove();
    footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
    footer.remove();
    footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_EVEN);
    footer.remove();
}
doc.save("Your Directory Path" + "RemoveContent.RemoveFooters.docx");
```

โค้ดนี้จะลบส่วนท้ายทุกประเภท (ส่วนแรก หลัก และคู่) ออกจากแต่ละส่วนในเอกสาร

## การลบสารบัญ

เขตข้อมูลสารบัญ (TOC) จะสร้างตารางแบบไดนามิกที่แสดงรายการส่วนหัวและหมายเลขหน้า หากต้องการลบ TOC คุณสามารถใช้รหัสต่อไปนี้:

```java
Document doc = new Document("Your Directory Path" + "Table of contents.docx");
removeTableOfContents(doc, 0);
doc.save("Your Directory Path" + "RemoveContent.RemoveToc.doc");
```

 รหัสนี้กำหนดวิธีการ`removeTableOfContents` ที่ลบ TOC ที่ระบุออกจากเอกสาร


## บทสรุป

ในบทความนี้ เราได้สำรวจวิธีการลบเนื้อหาประเภทต่างๆ ออกจากเอกสาร Word โดยใช้ Aspose.Words สำหรับ Java ไม่ว่าจะเป็นตัวแบ่งหน้า ตัวแบ่งส่วน ส่วนท้าย หรือสารบัญ Aspose.Words มีเครื่องมือในการจัดการเอกสารของคุณอย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันจะลบตัวแบ่งหน้าเฉพาะได้อย่างไร

หากต้องการลบตัวแบ่งหน้า ให้วนซ้ำย่อหน้าในเอกสารของคุณและล้างแอตทริบิวต์ตัวแบ่งหน้าสำหรับย่อหน้าที่ต้องการ

### ฉันสามารถลบส่วนหัวและส่วนท้ายได้หรือไม่

ได้ คุณสามารถลบทั้งส่วนหัวและส่วนท้ายออกจากเอกสารของคุณได้โดยปฏิบัติตามแนวทางที่คล้ายกันดังที่แสดงในบทความสำหรับส่วนท้าย

### Aspose.Words สำหรับ Java เข้ากันได้กับรูปแบบเอกสาร Word ล่าสุดหรือไม่

ใช่ Aspose.Words สำหรับ Java รองรับรูปแบบเอกสาร Word ล่าสุด จึงรับประกันความเข้ากันได้กับเอกสารสมัยใหม่

### Aspose.Words สำหรับ Java มีคุณสมบัติการจัดการเอกสารอื่นใดอีกบ้าง

Aspose.Words for Java นำเสนอฟีเจอร์ที่หลากหลาย รวมถึงการสร้างเอกสาร การแก้ไข การแปลง และอื่นๆ อีกมากมาย คุณสามารถสำรวจเอกสารประกอบเพื่อดูข้อมูลโดยละเอียด