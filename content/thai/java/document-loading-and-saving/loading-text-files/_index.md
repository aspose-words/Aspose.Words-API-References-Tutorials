---
title: กำลังโหลดไฟล์ข้อความด้วย Aspose.Words สำหรับ Java
linktitle: กำลังโหลดไฟล์ข้อความด้วย
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: ปลดล็อกพลังของ Aspose.Words สำหรับ Java เรียนรู้การโหลดเอกสารข้อความ จัดการรายการ จัดการช่องว่าง และควบคุมทิศทางของข้อความ
type: docs
weight: 13
url: /th/java/document-loading-and-saving/loading-text-files/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการโหลดไฟล์ข้อความด้วย Aspose.Words สำหรับ Java

ในคู่มือนี้ เราจะสำรวจวิธีการโหลดไฟล์ข้อความโดยใช้ Aspose.Words สำหรับ Java และจัดการไฟล์เหล่านั้นเป็นเอกสาร Word เราจะครอบคลุมแง่มุมต่างๆ เช่น การตรวจหารายการ การจัดการช่องว่าง และการควบคุมทิศทางของข้อความ

## ขั้นตอนที่ 1: การตรวจจับรายการ

หากต้องการโหลดเอกสารข้อความและตรวจหารายการ คุณสามารถทำตามขั้นตอนเหล่านี้:

```java
// สร้างเอกสารข้อความธรรมดาในรูปแบบของสตริงที่มีส่วนต่างๆ ที่อาจตีความได้ว่าเป็นรายการ
// เมื่อโหลดแล้ว Aspose.Words จะตรวจพบสามรายการแรกเสมอ
// และรายการวัตถุจะถูกสร้างขึ้นสำหรับพวกเขาหลังจากโหลด
final String TEXT_DOC = "Full stop delimiters:\n" +
        "1. First list item 1\n" +
        "2. First list item 2\n" +
        "3. First list item 3\n\n" +
        "Right bracket delimiters:\n" +
        "1) Second list item 1\n" +
        "2) Second list item 2\n" +
        "3) Second list item 3\n\n" +
        "Bullet delimiters:\n" +
        "• Third list item 1\n" +
        "• Third list item 2\n" +
        "• Third list item 3\n\n" +
        "Whitespace delimiters:\n" +
        "1 Fourth list item 1\n" +
        "2 Fourth list item 2\n" +
        "3 Fourth list item 3";
//รายการที่สี่ โดยมีช่องว่างระหว่างหมายเลขรายการและเนื้อหารายการ
// จะถูกตรวจพบเป็นรายการหากตั้งค่า "DetectNumberingWithWhitespaces" ในวัตถุ LoadOptions เป็นจริงเท่านั้น
// เพื่อหลีกเลี่ยงย่อหน้าที่ขึ้นต้นด้วยตัวเลขที่ถูกตรวจพบว่าเป็นรายการโดยไม่ตั้งใจ
TxtLoadOptions loadOptions = new TxtLoadOptions();
{
    loadOptions.setDetectNumberingWithWhitespaces(true);
}
// โหลดเอกสารในขณะที่ใช้ LoadOptions เป็นพารามิเตอร์และตรวจสอบผลลัพธ์
Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 รหัสนี้สาธิตวิธีการโหลดเอกสารข้อความที่มีรูปแบบรายการต่างๆ และใช้`DetectNumberingWithWhitespaces` ตัวเลือกในการตรวจจับรายการอย่างถูกต้อง

## ขั้นตอนที่ 2: การจัดการตัวเลือกช่องว่าง

เพื่อควบคุมช่องว่างนำหน้าและต่อท้ายเมื่อโหลดเอกสารข้อความ คุณสามารถใช้โค้ดต่อไปนี้:

```java
@Test
public void handleSpacesOptions() throws Exception {
    final String TEXT_DOC = "      Line 1 \n" +
            "    Line 2   \n" +
            " Line 3       ";
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
        loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
    }
    Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
