---
title: การใช้รายการใน Aspose.Words สำหรับ Java
linktitle: การใช้รายการ
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้การใช้รายการใน Aspose.Words สำหรับ Java ด้วยบทช่วยสอนทีละขั้นตอนนี้ จัดระเบียบและจัดรูปแบบเอกสารของคุณอย่างมีประสิทธิภาพ
type: docs
weight: 18
url: /th/java/using-document-elements/using-lists/
---

ในบทช่วยสอนที่ครอบคลุมนี้ เราจะสำรวจวิธีใช้รายการใน Aspose.Words สำหรับ Java อย่างมีประสิทธิภาพ ซึ่งเป็น API อันทรงพลังสำหรับการทำงานกับเอกสาร Microsoft Word โดยทางโปรแกรม รายการจำเป็นสำหรับการจัดโครงสร้างและการจัดระเบียบเนื้อหาในเอกสารของคุณ เราจะกล่าวถึงประเด็นสำคัญสองประการในการทำงานกับรายการ ได้แก่ การรีสตาร์ทรายการในแต่ละส่วน และการระบุระดับรายการ มาดำน้ำกันเถอะ!

## รู้เบื้องต้นเกี่ยวกับ Aspose.Words สำหรับ Java

ก่อนที่เราจะเริ่มทำงานกับรายการ เรามาทำความรู้จักกับ Aspose.Words สำหรับ Java กันดีกว่า API นี้มอบเครื่องมือสำหรับนักพัฒนาในการสร้าง แก้ไข และจัดการเอกสาร Word ในสภาพแวดล้อม Java เป็นโซลูชันอเนกประสงค์สำหรับงานต่างๆ ตั้งแต่การสร้างเอกสารอย่างง่ายไปจนถึงการจัดรูปแบบที่ซับซ้อนและการจัดการเนื้อหา

### การตั้งค่าสภาพแวดล้อมของคุณ

 ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Words สำหรับ Java และตั้งค่าในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/words/java/). 

## การเริ่มรายการใหม่ในแต่ละส่วน

ในหลายสถานการณ์ คุณอาจต้องเริ่มรายการใหม่ในแต่ละส่วนของเอกสาร สิ่งนี้มีประโยชน์สำหรับการสร้างเอกสารที่มีโครงสร้างซึ่งมีหลายส่วน เช่น รายงาน คู่มือ หรือเอกสารทางวิชาการ

คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการบรรลุเป้าหมายนี้โดยใช้ Aspose.Words สำหรับ Java:

### เริ่มต้นเอกสารของคุณ: 
เริ่มต้นด้วยการสร้างวัตถุเอกสารใหม่

```java
Document doc = new Document();
```

### เพิ่มรายการลำดับเลข: 
เพิ่มรายการลำดับเลขลงในเอกสารของคุณ เราจะใช้รูปแบบการกำหนดหมายเลขเริ่มต้น

```java
doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
```

### กำหนดการตั้งค่ารายการ: 
\เปิดใช้งานรายการเพื่อรีสตาร์ทในแต่ละส่วน

```java
List list = doc.getLists().get(0);
list.isRestartAtEachSection(true);
```

### การตั้งค่า DocumentBuilder: 
สร้าง DocumentBuilder เพื่อเพิ่มเนื้อหาลงในเอกสารของคุณ

```java
DocumentBuilder builder = new DocumentBuilder(doc);
builder.getListFormat().setList(list);
```

### เพิ่มรายการ: 
ใช้การวนซ้ำเพื่อเพิ่มรายการลงในเอกสารของคุณ เราจะแทรกตัวแบ่งส่วนหลังรายการที่ 15

```java
for (int i = 1; i < 45; i++) {
    builder.writeln(MessageFormat.format("List Item {0}", i));
    if (i == 15)
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
}
```

### บันทึกเอกสารของคุณ: 
บันทึกเอกสารด้วยตัวเลือกที่ต้องการ

```java
OoxmlSaveOptions options = new OoxmlSaveOptions();
options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
doc.save(outPath + "RestartListAtEachSection.docx", options);
```

เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถสร้างเอกสารที่มีรายการที่เริ่มต้นใหม่ในแต่ละส่วน โดยรักษาโครงสร้างเนื้อหาที่ชัดเจนและเป็นระเบียบ

## การระบุระดับรายการ

Aspose.Words สำหรับ Java ช่วยให้คุณสามารถระบุระดับรายการ ซึ่งมีประโยชน์อย่างยิ่งเมื่อคุณต้องการรูปแบบรายการที่แตกต่างกันภายในเอกสารของคุณ เรามาสำรวจวิธีการทำสิ่งนี้กัน:

### เริ่มต้นเอกสารของคุณ: 
สร้างวัตถุเอกสารใหม่

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### สร้างรายการลำดับเลข: 
ใช้เทมเพลตรายการลำดับเลขจาก Microsoft Word

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
```

### ระบุระดับรายการ: 
ทำซ้ำตามระดับรายการต่างๆ และเพิ่มเนื้อหา

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### สร้างรายการสัญลักษณ์แสดงหัวข้อย่อย: 
ตอนนี้เรามาสร้างรายการสัญลักษณ์แสดงหัวข้อย่อย

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
```

### ระบุระดับรายการสัญลักษณ์แสดงหัวข้อย่อย: 
คล้ายกับรายการลำดับเลข ระบุระดับ และเพิ่มเนื้อหา

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### การจัดรูปแบบรายการหยุด: 
หากต้องการหยุดการจัดรูปแบบรายการ ให้ตั้งค่ารายการเป็นค่าว่าง

