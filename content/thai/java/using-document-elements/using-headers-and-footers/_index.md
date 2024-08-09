---
title: การใช้ส่วนหัวและส่วนท้ายใน Aspose.Words สำหรับ Java
linktitle: การใช้ส่วนหัวและส่วนท้าย
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีใช้ส่วนหัวและส่วนท้ายใน Aspose.Words สำหรับ Java ทีละขั้นตอน สร้างเอกสารระดับมืออาชีพได้อย่างง่ายดาย
type: docs
weight: 16
url: /th/java/using-document-elements/using-headers-and-footers/
---

ในคู่มือที่ครอบคลุมนี้ เราจะแนะนำคุณตลอดกระบวนการทำงานกับส่วนหัวและส่วนท้ายใน Aspose.Words สำหรับ Java ส่วนหัวและส่วนท้ายเป็นองค์ประกอบสำคัญในการจัดรูปแบบเอกสาร และ Aspose.Words ก็มีเครื่องมืออันทรงพลังในการสร้างและปรับแต่งตามความต้องการของคุณ

ตอนนี้เรามาดูรายละเอียดแต่ละขั้นตอนเหล่านี้กัน

## 1. รู้เบื้องต้นเกี่ยวกับ Aspose.Words

Aspose.Words เป็น Java API อันทรงพลังที่ช่วยให้คุณสามารถสร้าง จัดการ และเรนเดอร์เอกสาร Word โดยทางโปรแกรมได้ มีคุณสมบัติมากมายสำหรับการจัดรูปแบบเอกสาร รวมถึงส่วนหัวและส่วนท้าย