```

 ในตัวอย่างนี้ เราโหลดเอกสารข้อความและตัดช่องว่างนำหน้าและต่อท้ายโดยใช้`TxtLeadingSpacesOptions.TRIM` และ`TxtTrailingSpacesOptions.TRIM`.

## ขั้นตอนที่ 3: การควบคุมทิศทางของข้อความ

หากต้องการระบุทิศทางของข้อความเมื่อโหลดเอกสารข้อความ คุณสามารถใช้รหัสต่อไปนี้:

```java
@Test
public void documentTextDirection() throws Exception {
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setDocumentDirection(DocumentDirection.AUTO);
    }
    Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
    Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
    System.out.println(paragraph.getParagraphFormat().getBidi());
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
}
```

รหัสนี้กำหนดทิศทางของเอกสารเป็นการตรวจจับอัตโนมัติ (`DocumentDirection.AUTO`และโหลดเอกสารข้อความที่มีข้อความภาษาฮิบรู คุณสามารถปรับทิศทางของเอกสารได้ตามต้องการ

## กรอกซอร์สโค้ดสำหรับการโหลดไฟล์ข้อความด้วย Aspose.Words สำหรับ Java

```java
public void detectNumberingWithWhitespaces() throws Exception {
	// สร้างเอกสารข้อความธรรมดาในรูปแบบของสตริงที่มีส่วนต่างๆ ที่อาจตีความได้ว่าเป็นรายการ
	// เมื่อโหลดแล้ว Aspose.Words จะตรวจพบสามรายการแรกเสมอ
	// และรายการวัตถุจะถูกสร้างขึ้นสำหรับพวกเขาหลังจากโหลด
	final String TEXT_DOC = "Full stop delimiters:\n" +
			"1. First list item 1\n" +
			"2. First list item 2\n" +
			"3. First list item 3\n\n" +
			"Right bracket delimiters:\n" +
			"1) Second list item 1\n" +
			"2) Second list item 2\n" +
			"3) Second list item 3\n\n" +
			"Bullet delimiters:\n" +
			"• Third list item 1\n" +
			"• Third list item 2\n" +
			"• Third list item 3\n\n" +
			"Whitespace delimiters:\n" +
			"1 Fourth list item 1\n" +
			"2 Fourth list item 2\n" +
			"3 Fourth list item 3";
	// รายการที่สี่ โดยมีช่องว่างอยู่ระหว่างหมายเลขรายการและเนื้อหารายการ
	// จะถูกตรวจพบเป็นรายการหากตั้งค่า "DetectNumberingWithWhitespaces" ในวัตถุ LoadOptions เป็นจริงเท่านั้น
	// เพื่อหลีกเลี่ยงย่อหน้าที่ขึ้นต้นด้วยตัวเลขที่ถูกตรวจพบว่าเป็นรายการโดยไม่ตั้งใจ
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDetectNumberingWithWhitespaces(true);
	}
	// โหลดเอกสารในขณะที่ใช้ LoadOptions เป็นพารามิเตอร์และตรวจสอบผลลัพธ์
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
}
@Test
public void handleSpacesOptions() throws Exception {
	final String TEXT_DOC = "      Line 1 \n" +
			"    Line 2   \n" +
			" Line 3       ";
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
		loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
	}
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
@Test
public void documentTextDirection() throws Exception {
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDocumentDirection(DocumentDirection.AUTO);
	}
	Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
	Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
	System.out.println(paragraph.getParagraphFormat().getBidi());
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
	}
