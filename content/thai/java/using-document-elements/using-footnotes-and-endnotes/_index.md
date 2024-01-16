---
title: การใช้เชิงอรรถและอ้างอิงท้ายเรื่องใน Aspose.Words สำหรับ Java
linktitle: การใช้เชิงอรรถและอ้างอิงท้ายเรื่อง
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้การใช้เชิงอรรถและอ้างอิงท้ายเรื่องอย่างมีประสิทธิภาพใน Aspose.Words สำหรับ Java เสริมทักษะการจัดรูปแบบเอกสารของคุณวันนี้!
type: docs
weight: 13
url: /th/java/using-document-elements/using-footnotes-and-endnotes/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการใช้เชิงอรรถและอ้างอิงท้ายเรื่องใน Aspose.Words สำหรับ Java เชิงอรรถและอ้างอิงท้ายเรื่องเป็นองค์ประกอบสำคัญในการจัดรูปแบบเอกสาร ซึ่งมักใช้สำหรับการอ้างอิง การอ้างอิง และข้อมูลเพิ่มเติม Aspose.Words สำหรับ Java มีฟังก์ชันการทำงานที่มีประสิทธิภาพเพื่อทำงานกับเชิงอรรถและอ้างอิงท้ายเรื่องได้อย่างราบรื่น

## 1. ข้อมูลเบื้องต้นเกี่ยวกับเชิงอรรถและอ้างอิงท้ายเรื่อง

เชิงอรรถและอ้างอิงท้ายเรื่องเป็นคำอธิบายประกอบที่ให้ข้อมูลเสริมหรือการอ้างอิงภายในเอกสาร เชิงอรรถจะปรากฏที่ด้านล่างของหน้า ในขณะที่อ้างอิงท้ายเรื่องจะถูกรวบรวมไว้ที่ส่วนท้ายของส่วนหรือเอกสาร โดยทั่วไปมักใช้ในเอกสารทางวิชาการ รายงาน และเอกสารทางกฎหมายเพื่ออ้างอิงแหล่งที่มาหรือชี้แจงเนื้อหา

## 2. การตั้งค่าสภาพแวดล้อมของคุณ

ก่อนที่เราจะเจาะลึกในการทำงานกับเชิงอรรถและอ้างอิงท้ายเรื่อง คุณต้องตั้งค่าสภาพแวดล้อมการพัฒนาของคุณก่อน ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่า Aspose.Words สำหรับ Java API ในโปรเจ็กต์ของคุณแล้ว

## 3. การเพิ่มเชิงอรรถลงในเอกสารของคุณ

เมื่อต้องการเพิ่มเชิงอรรถลงในเอกสารของคุณ ให้ทำตามขั้นตอนเหล่านี้:
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

