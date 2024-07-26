---
title: การใช้ตัวเลือกการล้างข้อมูลใน Aspose.Words สำหรับ Java
linktitle: การใช้ตัวเลือกการล้างข้อมูล
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เพิ่มความชัดเจนของเอกสารด้วย Aspose.Words สำหรับตัวเลือกการล้างข้อมูล Java เรียนรู้วิธีลบย่อหน้าว่าง ขอบเขตที่ไม่ได้ใช้ และอื่นๆ
type: docs
weight: 10
url: /th/java/document-manipulation/using-cleanup-options/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการใช้ตัวเลือกการล้างข้อมูลใน Aspose.Words สำหรับ Java

ในบทช่วยสอนนี้ เราจะสำรวจวิธีใช้ตัวเลือกการล้างข้อมูลใน Aspose.Words สำหรับ Java เพื่อจัดการและล้างข้อมูลเอกสารในระหว่างกระบวนการจดหมายเวียน ตัวเลือกการล้างข้อมูลช่วยให้คุณสามารถควบคุมลักษณะต่างๆ ของการล้างเอกสาร เช่น การลบย่อหน้าว่าง ขอบเขตที่ไม่ได้ใช้ และอื่นๆ

## ข้อกำหนดเบื้องต้น

 ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Words for Java เข้ากับโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/java/).

## ขั้นตอนที่ 1: การลบย่อหน้าว่าง

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกเขตข้อมูลผสาน
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// ตั้งค่าตัวเลือกการล้างข้อมูล
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// เปิดใช้งานการล้างย่อหน้าด้วยเครื่องหมายวรรคตอน
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// ดำเนินการจดหมายเวียน
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// บันทึกเอกสาร
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

ในตัวอย่างนี้ เราสร้างเอกสารใหม่ แทรกเขตข้อมูลผสาน และตั้งค่าตัวเลือกการล้างข้อมูลเพื่อลบย่อหน้าว่าง นอกจากนี้ เรายังช่วยให้สามารถลบย่อหน้าที่มีเครื่องหมายวรรคตอนได้ หลังจากดำเนินการจดหมายเวียน เอกสารจะถูกบันทึกโดยใช้การล้างข้อมูลที่ระบุ

## ขั้นตอนที่ 2: การลบภูมิภาคที่ไม่ได้รวมเข้าด้วยกัน

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// ตั้งค่าตัวเลือกการล้างข้อมูลเพื่อลบภูมิภาคที่ไม่ได้ใช้
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// ดำเนินการจดหมายเวียนกับภูมิภาค
doc.getMailMerge().executeWithRegions(data);

// บันทึกเอกสาร
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

ในตัวอย่างนี้ เราเปิดเอกสารที่มีอยู่ด้วยขอบเขตการผสาน ตั้งค่าตัวเลือกการล้างข้อมูลเพื่อลบขอบเขตที่ไม่ได้ใช้ จากนั้นจึงดำเนินการจดหมายเวียนด้วยข้อมูลว่าง กระบวนการนี้จะลบขอบเขตที่ไม่ได้ใช้ออกจากเอกสารโดยอัตโนมัติ

## ขั้นตอนที่ 3: การลบฟิลด์ว่าง

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// ตั้งค่าตัวเลือกการล้างข้อมูลเพื่อลบฟิลด์ว่าง
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// ดำเนินการจดหมายเวียน
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// บันทึกเอกสาร
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

ในตัวอย่างนี้ เราเปิดเอกสารที่มีเขตข้อมูลผสาน ตั้งค่าตัวเลือกการล้างข้อมูลเพื่อลบเขตข้อมูลว่าง และดำเนินการจดหมายเวียนด้วยข้อมูล หลังจากการผสาน ช่องว่างใดๆ จะถูกลบออกจากเอกสาร

## ขั้นตอนที่ 4: การลบฟิลด์ที่ไม่ได้ใช้

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// ตั้งค่าตัวเลือกการล้างข้อมูลเพื่อลบฟิลด์ที่ไม่ได้ใช้
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// ดำเนินการจดหมายเวียน
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// บันทึกเอกสาร
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