## 2. การตั้งค่าสภาพแวดล้อม Java ของคุณ

 ก่อนที่คุณจะเริ่มใช้ Aspose.Words ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา Java ไว้อย่างถูกต้อง คุณสามารถดูคำแนะนำการตั้งค่าที่จำเป็นได้ที่หน้าเอกสารประกอบของ Aspose.Words:[เอกสาร Java Aspose.Words](https://reference.aspose.com/words/java/).

## 3. การสร้างเอกสารใหม่

หากต้องการทำงานกับส่วนหัวและส่วนท้าย คุณต้องสร้างเอกสารใหม่โดยใช้ Aspose.Words รหัสต่อไปนี้สาธิตวิธีการทำเช่นนี้:

```java
// รหัส Java สำหรับการสร้างเอกสารใหม่
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. ทำความเข้าใจกับการตั้งค่าหน้ากระดาษ

 การตั้งค่าหน้าถือเป็นสิ่งสำคัญในการควบคุมเค้าโครงเอกสารของคุณ คุณสามารถระบุคุณสมบัติต่างๆ ที่เกี่ยวข้องกับส่วนหัวและส่วนท้ายได้โดยใช้`PageSetup` ระดับ. ตัวอย่างเช่น:

```java
// การตั้งค่าคุณสมบัติของเพจ
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. ส่วนหัว/ส่วนท้ายของหน้าแรกที่แตกต่างกัน

Aspose.Words ช่วยให้คุณมีส่วนหัวและส่วนท้ายที่แตกต่างกันสำหรับหน้าแรกของเอกสารของคุณ ใช้`pageSetup.setDifferentFirstPageHeaderFooter(true);` เพื่อเปิดใช้งานคุณสมบัตินี้

## 6. การทำงานกับส่วนหัว

### 6.1. การเพิ่มข้อความลงในส่วนหัว

 คุณสามารถเพิ่มข้อความในส่วนหัวโดยใช้`DocumentBuilder`- นี่คือตัวอย่าง:

```java
// การเพิ่มข้อความในส่วนหัวของหน้าแรก
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. การแทรกรูปภาพลงในส่วนหัว

 หากต้องการแทรกรูปภาพลงในส่วนหัว คุณสามารถใช้`insertImage` วิธี. นี่คือตัวอย่าง:

```java
// การแทรกรูปภาพลงในส่วนหัว
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. การปรับแต่งสไตล์ส่วนหัว

คุณสามารถปรับแต่งสไตล์ส่วนหัวได้โดยการตั้งค่าคุณสมบัติต่างๆ เช่น แบบอักษร การจัดตำแหน่ง และอื่นๆ ดังที่แสดงในตัวอย่างด้านบน

## 7. การทำงานกับส่วนท้าย

### 7.1. การเพิ่มข้อความในส่วนท้าย

 เช่นเดียวกับส่วนหัว คุณสามารถเพิ่มข้อความในส่วนท้ายได้โดยใช้`DocumentBuilder`- นี่คือตัวอย่าง:

```java
// การเพิ่มข้อความในส่วนท้ายหลัก
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// แทรกข้อความและฟิลด์ตามต้องการ
```

### 7.2. การแทรกรูปภาพในส่วนท้าย

 หากต้องการแทรกรูปภาพในส่วนท้าย ให้ใช้`insertImage` วิธีการเช่นเดียวกับในส่วนหัว

### 7.3. การปรับแต่งสไตล์ส่วนท้าย

 ปรับแต่งสไตล์ส่วนท้ายโดยใช้`DocumentBuilder`คล้ายกับการปรับแต่งส่วนหัว

## 8. การกำหนดหมายเลขหน้า

 คุณสามารถใส่หมายเลขหน้าในส่วนหัวและส่วนท้ายของคุณโดยใช้ช่องต่างๆ เช่น`PAGE`และ`NUMPAGES`- ฟิลด์เหล่านี้จะอัปเดตโดยอัตโนมัติเมื่อคุณเพิ่มหรือลบเพจ

## 9. ข้อมูลลิขสิทธิ์ในส่วนท้าย

หากต้องการเพิ่มข้อมูลลิขสิทธิ์ลงในส่วนท้ายของเอกสาร คุณสามารถใช้ตารางที่มีเซลล์ 2 เซลล์ โดยวางเซลล์หนึ่งไว้ทางซ้ายและอีกเซลล์อยู่ทางขวา ดังที่แสดงในตัวอย่างโค้ด

## 10. การทำงานกับหลายส่วน

Aspose.Words ช่วยให้คุณสามารถทำงานกับหลายส่วนภายในเอกสารได้ คุณสามารถตั้งค่าหน้ากระดาษและส่วนหัว/ส่วนท้ายที่แตกต่างกันสำหรับแต่ละส่วนได้

## 11. การวางแนวภูมิทัศน์

คุณสามารถเปลี่ยนการวางแนวของส่วนใดส่วนหนึ่งเป็นโหมดแนวนอนได้หากจำเป็น

## 12. การคัดลอกส่วนหัว/ส่วนท้ายจากส่วนก่อนหน้า

การคัดลอกส่วนหัวและส่วนท้ายจากส่วนก่อนหน้าจะช่วยประหยัดเวลาในการสร้างเอกสารที่ซับซ้อน

## 13. บันทึกเอกสารของคุณ

หลังจากสร้างและปรับแต่งเอกสารของคุณแล้ว อย่าลืมบันทึกโดยใช้`doc.save()` วิธี.

## กรอกซอร์สโค้ดให้สมบูรณ์
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // ระบุว่าเราต้องการให้ส่วนหัว/ส่วนท้ายของหน้าแรกแตกต่างจากหน้าอื่นๆ หรือไม่
        // คุณยังสามารถใช้คุณสมบัติ PageSetup.OddAndEvenPagesHeaderFooter เพื่อระบุได้
        // ส่วนหัว/ส่วนท้ายที่แตกต่างกันสำหรับหน้าคี่และหน้าคู่
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // แทรกรูปภาพที่จัดตำแหน่งไว้ที่มุมบน/ซ้ายของส่วนหัว
        // ระยะห่างจากขอบบน/ซ้ายของหน้าตั้งค่าไว้ที่ 10 จุด
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // เราใช้ตารางที่มีสองเซลล์เพื่อสร้างส่วนหนึ่งของข้อความในบรรทัด (พร้อมหมายเลขหน้า)
        // ให้จัดชิดซ้าย และส่วนอื่น ๆ ของข้อความ (ที่มีลิขสิทธิ์) ให้จัดชิดขวา
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // ใช้ฟิลด์ PAGE และ NUMPAGES เพื่อคำนวณหมายเลขหน้าปัจจุบันและหลายหน้าโดยอัตโนมัติ
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // แบ่งหน้าเพื่อสร้างหน้าที่สองที่ส่วนหัว/ท้ายกระดาษหลักจะปรากฏ
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // ส่วนนี้ไม่ต้องการส่วนหัว/ส่วนท้ายของหน้าแรกที่แตกต่างกัน เราจำเป็นต้องมีหน้าชื่อเรื่องเพียงหน้าเดียวในเอกสาร
        //และส่วนหัว/ส่วนท้ายของหน้านี้ได้ถูกกำหนดไว้แล้วในส่วนก่อนหน้า
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // ส่วนนี้จะแสดงส่วนหัว/ส่วนท้ายจากส่วนก่อนหน้า
        // โดยค่าเริ่มต้น ให้เรียก currentSection.HeadersFooters.LinkToPrevious(false) เพื่อยกเลิกความกว้างของหน้านี้
        // จะแตกต่างกันสำหรับส่วนใหม่ ดังนั้นเราจึงจำเป็นต้องตั้งค่าความกว้างของเซลล์ที่แตกต่างกันสำหรับตารางส่วนท้าย
        currentSection.getHeadersFooters().linkToPrevious(false);
        // หากเราต้องการใช้ชุดส่วนหัว/ส่วนท้ายที่มีอยู่แล้วสำหรับส่วนนี้
        // แต่หากมีการแก้ไขเล็กน้อย ก็อาจสมควรคัดลอกส่วนหัว/ส่วนท้าย
        // จากส่วนก่อนหน้าและใช้การแก้ไขที่จำเป็นตามที่เราต้องการ
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
ซอร์สโค้ดของเมธอด copyHeadersFootersFromPreviousSection
```java
    /// <สรุป>
    /// โคลนและคัดลอกส่วนหัว/ส่วนท้ายจากส่วนก่อนหน้าไปยังส่วนที่ระบุ
    /// </สรุป>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงพื้นฐานของการทำงานกับส่วนหัวและส่วนท้ายใน Aspose.Words สำหรับ Java คุณได้เรียนรู้วิธีสร้าง ปรับแต่ง และจัดรูปแบบส่วนหัวและส่วนท้าย รวมถึงเทคนิคการจัดรูปแบบเอกสารที่จำเป็นอื่นๆ

 สำหรับรายละเอียดเพิ่มเติมและคุณสมบัติขั้นสูง โปรดดูที่[เอกสาร Java Aspose.Words](https://reference.aspose.com/words/java/).

## คำถามที่พบบ่อย

### 1. ฉันจะเพิ่มหมายเลขหน้าในส่วนท้ายของเอกสารได้อย่างไร
 คุณสามารถเพิ่มหมายเลขหน้าได้โดยการใส่`PAGE` ฟิลด์ลงในส่วนท้ายโดยใช้ Aspose.Words

### 2. Aspose.Words เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java หรือไม่
ใช่ Aspose.Words ให้การสนับสนุนการพัฒนา Java ตรวจสอบให้แน่ใจว่าคุณมีการตั้งค่าที่จำเป็น

### 3. ฉันสามารถปรับแต่งแบบอักษรและรูปแบบของส่วนหัวและส่วนท้ายได้หรือไม่?
แน่นอน คุณสามารถปรับแต่งแบบอักษร การจัดตำแหน่ง และสไตล์อื่นๆ เพื่อทำให้ส่วนหัวและส่วนท้ายของคุณดูน่าดึงดูด

### 4. เป็นไปได้ไหมที่จะมีส่วนหัวที่แตกต่างกันสำหรับหน้าคี่และหน้าคู่?
 ใช่คุณสามารถใช้`PageSetup.OddAndEvenPagesHeaderFooter` เพื่อระบุส่วนหัวที่แตกต่างกันสำหรับหน้าคี่และหน้าคู่

### 5. ฉันจะเริ่มต้นใช้งาน Aspose.Words สำหรับ Java ได้อย่างไร
 ในการเริ่มต้น เยี่ยมชม[เอกสาร Java Aspose.Words](https://reference.aspose.com/words/java/) สำหรับคำแนะนำที่ครอบคลุมเกี่ยวกับการใช้ API