---
title: ตัวเลือกการบันทึกเอกสาร HTML ขั้นสูงด้วย Aspose.Words Java
linktitle: การบันทึกเอกสาร HTML ด้วย
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: ในบทช่วยสอนนี้ เราได้กล่าวถึงตัวเลือกการบันทึกเอกสาร HTML ขั้นสูงต่างๆ ด้วย Aspose.Words สำหรับ Java ตัวเลือกเหล่านี้ช่วยให้คุณสร้าง HTML คุณภาพสูงได้
type: docs
weight: 16
url: /th/java/document-loading-and-saving/advance-html-documents-saving-options/
---

ในบทช่วยสอนนี้ เราจะสำรวจตัวเลือกการบันทึกเอกสาร HTML ขั้นสูงที่ Aspose.Words สำหรับ Java มอบให้ Aspose.Words เป็น Java API ที่ทรงพลังสำหรับการทำงานกับเอกสาร Word และมีคุณสมบัติที่หลากหลายสำหรับการจัดการและการแปลงเอกสาร

## 1. บทนำ
Aspose.Words สำหรับ Java ช่วยให้คุณสามารถทำงานกับเอกสาร Word โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะเน้นที่ตัวเลือกการบันทึกเอกสาร HTML ขั้นสูง ซึ่งช่วยให้คุณควบคุมวิธีการแปลงเอกสาร Word เป็น HTML ได้

## 2. ส่งออกข้อมูลไปกลับ
 ที่`exportRoundtripInformation` วิธีการช่วยให้คุณสามารถส่งออกเอกสาร Word เป็น HTML ในขณะที่รักษาข้อมูลไปกลับ ข้อมูลนี้จะมีประโยชน์เมื่อคุณต้องการแปลง HTML กลับเป็นรูปแบบ Word โดยไม่สูญเสียรายละเอียดเฉพาะเอกสารใดๆ

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. ส่งออกแบบอักษรเป็น Base64
 กับ`exportFontsAsBase64` คุณสามารถส่งออกแบบอักษรที่ใช้ในเอกสารเป็นข้อมูลที่เข้ารหัส Base64 ใน HTML ได้ เพื่อให้แน่ใจว่าการแสดง HTML ยังคงรูปแบบตัวอักษรเหมือนกับเอกสาร Word ต้นฉบับ

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. ทรัพยากรการส่งออก
 ที่`exportResources` วิธีการช่วยให้คุณสามารถระบุประเภทของสไตล์ชีต CSS และส่งออกทรัพยากรแบบอักษร คุณยังสามารถตั้งค่าโฟลเดอร์ทรัพยากรและนามแฝงสำหรับทรัพยากรใน HTML ได้อีกด้วย

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. แปลง Metafiles เป็น EMF หรือ WMF
 ที่`convertMetafilesToEmfOrWmf`วิธีการช่วยให้คุณสามารถแปลง metafiles ในเอกสารเป็นรูปแบบ EMF หรือ WMF เพื่อให้มั่นใจถึงความเข้ากันได้และการเรนเดอร์ที่ราบรื่นใน HTML

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // ข้อมูลโค้ดไม่แสดงเพื่อความกระชับ
}
```

## 6. แปลง Metafiles เป็น SVG
 ใช้`convertMetafilesToSvg` วิธีการแปลง metafiles เป็นรูปแบบ SVG รูปแบบนี้เหมาะสำหรับการแสดงกราฟิกแบบเวกเตอร์ในเอกสาร HTML

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // ข้อมูลโค้ดไม่แสดงเพื่อความกระชับ
}
```