ในตัวอย่างนี้ เราเปิดเอกสารที่มีเขตข้อมูลผสาน ตั้งค่าตัวเลือกการล้างข้อมูลเพื่อลบเขตข้อมูลที่ไม่ได้ใช้ และดำเนินการจดหมายเวียนด้วยข้อมูล หลังจากการผสาน ฟิลด์ที่ไม่ได้ใช้จะถูกลบออกจากเอกสาร

## ขั้นตอนที่ 5: การลบฟิลด์ที่มี

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// ตั้งค่าตัวเลือกการล้างข้อมูลเพื่อลบฟิลด์ที่มีข้อมูล
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// ดำเนินการจดหมายเวียน
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// บันทึกเอกสาร
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

ในตัวอย่างนี้ เราเปิดเอกสารที่มีเขตข้อมูลผสาน ตั้งค่าตัวเลือกการล้างข้อมูลเพื่อลบเขตข้อมูลที่มี และดำเนินการจดหมายเวียนด้วยข้อมูล หลังจากการผสาน เขตข้อมูลต่างๆ จะถูกลบออกจากเอกสาร

## ขั้นตอนที่ 6: การลบแถวตารางว่าง

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// ตั้งค่าตัวเลือกการล้างข้อมูลเพื่อลบแถวตารางว่าง
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// ดำเนินการจดหมายเวียน
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// บันทึกเอกสาร
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

ในตัวอย่างนี้ เราเปิดเอกสารที่มีตารางและเขตข้อมูลผสาน ตั้งค่าตัวเลือกการล้างข้อมูลเพื่อลบแถวตารางว่าง และดำเนินการจดหมายเวียนด้วยข้อมูล หลังจากการผสาน แถวตารางว่างใดๆ จะถูกลบออกจากเอกสาร

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีใช้ตัวเลือกการล้างข้อมูลใน Aspose.Words สำหรับ Java เพื่อจัดการและล้างข้อมูลเอกสารในระหว่างกระบวนการจดหมายเวียน ตัวเลือกเหล่านี้ให้การควบคุมการล้างเอกสารอย่างละเอียด ช่วยให้คุณสร้างเอกสารที่สวยงามและปรับแต่งเองได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### ตัวเลือกการล้างข้อมูลใน Aspose.Words สำหรับ Java คืออะไร

ตัวเลือกการล้างข้อมูลใน Aspose.Words สำหรับ Java คือการตั้งค่าที่ช่วยให้คุณสามารถควบคุมลักษณะต่างๆ ของการล้างข้อมูลเอกสารในระหว่างกระบวนการจดหมายเวียน ช่วยให้คุณสามารถลบองค์ประกอบที่ไม่จำเป็น เช่น ย่อหน้าว่าง ขอบเขตที่ไม่ได้ใช้ และอื่นๆ เพื่อให้มั่นใจว่าเอกสารขั้นสุดท้ายของคุณมีโครงสร้างที่ดีและสวยงาม

### ฉันจะลบย่อหน้าว่างออกจากเอกสารของฉันได้อย่างไร

 หากต้องการลบย่อหน้าว่างออกจากเอกสารของคุณโดยใช้ Aspose.Words สำหรับ Java คุณสามารถตั้งค่า`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` ตัวเลือกเป็นจริง การดำเนินการนี้จะกำจัดย่อหน้าที่ไม่มีเนื้อหาโดยอัตโนมัติ ส่งผลให้เอกสารสะอาดยิ่งขึ้น

###  จุดประสงค์ของ..คืออะไร.`REMOVE_UNUSED_REGIONS` cleanup option?

 ที่`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` ตัวเลือกนี้ใช้เพื่อลบขอบเขตในเอกสารที่ไม่มีข้อมูลที่เกี่ยวข้องในระหว่างกระบวนการจดหมายเวียน ช่วยให้เอกสารของคุณเป็นระเบียบเรียบร้อยโดยการกำจัดตัวยึดตำแหน่งที่ไม่ได้ใช้

