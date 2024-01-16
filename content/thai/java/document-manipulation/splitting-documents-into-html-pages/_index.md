---
title: การแบ่งเอกสารออกเป็นหน้า HTML ใน Aspose.Words สำหรับ Java
linktitle: การแบ่งเอกสารออกเป็นหน้า HTML
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีแบ่งเอกสารออกเป็นหน้า HTML ด้วย Aspose.Words สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการแปลงเอกสารที่ราบรื่น
type: docs
weight: 25
url: /th/java/document-manipulation/splitting-documents-into-html-pages/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการแบ่งเอกสารออกเป็นหน้า HTML ใน Aspose.Words สำหรับ Java

ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีแบ่งเอกสารออกเป็นหน้า HTML โดยใช้ Aspose.Words สำหรับ Java Aspose.Words เป็น Java API ที่ทรงพลังสำหรับการทำงานกับเอกสาร Microsoft Word และมีคุณสมบัติมากมายสำหรับการจัดการเอกสาร รวมถึงความสามารถในการแปลงเอกสารเป็นรูปแบบต่าง ๆ รวมถึง HTML

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Words สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/java/).

## ขั้นตอนที่ 1: นำเข้าแพ็คเกจที่จำเป็น

```java
import com.aspose.words.*;
import java.io.*;
import java.util.ArrayList;
```

## ขั้นตอนที่ 2: สร้างวิธีการสำหรับการแปลง Word เป็น HTML

```java
class WordToHtmlConverter
{
    // รายละเอียดการใช้งานสำหรับการแปลง Word เป็น HTML
    // ...
}
```

## ขั้นตอนที่ 3: เลือกย่อหน้าหัวเรื่องเมื่อหัวข้อเริ่มต้น

```java
private ArrayList<Paragraph> selectTopicStarts()
{
    NodeCollection paras = mDoc.getChildNodes(NodeType.PARAGRAPH, true);
    ArrayList<Paragraph> topicStartParas = new ArrayList<Paragraph>();
    for (Paragraph para : (Iterable<Paragraph>) paras)
    {
        int style = para.getParagraphFormat().getStyleIdentifier();
        if (style == StyleIdentifier.HEADING_1)
            topicStartParas.add(para);
    }
    return topicStartParas;
}
```

## ขั้นตอนที่ 4: แทรกตัวแบ่งส่วนก่อนย่อหน้าหัวเรื่อง

```java
private void insertSectionBreaks(ArrayList<Paragraph> topicStartParas)
{
    DocumentBuilder builder = new DocumentBuilder(mDoc);
    for (Paragraph para : topicStartParas)
    {
        Section section = para.getParentSection();
        if (para != section.getBody().getFirstParagraph())
        {
            builder.moveTo(para.getFirstChild());
            builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
            section.getBody().getLastParagraph().remove();
        }
    }
}
```

## ขั้นตอนที่ 5: แบ่งเอกสารออกเป็นหัวข้อ

```java
private ArrayList<Topic> saveHtmlTopics() throws Exception
{
    ArrayList<Topic> topics = new ArrayList<Topic>();
    for (int sectionIdx = 0; sectionIdx < mDoc.getSections().getCount(); sectionIdx++)
    {
        Section section = mDoc.getSections().get(sectionIdx);
        String paraText = section.getBody().getFirstParagraph().getText();
        String fileName = makeTopicFileName(paraText);
        if ("".equals(fileName))
            fileName = "UNTITLED SECTION " + sectionIdx;
        fileName = mDstDir + fileName + ".html";
        String title = makeTopicTitle(paraText);
        if ("".equals(title))
            title = "UNTITLED SECTION " + sectionIdx;
        Topic topic = new Topic(title, fileName);
        topics.add(topic);
        saveHtmlTopic(section, topic);
    }
    return topics;
}
```

## ขั้นตอนที่ 6: บันทึกแต่ละหัวข้อเป็นไฟล์ HTML

