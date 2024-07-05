---
title: การใช้คุณสมบัติเอกสารใน Aspose.Words สำหรับ Java
linktitle: การใช้คุณสมบัติเอกสาร
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เพิ่มประสิทธิภาพการจัดการเอกสารด้วย Aspose.Words สำหรับ Java เรียนรู้การทำงานกับคุณสมบัติเอกสาร เพิ่มข้อมูลเมตาที่กำหนดเอง และอื่นๆ ในบทช่วยสอนที่ครอบคลุมนี้
type: docs
weight: 32
url: /th/java/document-manipulation/using-document-properties/
---

## ความรู้เบื้องต้นเกี่ยวกับคุณสมบัติของเอกสาร

คุณสมบัติของเอกสารเป็นส่วนสำคัญของเอกสารใดๆ โดยให้ข้อมูลเพิ่มเติมเกี่ยวกับเอกสาร เช่น ชื่อ ผู้แต่ง หัวเรื่อง คำสำคัญ และอื่นๆ ใน Aspose.Words สำหรับ Java คุณสามารถจัดการคุณสมบัติเอกสารทั้งในตัวและแบบกำหนดเองได้

## การแจงนับคุณสมบัติของเอกสาร

### คุณสมบัติในตัว

หากต้องการดึงข้อมูลและทำงานกับคุณสมบัติเอกสารในตัว คุณสามารถใช้ข้อมูลโค้ดต่อไปนี้:

```java
@Test
public void enumerateProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
    System.out.println("2. Built-in Properties");
    for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
        System.out.println(MessageFormat.format("{0} : {1}", prop.getName(), prop.getValue()));
}
```

รหัสนี้จะแสดงชื่อของเอกสารและคุณสมบัติในตัว รวมถึงคุณสมบัติเช่น "ชื่อเรื่อง" "ผู้เขียน" และ "คำหลัก"

### คุณสมบัติที่กำหนดเอง

หากต้องการทำงานกับคุณสมบัติเอกสารแบบกำหนดเอง คุณสามารถใช้ข้อมูลโค้ดต่อไปนี้:

```java
@Test
public void addCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();

    if (customDocumentProperties.get("Authorized") != null) return;

    customDocumentProperties.add("Authorized", true);
    customDocumentProperties.add("Authorized By", "John Smith");
    customDocumentProperties.add("Authorized Date", new Date());
    customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
    customDocumentProperties.add("Authorized Amount", 123.45);
}
```

ข้อมูลโค้ดนี้สาธิตวิธีการเพิ่มคุณสมบัติเอกสารที่กำหนดเอง รวมถึงค่าบูลีน สตริง วันที่ หมายเลขการแก้ไข และค่าตัวเลข

## การลบคุณสมบัติเอกสาร

เมื่อต้องการลบคุณสมบัติเอกสารเฉพาะ คุณสามารถใช้รหัสต่อไปนี้:

```java
@Test
public void removeCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    doc.getCustomDocumentProperties().remove("Authorized Date");
}
```

รหัสนี้จะลบคุณสมบัติแบบกำหนดเอง "วันที่ได้รับอนุญาต" ออกจากเอกสาร

## การกำหนดค่าลิงก์ไปยังเนื้อหา