```java
builder.getListFormat().setList(null);
```

### บันทึกเอกสารของคุณ: 
บันทึกเอกสาร

```java
builder.getDocument().save(outPath + "SpecifyListLevel.docx");
```

เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถสร้างเอกสารที่มีระดับรายการแบบกำหนดเองได้ ซึ่งช่วยให้คุณควบคุมการจัดรูปแบบของรายการในเอกสารของคุณได้

## กรอกซอร์สโค้ดให้สมบูรณ์
```java
	string outPath = "Your Output Directory";
 public void restartListAtEachSection() throws Exception
    {
        Document doc = new Document();
        doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
        List list = doc.getLists().get(0);
        list.isRestartAtEachSection(true);
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getListFormat().setList(list);
        for (int i = 1; i < 45; i++)
        {
            builder.writeln(MessageFormat.format("List Item {0}", i));
            if (i == 15)
                builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        }
        // IsRestartAtEachSection จะถูกเขียนเฉพาะในกรณีที่การปฏิบัติตามข้อกำหนดสูงกว่า OoxmlComplianceCore.Ecma376
        OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL); }
        doc.save(outPath + "WorkingWithList.RestartListAtEachSection.docx", options);
    }
    @Test
    public void specifyListLevel() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // สร้างรายการลำดับเลขโดยยึดตามเทมเพลตรายการ Microsoft Word รายการใดรายการหนึ่ง
        //และนำไปใช้กับย่อหน้าปัจจุบันของตัวสร้างเอกสาร
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
        // มีเก้าระดับในรายการนี้ มาลองกันทั้งหมดเลย
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // สร้างรายการสัญลักษณ์แสดงหัวข้อย่อยโดยยึดตามเทมเพลตรายการ Microsoft Word รายการใดรายการหนึ่ง
        //และนำไปใช้กับย่อหน้าปัจจุบันของตัวสร้างเอกสาร
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // นี่เป็นวิธีหยุดการจัดรูปแบบรายการ
        builder.getListFormat().setList(null);
        builder.getDocument().save(outPath + "WorkingWithList.SpecifyListLevel.docx");
    }
    @Test
    public void restartListNumber() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // สร้างรายการตามเทมเพลต
        List list1 = doc.getLists().add(ListTemplate.NUMBER_ARABIC_PARENTHESIS);
        list1.getListLevels().get(0).getFont().setColor(Color.RED);
        list1.getListLevels().get(0).setAlignment(ListLevelAlignment.RIGHT);
        builder.writeln("List 1 starts below:");
        builder.getListFormat().setList(list1);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        // หากต้องการนำรายการแรกมาใช้ซ้ำ เราจำเป็นต้องเริ่มการกำหนดหมายเลขใหม่โดยสร้างสำเนาของการจัดรูปแบบรายการดั้งเดิม
        List list2 = doc.getLists().addCopy(list1);
        // เราสามารถแก้ไขรายการใหม่ได้ทุกทางรวมถึงการตั้งหมายเลขเริ่มต้นใหม่
        list2.getListLevels().get(0).setStartAt(10);
        builder.writeln("List 2 starts below:");
        builder.getListFormat().setList(list2);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        builder.getDocument().save(outPath + "WorkingWithList.RestartListNumber.docx");
	}
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีทำงานกับรายการใน Aspose.Words สำหรับ Java อย่างมีประสิทธิภาพแล้ว รายการมีความสำคัญอย่างยิ่งต่อการจัดระเบียบและการนำเสนอเนื้อหาในเอกสารของคุณ ไม่ว่าคุณจะต้องรีสตาร์ทรายการในแต่ละส่วนหรือระบุระดับรายการ Aspose.Words สำหรับ Java มีเครื่องมือที่คุณต้องการในการสร้างเอกสารที่ดูเป็นมืออาชีพ

ตอนนี้คุณสามารถใช้คุณสมบัติเหล่านี้ได้อย่างมั่นใจเพื่อปรับปรุงงานการสร้างและการจัดรูปแบบเอกสารของคุณ หากคุณมีคำถามหรือต้องการความช่วยเหลือเพิ่มเติม โปรดติดต่อไปที่[กำหนดฟอรั่มชุมชน](https://forum.aspose.com/) สำหรับการสนับสนุน

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Words สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Words สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/words/java/) และปฏิบัติตามคำแนะนำในการติดตั้งในเอกสารประกอบ

### ฉันสามารถปรับแต่งรูปแบบการเรียงลำดับเลขของรายการได้หรือไม่
ใช่ Aspose.Words สำหรับ Java มีตัวเลือกมากมายสำหรับการปรับแต่งรูปแบบการกำหนดหมายเลขรายการ คุณสามารถดูเอกสารประกอบ API เพื่อดูรายละเอียดได้

### Aspose.Words สำหรับ Java เข้ากันได้กับมาตรฐานเอกสาร Word ล่าสุดหรือไม่
ได้ คุณสามารถกำหนดค่า Aspose.Words สำหรับ Java ให้สอดคล้องกับมาตรฐานเอกสาร Word ต่างๆ ได้ รวมถึง ISO 29500

### ฉันสามารถสร้างเอกสารที่ซับซ้อนด้วยตารางและรูปภาพโดยใช้ Aspose.Words สำหรับ Java ได้หรือไม่
อย่างแน่นอน! Aspose.Words สำหรับ Java รองรับการจัดรูปแบบเอกสารขั้นสูง รวมถึงตาราง รูปภาพ และอื่นๆ ตรวจสอบเอกสารประกอบเพื่อดูตัวอย่าง

### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Words สำหรับ Java ได้ที่ไหน
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