```java
private void saveHtmlTopic(Section section, Topic topic) throws Exception
{
    Document dummyDoc = new Document();
    dummyDoc.removeAllChildren();
    dummyDoc.appendChild(dummyDoc.importNode(section, true, ImportFormatMode.KEEP_SOURCE_FORMATTING));
    dummyDoc.getBuiltInDocumentProperties().setTitle(topic.getTitle());
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    {
        saveOptions.setPrettyFormat(true);
        saveOptions.setAllowNegativeIndent(true);
        saveOptions.setExportHeadersFootersMode(ExportHeadersFootersMode.NONE);
    }
    dummyDoc.save(topic.getFileName(), saveOptions);
}
```

## ขั้นตอนที่ 7: สร้างสารบัญสำหรับหัวข้อต่างๆ

```java
private void saveTableOfContents(ArrayList<Topic> topics) throws Exception
{
    Document tocDoc = new Document(mTocTemplate);
    tocDoc.getMailMerge().setFieldMergingCallback(new HandleTocMergeField());
    tocDoc.getMailMerge().executeWithRegions(new TocMailMergeDataSource(topics));
    tocDoc.save(mDstDir + "contents.html");
}
```

ตอนนี้เราได้สรุปขั้นตอนต่างๆ แล้ว คุณสามารถปรับใช้แต่ละขั้นตอนในโปรเจ็กต์ Java ของคุณเพื่อแบ่งเอกสารออกเป็นหน้า HTML โดยใช้ Aspose.Words สำหรับ Java กระบวนการนี้จะช่วยให้คุณสร้างการแสดง HTML ที่มีโครงสร้างสำหรับเอกสารของคุณ ทำให้เข้าถึงได้ง่ายและใช้งานง่ายยิ่งขึ้น

## บทสรุป

ในคู่มือที่ครอบคลุมนี้ เราได้กล่าวถึงกระบวนการแบ่งเอกสารออกเป็นหน้า HTML โดยใช้ Aspose.Words สำหรับ Java ด้วยการทำตามขั้นตอนที่ระบุไว้ คุณสามารถแปลงเอกสาร Word เป็นรูปแบบ HTML ได้อย่างมีประสิทธิภาพ ทำให้เนื้อหาของคุณเข้าถึงได้ง่ายขึ้นบนเว็บ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Words สำหรับ Java ได้อย่างไร

 หากต้องการติดตั้ง Aspose.Words สำหรับ Java คุณสามารถดาวน์โหลดไลบรารีได้จาก[ที่นี่](https://releases.aspose.com/words/java/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบ

### ฉันสามารถปรับแต่งเอาต์พุต HTML ได้หรือไม่

 ใช่ คุณสามารถปรับแต่งเอาต์พุต HTML ได้โดยการปรับตัวเลือกการบันทึกใน`HtmlSaveOptions` ระดับ. สิ่งนี้ช่วยให้คุณควบคุมการจัดรูปแบบและรูปลักษณ์ของไฟล์ HTML ที่สร้างขึ้น

### Aspose.Words สำหรับ Java รองรับ Microsoft Word เวอร์ชันใดบ้าง

Aspose.Words สำหรับ Java รองรับรูปแบบเอกสาร Microsoft Word ที่หลากหลาย รวมถึง DOC, DOCX, RTF และอื่นๆ สามารถทำงานร่วมกับ Microsoft Word เวอร์ชันต่างๆ ได้

### ฉันจะจัดการรูปภาพใน HTML ที่แปลงแล้วได้อย่างไร

Aspose.Words สำหรับ Java สามารถจัดการรูปภาพใน HTML ที่แปลงแล้วโดยบันทึกเป็นไฟล์แยกกันในโฟลเดอร์เดียวกันกับไฟล์ HTML เพื่อให้แน่ใจว่ารูปภาพจะแสดงอย่างถูกต้องในเอาต์พุต HTML

### มี Aspose.Words สำหรับ Java เวอร์ชันทดลองใช้งานหรือไม่

ได้ คุณสามารถขอ Aspose.Words สำหรับ Java เวอร์ชันทดลองใช้ฟรีได้จากเว็บไซต์ Aspose เพื่อประเมินคุณสมบัติและความสามารถของเวอร์ชันก่อนซื้อใบอนุญาต