### ฉันสามารถลบแถวตารางว่างออกจากเอกสารโดยใช้ Aspose.Words สำหรับ Java ได้หรือไม่

 ได้ คุณสามารถลบแถวตารางว่างออกจากเอกสารได้โดยการตั้งค่า`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`ตัวเลือกการล้างข้อมูลเป็นจริง การดำเนินการนี้จะลบแถวของตารางที่ไม่มีข้อมูลโดยอัตโนมัติ เพื่อให้มั่นใจว่าตารางมีโครงสร้างที่ดีในเอกสารของคุณ

###  จะเกิดอะไรขึ้นเมื่อฉันตั้งค่า`REMOVE_CONTAINING_FIELDS` option?

 การตั้งค่า`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` ตัวเลือกจะลบฟิลด์ผสานทั้งหมด รวมถึงย่อหน้าที่มี ออกจากเอกสารในระหว่างกระบวนการจดหมายเวียน สิ่งนี้มีประโยชน์เมื่อคุณต้องการกำจัดเขตข้อมูลผสานและข้อความที่เกี่ยวข้อง

### ฉันจะลบเขตข้อมูลผสานที่ไม่ได้ใช้ออกจากเอกสารของฉันได้อย่างไร

 หากต้องการลบเขตข้อมูลผสานที่ไม่ได้ใช้ออกจากเอกสาร คุณสามารถตั้งค่า`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` ตัวเลือกเป็นจริง การดำเนินการนี้จะกำจัดเขตข้อมูลผสานที่ไม่ได้ถูกเติมระหว่างจดหมายเวียนโดยอัตโนมัติ ส่งผลให้เอกสารสะอาดยิ่งขึ้น

###  อะไรคือความแตกต่างระหว่าง`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

 ที่`REMOVE_EMPTY_FIELDS` ตัวเลือกลบเขตข้อมูลผสานที่ไม่มีข้อมูลหรือว่างเปล่าในระหว่างกระบวนการจดหมายเวียน ในทางกลับกัน`REMOVE_UNUSED_FIELDS`ตัวเลือกจะลบเขตข้อมูลผสานที่ไม่ได้เติมข้อมูลระหว่างการผสาน ตัวเลือกระหว่างพวกเขาขึ้นอยู่กับว่าคุณต้องการลบเขตข้อมูลที่ไม่มีเนื้อหาหรือเขตข้อมูลที่ไม่ได้ใช้ในการดำเนินการผสานเฉพาะ

### ฉันจะเปิดใช้งานการลบย่อหน้าที่มีเครื่องหมายวรรคตอนได้อย่างไร

 หากต้องการเปิดใช้งานการลบย่อหน้าที่มีเครื่องหมายวรรคตอน คุณสามารถตั้งค่าได้`cleanupParagraphsWithPunctuationMarks` ตัวเลือกเป็นจริงและระบุเครื่องหมายวรรคตอนที่จะพิจารณาสำหรับการล้างข้อมูล วิธีนี้ช่วยให้คุณสร้างเอกสารที่ละเอียดยิ่งขึ้นโดยการลบย่อหน้าที่มีเครื่องหมายวรรคตอนเท่านั้นที่ไม่จำเป็นออก

### ฉันสามารถปรับแต่งตัวเลือกการล้างข้อมูลใน Aspose.Words สำหรับ Java ได้หรือไม่

ได้ คุณสามารถปรับแต่งตัวเลือกการล้างข้อมูลได้ตามความต้องการเฉพาะของคุณ คุณสามารถเลือกตัวเลือกการล้างข้อมูลที่จะใช้และกำหนดค่าตามข้อกำหนดการล้างข้อมูลเอกสารของคุณ เพื่อให้มั่นใจว่าเอกสารขั้นสุดท้ายของคุณตรงตามมาตรฐานที่คุณต้องการ