## 7. เพิ่มคำนำหน้าชื่อคลาส CSS
 กับ`addCssClassNamePrefix` วิธีการคุณสามารถเพิ่มคำนำหน้าให้กับชื่อคลาส CSS ใน HTML ที่ส่งออกได้ ซึ่งจะช่วยป้องกันความขัดแย้งกับสไตล์ที่มีอยู่

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. ส่งออก CID URL สำหรับทรัพยากร MHTML
 ที่`exportCidUrlsForMhtmlResources` วิธีการนี้ใช้ในการบันทึกเอกสารในรูปแบบ MHTML อนุญาตให้ส่งออก URL ของ Content-ID สำหรับทรัพยากร

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // ข้อมูลโค้ดไม่แสดงเพื่อความกระชับ
}
```

## 9. แก้ไขชื่อแบบอักษร
 ที่`resolveFontNames` วิธีการนี้ช่วยแก้ไขชื่อแบบอักษรเมื่อบันทึกเอกสารในรูปแบบ HTML ช่วยให้มั่นใจได้ถึงการแสดงผลที่สอดคล้องกันบนแพลตฟอร์มต่างๆ

```java
@Test
public void resolveFontNames() throws Exception {
    // ข้อมูลโค้ดไม่แสดงเพื่อความกระชับ
}
```

## 10. ส่งออกฟิลด์แบบฟอร์มป้อนข้อความเป็นข้อความ
 ที่`exportTextInputFormFieldAsText` วิธีการส่งออกฟิลด์แบบฟอร์มเป็นข้อความธรรมดาใน HTML ทำให้สามารถอ่านและแก้ไขได้ง่าย

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // ข้อมูลโค้ดไม่แสดงเพื่อความกระชับ
}
```

## 11. บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจตัวเลือกการบันทึกเอกสาร HTML ขั้นสูงที่ Aspose.Words สำหรับ Java มอบให้ ตัวเลือกเหล่านี้ช่วยให้คุณควบคุมกระบวนการแปลงได้อย่างละเอียด ทำให้คุณสามารถสร้างเอกสาร HTML ที่มีลักษณะใกล้เคียงกับเอกสาร Word ต้นฉบับได้

## 12. คำถามที่พบบ่อย
ต่อไปนี้เป็นคำถามที่พบบ่อยเกี่ยวกับการทำงานกับ Aspose.Words สำหรับตัวเลือกการบันทึกเอกสาร Java และ HTML:

### คำถามที่ 1: ฉันจะแปลง HTML กลับเป็นรูปแบบ Word โดยใช้ Aspose.Words สำหรับ Java ได้อย่างไร
 หากต้องการแปลง HTML กลับเป็นรูปแบบ Word คุณสามารถใช้ Aspose.Words API ได้`load` วิธีโหลดเอกสาร HTML แล้วบันทึกเป็นไฟล์ Word

### คำถามที่ 2: ฉันสามารถปรับแต่งสไตล์ CSS เมื่อส่งออกเป็น HTML ได้หรือไม่
 ใช่ คุณสามารถปรับแต่งสไตล์ CSS ได้โดยการแก้ไขสไตล์ชีตที่ใช้ใน HTML หรือโดยใช้`addCssClassNamePrefix` วิธีการเพิ่มคำนำหน้าให้กับชื่อคลาส CSS

### คำถามที่ 3: มีวิธีเพิ่มประสิทธิภาพเอาต์พุต HTML สำหรับการแสดงผลบนเว็บหรือไม่
ใช่ คุณสามารถปรับเอาต์พุต HTML ให้เหมาะสมสำหรับการแสดงผลบนเว็บได้โดยการกำหนดค่าตัวเลือก เช่น การส่งออกแบบอักษรเป็น Base64 และการแปลงไฟล์เมตาเป็น SVG

### คำถามที่ 4: มีข้อจำกัดในการแปลงเอกสาร Word ที่ซับซ้อนเป็น HTML หรือไม่
แม้ว่า Aspose.Words สำหรับ Java จะให้ความสามารถในการแปลงที่มีประสิทธิภาพ แต่เอกสาร Word ที่ซับซ้อนซึ่งมีเค้าโครงที่ซับซ้อนอาจจำเป็นต้องมีการประมวลผลเพิ่มเติมในภายหลังเพื่อให้ได้เอาต์พุต HTML ที่ต้องการ