```

## บทสรุป

ในคู่มือนี้ เราได้สำรวจวิธีการโหลดไฟล์ข้อความโดยใช้ Aspose.Words สำหรับ Java ตรวจหารายการ จัดการช่องว่าง และควบคุมทิศทางของข้อความ เทคนิคเหล่านี้ช่วยให้คุณสามารถจัดการเอกสารข้อความในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ Java คืออะไร

Aspose.Words สำหรับ Java เป็นไลบรารีการประมวลผลเอกสารอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงเอกสาร Word โดยทางโปรแกรมในแอปพลิเคชัน Java มีคุณสมบัติมากมายสำหรับการทำงานกับข้อความ ตาราง รูปภาพ และองค์ประกอบเอกสารอื่นๆ

### ฉันจะเริ่มต้นใช้งาน Aspose.Words สำหรับ Java ได้อย่างไร

หากต้องการเริ่มต้นใช้งาน Aspose.Words สำหรับ Java ให้ทำตามขั้นตอนเหล่านี้:
1. ดาวน์โหลดและติดตั้งไลบรารี Aspose.Words สำหรับ Java
2.  อ้างอิงเอกสารประกอบได้ที่[Aspose.Words สำหรับการอ้างอิง Java API](https://reference.aspose.com/words/java/)สำหรับข้อมูลโดยละเอียดและตัวอย่าง
3. สำรวจโค้ดตัวอย่างและบทช่วยสอนเพื่อเรียนรู้วิธีใช้ไลบรารีอย่างมีประสิทธิภาพ

### ฉันจะโหลดเอกสารข้อความโดยใช้ Aspose.Words สำหรับ Java ได้อย่างไร

 หากต้องการโหลดเอกสารข้อความโดยใช้ Aspose.Words สำหรับ Java คุณสามารถใช้`TxtLoadOptions` ชั้นเรียนและ`Document` ระดับ. ตรวจสอบให้แน่ใจว่าคุณระบุตัวเลือกที่เหมาะสมสำหรับการจัดการช่องว่างและทิศทางของข้อความตามความจำเป็น ดูคำแนะนำทีละขั้นตอนในบทความนี้สำหรับตัวอย่างโดยละเอียด

### ฉันสามารถแปลงเอกสารข้อความที่โหลดไปเป็นรูปแบบอื่นได้หรือไม่

 ใช่ Aspose.Words สำหรับ Java ช่วยให้คุณสามารถแปลงเอกสารข้อความที่โหลดเป็นรูปแบบต่างๆ รวมถึง DOCX, PDF และอื่นๆ คุณสามารถใช้`Document` คลาสเพื่อทำการแปลง ตรวจสอบเอกสารสำหรับตัวอย่างการแปลงเฉพาะ

### ฉันจะจัดการช่องว่างในเอกสารข้อความที่โหลดได้อย่างไร

 คุณสามารถควบคุมวิธีจัดการช่องว่างนำหน้าและต่อท้ายในเอกสารข้อความที่โหลดได้โดยใช้`TxtLoadOptions` - ตัวเลือกเช่น`TxtLeadingSpacesOptions` และ`TxtTrailingSpacesOptions`ช่วยให้คุณสามารถตัดแต่งหรือรักษาช่องว่างได้ตามต้องการ โปรดดูตัวอย่างในส่วน "ตัวเลือกการจัดการพื้นที่" ในคู่มือนี้

### ทิศทางข้อความใน Aspose.Words สำหรับ Java มีความสำคัญอย่างไร

ทิศทางของข้อความเป็นสิ่งจำเป็นสำหรับเอกสารที่มีสคริปต์หรือภาษาผสม เช่น ฮีบรูหรืออารบิก Aspose.Words for Java มีตัวเลือกในการระบุทิศทางของข้อความ เพื่อให้มั่นใจว่ามีการเรนเดอร์และจัดรูปแบบข้อความในภาษาเหล่านี้อย่างเหมาะสม ส่วน "การควบคุมทิศทางของข้อความ" ในคู่มือนี้สาธิตวิธีกำหนดทิศทางของข้อความ

### ฉันจะค้นหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Words สำหรับ Java ได้ที่ไหน

 สำหรับแหล่งข้อมูลเพิ่มเติม เอกสาร และการสนับสนุน โปรดไปที่[Aspose.Words สำหรับเอกสาร Java](https://reference.aspose.com/words/java/)- คุณยังสามารถเข้าร่วมในฟอรัมชุมชน Aspose.Words หรือติดต่อฝ่ายสนับสนุนของ Aspose เพื่อขอความช่วยเหลือในประเด็นเฉพาะหรือสอบถามข้อมูล

### Aspose.Words สำหรับ Java เหมาะสำหรับโครงการเชิงพาณิชย์หรือไม่

ใช่ Aspose.Words สำหรับ Java เหมาะสำหรับทั้งโครงการส่วนบุคคลและเชิงพาณิชย์ มีตัวเลือกใบอนุญาตเพื่อรองรับสถานการณ์การใช้งานที่หลากหลาย ตรวจสอบให้แน่ใจว่าได้ตรวจสอบข้อกำหนดสิทธิ์การใช้งานและราคาบนเว็บไซต์ Aspose เพื่อเลือกสิทธิ์การใช้งานที่เหมาะสมสำหรับโครงการของคุณ