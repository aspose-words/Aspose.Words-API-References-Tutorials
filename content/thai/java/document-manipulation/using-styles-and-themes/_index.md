---
title: การใช้สไตล์และธีมใน Aspose.Words สำหรับ Java
linktitle: การใช้สไตล์และธีม
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีปรับปรุงการจัดรูปแบบเอกสารด้วย Aspose.Words สำหรับ Java สำรวจสไตล์ ธีม และอื่นๆ ในคู่มือที่ครอบคลุมนี้พร้อมตัวอย่างซอร์สโค้ด
type: docs
weight: 20
url: /th/java/document-manipulation/using-styles-and-themes/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการใช้สไตล์และธีมใน Aspose.Words สำหรับ Java

ในคู่มือนี้ เราจะสำรวจวิธีการทำงานกับสไตล์และธีมใน Aspose.Words สำหรับ Java เพื่อปรับปรุงการจัดรูปแบบและรูปลักษณ์ของเอกสารของคุณ เราจะครอบคลุมหัวข้อต่างๆ เช่น การดึงข้อมูลสไตล์ การคัดลอกสไตล์ การจัดการธีม และการแทรกตัวคั่นสไตล์ มาเริ่มกันเลย!

## กำลังดึงสไตล์

หากต้องการดึงสไตล์จากเอกสาร คุณสามารถใช้ข้อมูลโค้ด Java ต่อไปนี้:

```java
Document doc = new Document();
String styleName = "";
//รับคอลเลกชันสไตล์จากเอกสาร
StyleCollection styles = doc.getStyles();
for (Style style : styles)
{
    if ("".equals(styleName))
    {
        styleName = style.getName();
        System.out.println(styleName);
    }
    else
    {
        styleName = styleName + ", " + style.getName();
        System.out.println(styleName);
    }
}
```

รหัสนี้จะดึงสไตล์ที่กำหนดไว้ในเอกสารและพิมพ์ชื่อ

## การคัดลอกสไตล์

 หากต้องการคัดลอกสไตล์จากเอกสารหนึ่งไปยังอีกเอกสารหนึ่ง คุณสามารถใช้`copyStylesFromTemplate` วิธีการดังแสดงด้านล่าง:

```java
@Test
public void copyStyles() throws Exception
{
    Document doc = new Document();
    Document target = new Document("Your Directory Path" + "Rendering.docx");
    target.copyStylesFromTemplate(doc);
    doc.save("Your Directory Path" + "WorkingWithStylesAndThemes.CopyStyles.docx");
}
```

โค้ดนี้จะคัดลอกสไตล์จากเอกสารเทมเพลตไปยังเอกสารปัจจุบัน

## การจัดการธีม

ธีมมีความสำคัญต่อการกำหนดรูปลักษณ์โดยรวมของเอกสารของคุณ คุณสามารถดึงข้อมูลและตั้งค่าคุณสมบัติของธีมได้ตามที่แสดงในโค้ดต่อไปนี้:

```java
@Test
public void getThemeProperties() throws Exception
{
    Document doc = new Document();
    Theme theme = doc.getTheme();
    System.out.println(theme.getMajorFonts().getLatin());
    System.out.println(theme.getMinorFonts().getEastAsian());
    System.out.println(theme.getColors().getAccent1());
}

@Test
public void setThemeProperties() throws Exception
{
    Document doc = new Document();
    Theme theme = doc.getTheme();
    theme.getMinorFonts().setLatin("Times New Roman");
    theme.getColors().setHyperlink(Color.ORANGE);
}
```

ตัวอย่างเหล่านี้สาธิตวิธีการดึงข้อมูลและแก้ไขคุณสมบัติของธีม เช่น แบบอักษรและสี

## การแทรกตัวคั่นสไตล์

ตัวคั่นลักษณะมีประโยชน์สำหรับการนำสไตล์ต่างๆ ไปใช้ภายในย่อหน้าเดียว ต่อไปนี้เป็นตัวอย่างวิธีการแทรกตัวคั่นลักษณะ:

```java
@Test
public void insertStyleSeparator() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    Style paraStyle = builder.getDocument().getStyles().add(StyleType.PARAGRAPH, "MyParaStyle");
    paraStyle.getFont().setBold(false);
    paraStyle.getFont().setSize(8.0);
    paraStyle.getFont().setName("Arial");
    // ต่อท้ายข้อความด้วยสไตล์ "หัวเรื่อง 1"
    builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_1);
    builder.write("Heading 1");
    builder.insertStyleSeparator();
    // ต่อท้ายข้อความด้วยสไตล์อื่น
    builder.getParagraphFormat().setStyleName(paraStyle.getName());
    builder.write("This is text with some other formatting ");
    doc.save("Your Directory Path" + "WorkingWithStylesAndThemes.InsertStyleSeparator.docx");
}
```

ในโค้ดนี้ เราสร้างสไตล์ย่อหน้าแบบกำหนดเองและแทรกตัวคั่นสไตล์เพื่อสลับสไตล์ภายในย่อหน้าเดียวกัน

## บทสรุป

คู่มือนี้ครอบคลุมพื้นฐานการทำงานกับสไตล์และธีมใน Aspose.Words สำหรับ Java คุณได้เรียนรู้วิธีดึงและคัดลอกสไตล์ จัดการธีม และแทรกตัวแยกสไตล์เพื่อสร้างเอกสารที่มีรูปลักษณ์สวยงามและมีรูปแบบที่ดี ทดลองใช้เทคนิคเหล่านี้เพื่อปรับแต่งเอกสารของคุณตามความต้องการของคุณ


## คำถามที่พบบ่อย

### ฉันจะดึงคุณสมบัติธีมใน Aspose.Words สำหรับ Java ได้อย่างไร

คุณสามารถเรียกข้อมูลคุณสมบัติธีมได้โดยการเข้าถึงอ็อบเจ็กต์ธีมและคุณสมบัติต่างๆ

### ฉันจะตั้งค่าคุณสมบัติของธีม เช่น แบบอักษรและสีได้อย่างไร

คุณสามารถตั้งค่าคุณสมบัติของธีมได้โดยการแก้ไขคุณสมบัติของอ็อบเจ็กต์ธีม

### ฉันจะใช้ตัวคั่นสไตล์เพื่อสลับสไตล์ภายในย่อหน้าเดียวกันได้อย่างไร

 คุณสามารถแทรกตัวคั่นสไตล์ได้โดยใช้`insertStyleSeparator` วิธีการของ`DocumentBuilder` ระดับ.