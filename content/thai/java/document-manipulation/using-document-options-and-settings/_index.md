---
title: การใช้ตัวเลือกเอกสารและการตั้งค่าใน Aspose.Words สำหรับ Java
linktitle: การใช้ตัวเลือกเอกสารและการตั้งค่า
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: ปลดล็อกพลังของ Aspose.Words สำหรับ Java ตัวเลือกเอกสารหลักและการตั้งค่าสำหรับการจัดการเอกสารที่ราบรื่น เพิ่มประสิทธิภาพ ปรับแต่ง และอื่นๆ อีกมากมาย
type: docs
weight: 31
url: /th/java/document-manipulation/using-document-options-and-settings/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการใช้ตัวเลือกเอกสารและการตั้งค่าใน Aspose.Words สำหรับ Java

ในคู่มือที่ครอบคลุมนี้ เราจะสำรวจวิธีใช้ประโยชน์จากฟีเจอร์อันทรงพลังของ Aspose.Words สำหรับ Java เพื่อทำงานกับตัวเลือกและการตั้งค่าเอกสาร ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คุณจะพบข้อมูลเชิงลึกอันมีค่าและตัวอย่างที่เป็นประโยชน์เพื่อปรับปรุงงานการประมวลผลเอกสารของคุณ

## การเพิ่มประสิทธิภาพเอกสารเพื่อความเข้ากันได้

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.OptimizeForMsWord.docx");
```

สิ่งสำคัญประการหนึ่งของการจัดการเอกสารคือการรับรองความเข้ากันได้กับ Microsoft Word เวอร์ชันต่างๆ Aspose.Words สำหรับ Java มอบวิธีที่ตรงไปตรงมาในการปรับเอกสารให้เหมาะสมสำหรับ Word เวอร์ชันเฉพาะ ในตัวอย่างข้างต้น เราปรับเอกสารให้เหมาะสมสำหรับ Word 2016 เพื่อให้มั่นใจถึงความเข้ากันได้ที่ราบรื่น

## การระบุข้อผิดพลาดทางไวยากรณ์และการสะกดคำ

```java
@Test
public void showGrammaticalAndSpellingErrors() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Document.docx");
    doc.setShowGrammaticalErrors(true);
    doc.setShowSpellingErrors(true);
    doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
}
```

ความแม่นยำเป็นสิ่งสำคัญยิ่งเมื่อต้องจัดการกับเอกสาร Aspose.Words สำหรับ Java ช่วยให้คุณสามารถเน้นข้อผิดพลาดทางไวยากรณ์และการสะกดคำภายในเอกสารของคุณ ทำให้การพิสูจน์อักษรและการแก้ไขมีประสิทธิภาพมากขึ้น

## ทำความสะอาดสไตล์และรายการที่ไม่ได้ใช้

```java
@Test
public void cleanupUnusedStylesAndLists() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Unused styles.docx");
    // กำหนดตัวเลือกการล้างข้อมูล
    CleanupOptions cleanupOptions = new CleanupOptions();
    cleanupOptions.setUnusedLists(false);
    cleanupOptions.setUnusedStyles(true);
    doc.cleanup(cleanupOptions);
    doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
}
```

การจัดการรูปแบบและรายการเอกสารอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญสำหรับการรักษาความสอดคล้องของเอกสาร Aspose.Words สำหรับ Java ช่วยให้คุณสามารถล้างสไตล์และรายการที่ไม่ได้ใช้ เพื่อให้มั่นใจว่าโครงสร้างเอกสารมีความคล่องตัวและเป็นระเบียบ

## การลบสไตล์ที่ซ้ำกัน

```java
@Test
public void cleanupDuplicateStyle() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Document.docx");
    // ทำความสะอาดรูปแบบที่ซ้ำกัน
    CleanupOptions options = new CleanupOptions();
    options.setDuplicateStyle(true);
    doc.cleanup(options);
    doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
}
```

รูปแบบที่ซ้ำกันอาจทำให้เกิดความสับสนและไม่สอดคล้องกันในเอกสารของคุณ ด้วย Aspose.Words สำหรับ Java คุณสามารถลบสไตล์ที่ซ้ำกันได้อย่างง่ายดาย โดยรักษาความชัดเจนและความสอดคล้องของเอกสาร

## การปรับแต่งตัวเลือกการดูเอกสาร

```java
@Test
public void viewOptions() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Document.docx");
    // ปรับแต่งตัวเลือกการรับชม
    doc.getViewOptions().setViewType(ViewType.PAGE_LAYOUT);
    doc.getViewOptions().setZoomPercent(50);
    doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
}
```

การปรับแต่งประสบการณ์การดูเอกสารของคุณเป็นสิ่งสำคัญ Aspose.Words สำหรับ Java ช่วยให้คุณสามารถตั้งค่าตัวเลือกการดูต่างๆ เช่น เค้าโครงหน้าและเปอร์เซ็นต์การซูม เพื่อปรับปรุงความสามารถในการอ่านเอกสาร

## การกำหนดค่าการตั้งค่าหน้าเอกสาร

```java
@Test
public void documentPageSetup() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Document.docx");
    // กำหนดค่าตัวเลือกการตั้งค่าเพจ
    doc.getFirstSection().getPageSetup().setLayoutMode(SectionLayoutMode.GRID);
    doc.getFirstSection().getPageSetup().setCharactersPerLine(30);
    doc.getFirstSection().getPageSetup().setLinesPerPage(10);
    doc.save("Your Directory Path" + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
}
```

การตั้งค่าหน้าที่แม่นยำเป็นสิ่งสำคัญสำหรับการจัดรูปแบบเอกสาร Aspose.Words สำหรับ Java ช่วยให้คุณสามารถตั้งค่าโหมดเค้าโครง อักขระต่อบรรทัด และบรรทัดต่อหน้า เพื่อให้มั่นใจว่าเอกสารของคุณมีความน่าสนใจทางสายตา

## การตั้งค่าภาษาการแก้ไข

```java
@Test
public void addJapaneseAsEditingLanguages() throws Exception
{
    LoadOptions loadOptions = new LoadOptions();
    // ตั้งค่ากำหนดภาษาสำหรับการแก้ไข
    loadOptions.getLanguagePreferences().addEditingLanguage(EditingLanguage.JAPANESE);
    Document doc = new Document("Your Directory Path" + "No default editing language.docx", loadOptions);
    // ตรวจสอบภาษาการแก้ไขที่ถูกแทนที่
    int localeIdFarEast = doc.getStyles().getDefaultFont().getLocaleIdFarEast();
    System.out.println(localeIdFarEast == (int) EditingLanguage.JAPANESE
            ? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
            : "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
}
```

การแก้ไขภาษามีบทบาทสำคัญในการประมวลผลเอกสาร ด้วย Aspose.Words สำหรับ Java คุณสามารถตั้งค่าและปรับแต่งภาษาสำหรับการแก้ไขเพื่อให้เหมาะกับความต้องการทางภาษาของเอกสารของคุณ


## บทสรุป

ในคู่มือนี้ เราได้เจาะลึกตัวเลือกเอกสารและการตั้งค่าต่างๆ ที่มีอยู่ใน Aspose.Words สำหรับ Java ตั้งแต่การเพิ่มประสิทธิภาพและการแสดงข้อผิดพลาดไปจนถึงตัวเลือกการล้างข้อมูลและการดูรูปแบบ ไลบรารีอันทรงพลังนี้มีความสามารถที่ครอบคลุมในการจัดการและปรับแต่งเอกสารของคุณ

## คำถามที่พบบ่อย

### ฉันจะปรับเอกสารให้เหมาะสมสำหรับ Word เวอร์ชันใดเวอร์ชันหนึ่งได้อย่างไร

 หากต้องการปรับเอกสารให้เหมาะสมสำหรับ Word เวอร์ชันใดเวอร์ชันหนึ่ง ให้ใช้`optimizeFor` วิธีการและระบุเวอร์ชันที่ต้องการ ตัวอย่างเช่น หากต้องการปรับให้เหมาะสมสำหรับ Word 2016:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
doc.save("Your Directory Path" + "OptimizedForWord2016.docx");
```

### ฉันจะเน้นข้อผิดพลาดทางไวยากรณ์และการสะกดคำในเอกสารได้อย่างไร

คุณสามารถเปิดใช้งานการแสดงข้อผิดพลาดทางไวยากรณ์และการสะกดคำในเอกสารโดยใช้รหัสต่อไปนี้:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
doc.setShowGrammaticalErrors(true);
doc.setShowSpellingErrors(true);
doc.save("Your Directory Path" + "ShowErrors.docx");
```

### จุดประสงค์ของการล้างสไตล์และรายการที่ไม่ได้ใช้คืออะไร?

การล้างสไตล์และรายการที่ไม่ได้ใช้จะช่วยรักษาโครงสร้างเอกสารที่สะอาดและเป็นระเบียบ ช่วยขจัดความยุ่งเหยิงที่ไม่จำเป็น ปรับปรุงความสามารถในการอ่านเอกสารและความสม่ำเสมอ

### ฉันจะลบสไตล์ที่ซ้ำกันออกจากเอกสารได้อย่างไร

หากต้องการลบสไตล์ที่ซ้ำกันออกจากเอกสาร ให้ใช้`cleanup` วิธีการด้วย`duplicateStyle` ตัวเลือกที่ตั้งไว้เป็น`true`- นี่คือตัวอย่าง:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
CleanupOptions options = new CleanupOptions();
options.setDuplicateStyle(true);
doc.cleanup(options);
doc.save("Your Directory Path" + "CleanedDocument.docx");
```

### ฉันจะปรับแต่งตัวเลือกการดูเอกสารได้อย่างไร

 คุณสามารถปรับแต่งตัวเลือกการดูเอกสารได้โดยใช้`ViewOptions` ชั้นเรียน ตัวอย่างเช่น หากต้องการตั้งค่าประเภทมุมมองเป็นเค้าโครงหน้าและซูมเป็น 50%:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
doc.getViewOptions().setViewType(ViewType.PAGE_LAYOUT);
doc.getViewOptions().setZoomPercent(50);
doc.save("Your Directory Path" + "CustomView.docx");
```