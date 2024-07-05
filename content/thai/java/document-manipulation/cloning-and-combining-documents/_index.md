---
title: การโคลนและการรวมเอกสารใน Aspose.Words สำหรับ Java
linktitle: การโคลนและการรวมเอกสาร
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีโคลนและรวมเอกสารใน Aspose.Words สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างซอร์สโค้ด
type: docs
weight: 27
url: /th/java/document-manipulation/cloning-and-combining-documents/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการโคลนและการรวมเอกสารใน Aspose.Words สำหรับ Java

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการโคลนและรวมเอกสารโดยใช้ Aspose.Words สำหรับ Java เราจะครอบคลุมสถานการณ์ต่างๆ รวมถึงการโคลนเอกสาร การแทรกเอกสารที่จุดแทนที่ บุ๊กมาร์ก และระหว่างการดำเนินการจดหมายเวียน

## ขั้นตอนที่ 1: การโคลนเอกสาร

 หากต้องการโคลนเอกสารใน Aspose.Words สำหรับ Java คุณสามารถใช้ไฟล์`deepClone()` วิธี. นี่เป็นตัวอย่างง่ายๆ:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "CloneAndCombineDocuments.CloningDocument.docx");
```

โค้ดนี้จะสร้างสำเนาแบบลึกของเอกสารต้นฉบับและบันทึกเป็นไฟล์ใหม่

## ขั้นตอนที่ 2: การแทรกเอกสารที่จุดแทนที่

คุณสามารถแทรกเอกสารที่จุดแทนที่เฉพาะในเอกสารอื่นได้ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
FindReplaceOptions options = new FindReplaceOptions();
options.setDirection(FindReplaceDirection.BACKWARD);
options.setReplacingCallback(new InsertDocumentAtReplaceHandler());
mainDoc.getRange().replace(Pattern.compile("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

 ในตัวอย่างนี้ เราใช้ a`FindReplaceOptions` วัตถุเพื่อระบุตัวจัดการการเรียกกลับสำหรับการแทนที่ ที่`InsertDocumentAtReplaceHandler` คลาสจัดการตรรกะการแทรก

## ขั้นตอนที่ 3: การแทรกเอกสารที่บุ๊กมาร์ก

หากต้องการแทรกเอกสารที่บุ๊กมาร์กเฉพาะในเอกสารอื่น คุณสามารถใช้รหัสต่อไปนี้:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
Document subDoc = new Document("Your Directory Path" + "Document insertion 2.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("insertionPlace");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtBookmark.docx");
```

 ที่นี่เราค้นหาบุ๊กมาร์กตามชื่อและใช้`insertDocument` วิธีการแทรกเนื้อหาของ`subDoc` เอกสารที่ตำแหน่งบุ๊กมาร์ก

## ขั้นตอนที่ 4: การแทรกเอกสารระหว่างจดหมายเวียน

คุณสามารถแทรกเอกสารระหว่างการดำเนินการจดหมายเวียนใน Aspose.Words สำหรับ Java มีวิธีดังนี้:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "Document_1" }, new Object[] { "Your Directory Path" + "Document insertion 2.docx" });
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

 ในตัวอย่างนี้ เราตั้งค่าฟิลด์ที่รวมการโทรกลับโดยใช้`InsertDocumentAtMailMergeHandler` คลาสเพื่อจัดการการแทรกเอกสารที่ระบุโดยฟิลด์ "Document_1"

## บทสรุป

การโคลนและการรวมเอกสารใน Aspose.Words สำหรับ Java สามารถทำได้โดยใช้เทคนิคต่างๆ ไม่ว่าคุณต้องการโคลนเอกสาร แทรกเนื้อหาที่จุดแทนที่ บุ๊กมาร์ก หรือระหว่างการรวมจดหมาย Aspose.Words มอบคุณสมบัติอันทรงพลังเพื่อจัดการเอกสารได้อย่างราบรื่น

## คำถามที่พบบ่อย

### ฉันจะโคลนเอกสารใน Aspose.Words สำหรับ Java ได้อย่างไร

 คุณสามารถโคลนเอกสารใน Aspose.Words สำหรับ Java ได้โดยใช้`deepClone()` วิธี. นี่คือตัวอย่าง:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "ClonedDocument.docx");
```

### ฉันจะแทรกเอกสารลงในบุ๊กมาร์กได้อย่างไร?

 หากต้องการแทรกเอกสารที่บุ๊กมาร์กใน Aspose.Words สำหรับ Java คุณสามารถค้นหาบุ๊กมาร์กตามชื่อ จากนั้นใช้`insertDocument` วิธีการแทรกเนื้อหา นี่คือตัวอย่าง:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
Document subDoc = new Document("Your Directory Path" + "SubDocument.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("MyBookmark");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CombinedDocument.docx");
```

### ฉันจะแทรกเอกสารระหว่างจดหมายเวียนใน Aspose.Words สำหรับ Java ได้อย่างไร

คุณสามารถแทรกเอกสารระหว่างจดหมายเวียนใน Aspose.Words สำหรับ Java ได้โดยตั้งค่าฟิลด์ที่รวมการโทรกลับและระบุเอกสารที่จะแทรก นี่คือตัวอย่าง:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "DocumentField" }, new Object[] { "Your Directory Path" + "DocumentToInsert.docx" });
mainDoc.save("Your Directory Path" + "MergedDocument.docx");
```

 ในตัวอย่างนี้`InsertDocumentAtMailMergeHandler`คลาสจัดการตรรกะการแทรกสำหรับ "DocumentField" ในระหว่างจดหมายเวียน