ในบางกรณี คุณอาจต้องการสร้างลิงก์ภายในเอกสารของคุณ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
@Test
public void configuringLinkToContent() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.startBookmark("MyBookmark");
    builder.writeln("Text inside a bookmark.");
    builder.endBookmark("MyBookmark");

    CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();

    // เพิ่มเชื่อมโยงกับคุณสมบัติเนื้อหา
    DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
    customProperty = customProperties.get("Bookmark");
    boolean isLinkedToContent = customProperty.isLinkToContent();
    String linkSource = customProperty.getLinkSource();
    String customPropertyValue = customProperty.getValue().toString();
}
```

ข้อมูลโค้ดนี้สาธิตวิธีสร้างบุ๊กมาร์กในเอกสารของคุณ และเพิ่มคุณสมบัติเอกสารที่กำหนดเองซึ่งลิงก์ไปยังบุ๊กมาร์กนั้น

## การแปลงระหว่างหน่วยการวัด

ใน Aspose.Words สำหรับ Java คุณสามารถแปลงหน่วยการวัดได้อย่างง่ายดาย นี่คือตัวอย่างวิธีการ:

```java
@Test
public void convertBetweenMeasurementUnits() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    PageSetup pageSetup = builder.getPageSetup();

    // กำหนดระยะขอบเป็นนิ้ว
    pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
    pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
}
```

ข้อมูลโค้ดนี้กำหนดระยะขอบและระยะทางต่างๆ เป็นนิ้วโดยแปลงเป็นจุด

## การใช้อักขระควบคุม

อักขระควบคุมมีประโยชน์เมื่อต้องจัดการกับข้อความ ต่อไปนี้เป็นวิธีแทนที่อักขระควบคุมในข้อความของคุณ:

```java
@Test
public void useControlCharacters()
{
    final String TEXT = "test\r";

    // แทนที่อักขระควบคุม "\r" ด้วย "\r\n"
    String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
}
```

ในตัวอย่างนี้ เราแทนที่การขึ้นบรรทัดใหม่ (`\r`) โดยมีการขึ้นบรรทัดใหม่ตามด้วยการป้อนบรรทัด (`\r\n`-

## บทสรุป

คุณสมบัติเอกสารมีบทบาทสำคัญในการจัดการและการจัดระเบียบเอกสารของคุณอย่างมีประสิทธิภาพใน Aspose.Words สำหรับ Java ไม่ว่าจะทำงานกับคุณสมบัติในตัว คุณสมบัติแบบกำหนดเอง หรือการใช้อักขระควบคุม คุณมีเครื่องมือมากมายที่พร้อมใช้เพื่อเพิ่มขีดความสามารถในการจัดการเอกสารของคุณ

## คำถามที่พบบ่อย

### ฉันจะเข้าถึงคุณสมบัติเอกสารในตัวได้อย่างไร

 หากต้องการเข้าถึงคุณสมบัติเอกสารในตัวใน Aspose.Words สำหรับ Java คุณสามารถใช้`getBuiltInDocumentProperties` วิธีการบน`Document` วัตถุ. เมธอดนี้จะส่งคืนคอลเลกชันของคุณสมบัติบิวท์อินที่คุณสามารถวนซ้ำได้

### ฉันสามารถเพิ่มคุณสมบัติเอกสารแบบกำหนดเองให้กับเอกสารได้หรือไม่

 ใช่ คุณสามารถเพิ่มคุณสมบัติเอกสารแบบกำหนดเองให้กับเอกสารได้โดยใช้`CustomDocumentProperties` ของสะสม. คุณสามารถกำหนดคุณสมบัติที่กำหนดเองด้วยประเภทข้อมูลต่างๆ รวมถึงสตริง บูลีน วันที่ และค่าตัวเลข

### ฉันจะลบคุณสมบัติเอกสารแบบกำหนดเองเฉพาะได้อย่างไร

 หากต้องการลบคุณสมบัติเอกสารแบบกำหนดเอง คุณสามารถใช้`remove` วิธีการบน`CustomDocumentProperties`คอลเลกชัน โดยส่งชื่อของคุณสมบัติที่คุณต้องการลบเป็นพารามิเตอร์

### จุดประสงค์ของการเชื่อมโยงไปยังเนื้อหาภายในเอกสารคืออะไร?

การลิงก์ไปยังเนื้อหาภายในเอกสารทำให้คุณสามารถสร้างการอ้างอิงแบบไดนามิกไปยังส่วนเฉพาะของเอกสารได้ สิ่งนี้มีประโยชน์สำหรับการสร้างเอกสารเชิงโต้ตอบหรือการอ้างอิงโยงระหว่างส่วนต่างๆ

### ฉันจะแปลงระหว่างหน่วยการวัดที่แตกต่างกันใน Aspose.Words สำหรับ Java ได้อย่างไร

 คุณสามารถแปลงระหว่างหน่วยการวัดต่างๆ ใน Aspose.Words สำหรับ Java ได้โดยใช้`ConvertUtil` ระดับ. โดยมีวิธีการแปลงหน่วยต่างๆ เช่น นิ้วเป็นจุด จุดเป็นเซนติเมตร และอื่นๆ