public void getFootnoteOptions(){
    Document doc = new Document(dataDir + "Document.docx");
    
    // ระบุจำนวนคอลัมน์ที่ใช้จัดรูปแบบพื้นที่เชิงอรรถ
    doc.getFootnoteOptions().setColumns(3);
    doc.save("Your Directory Path" + "WorkingWithFootnotes.SetFootNoteColumns.docx");
}
```

## 4. การแก้ไขตัวเลือกเชิงอรรถ

คุณสามารถแก้ไขตัวเลือกเชิงอรรถเพื่อปรับแต่งรูปลักษณ์และลักษณะการทำงานได้ มีวิธีดังนี้:
```java
@Test
public void setFootnoteAndEndNotePosition() throws Exception {
    Document doc = new Document(dataDir + "Document.docx");
    
    doc.getFootnoteOptions().setPosition(FootnotePosition.BENEATH_TEXT);
    doc.getEndnoteOptions().setPosition(EndnotePosition.END_OF_SECTION);
    
    doc.save(outPath + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
}
```

## 5. การเพิ่มอ้างอิงท้ายเรื่องลงในเอกสารของคุณ

การเพิ่มอ้างอิงท้ายเรื่องลงในเอกสารของคุณทำได้ง่ายตรงไปตรงมา นี่คือตัวอย่าง:
```java
@Test
public void setEndnoteOptions() throws Exception {
    Document doc = new Document(dataDir + "Document.docx");
    DocumentBuilder builder = new DocumentBuilder(doc);
    
    builder.write("Some text");
    builder.insertFootnote(FootnoteType.ENDNOTE, "Footnote text.");
    
    EndnoteOptions option = doc.getEndnoteOptions();
    option.setRestartRule(FootnoteNumberingRule.RESTART_PAGE);
    option.setPosition(EndnotePosition.END_OF_SECTION);
    
    doc.save(outPath + "WorkingWithFootnotes.SetEndnoteOptions.docx");
}
```

## 6. การปรับแต่งการตั้งค่าอ้างอิงท้ายเรื่อง

คุณสามารถปรับแต่งการตั้งค่าอ้างอิงท้ายเรื่องเพิ่มเติมเพื่อให้ตรงตามข้อกำหนดเอกสารของคุณได้

## กรอกซอร์สโค้ดให้สมบูรณ์
```java
	string dataDir = "Your Document Directory";
	string outPath = "Your Output Directory";
	public void getFootnoteOptions(){
        Document doc = new Document(dataDir + "Document.docx");
        // ระบุจำนวนคอลัมน์ที่ใช้จัดรูปแบบพื้นที่เชิงอรรถ
        doc.getFootnoteOptions().setColumns(3);
        doc.save("Your Directory Path" + "WorkingWithFootnotes.SetFootNoteColumns.docx");
    }
    @Test
    public void setFootnoteAndEndNotePosition() throws Exception
    {
        Document doc = new Document(dataDir + "Document.docx");
        doc.getFootnoteOptions().setPosition(FootnotePosition.BENEATH_TEXT);
        doc.getEndnoteOptions().setPosition(EndnotePosition.END_OF_SECTION);
        doc.save(outPath + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
    }
    @Test
    public void setEndnoteOptions() throws Exception
    {
        Document doc = new Document(dataDir + "Document.docx");
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.write("Some text");
        builder.insertFootnote(FootnoteType.ENDNOTE, "Footnote text.");
        EndnoteOptions option = doc.getEndnoteOptions();
        option.setRestartRule(FootnoteNumberingRule.RESTART_PAGE);
        option.setPosition(EndnotePosition.END_OF_SECTION);
        doc.save(outPath + "WorkingWithFootnotes.SetEndnoteOptions.docx");
	}
```

## 7. บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีการทำงานกับเชิงอรรถและอ้างอิงท้ายเรื่องใน Aspose.Words สำหรับ Java คุณสมบัติเหล่านี้มีประโยชน์อย่างมากสำหรับการสร้างเอกสารที่มีโครงสร้างที่ดีพร้อมการอ้างอิงและการอ้างอิงที่เหมาะสม

เมื่อคุณได้เรียนรู้วิธีใช้เชิงอรรถและอ้างอิงท้ายเรื่องแล้ว คุณสามารถปรับปรุงการจัดรูปแบบเอกสารของคุณและทำให้เนื้อหาของคุณเป็นมืออาชีพมากขึ้นได้

### คำถามที่พบบ่อย

### 1. เชิงอรรถและอ้างอิงท้ายเรื่องแตกต่างกันอย่างไร?
เชิงอรรถจะปรากฏที่ด้านล่างของหน้า ในขณะที่อ้างอิงท้ายเรื่องจะถูกรวบรวมไว้ที่ส่วนท้ายของส่วนหรือเอกสาร

### 2. ฉันจะเปลี่ยนตำแหน่งของเชิงอรรถหรืออ้างอิงท้ายเรื่องได้อย่างไร?
 คุณสามารถใช้`setPosition` วิธีการเปลี่ยนตำแหน่งของเชิงอรรถหรืออ้างอิงท้ายเรื่อง

### 3. ฉันสามารถปรับแต่งการจัดรูปแบบของเชิงอรรถและอ้างอิงท้ายเรื่องได้หรือไม่
ใช่ คุณสามารถปรับแต่งการจัดรูปแบบของเชิงอรรถและอ้างอิงท้ายเรื่องได้โดยใช้ Aspose.Words สำหรับ Java

### 4. เชิงอรรถและอ้างอิงท้ายเรื่องมีความสำคัญในการจัดรูปแบบเอกสารหรือไม่?
ใช่ เชิงอรรถและอ้างอิงท้ายเรื่องเป็นสิ่งจำเป็นสำหรับการอ้างอิงและข้อมูลเพิ่มเติมในเอกสาร

สำรวจคุณสมบัติเพิ่มเติมของ Aspose.Words สำหรับ Java และเพิ่มความสามารถในการสร้างเอกสารของคุณได้ตามสบาย ขอให้มีความสุขในการเขียนโค้ด!