---
title: การค้นหาและการจำลองข้อความใน Aspose.Words สำหรับ Java
linktitle: การค้นหาและการจำลองข้อความ
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีค้นหาและแทนที่ข้อความในเอกสาร Word ด้วย Aspose.Words สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด พัฒนาทักษะการจัดการเอกสาร Java ของคุณ
type: docs
weight: 15
url: /th/java/document-manipulation/finding-and-replacing-text/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการค้นหาและการแทนที่ข้อความใน Aspose.Words สำหรับ Java

Aspose.Words สำหรับ Java เป็น Java API ที่ทรงพลังซึ่งช่วยให้คุณทำงานกับเอกสาร Word โดยทางโปรแกรมได้ งานทั่วไปอย่างหนึ่งเมื่อต้องจัดการกับเอกสาร Word คือการค้นหาและแทนที่ข้อความ ไม่ว่าคุณจะต้องการอัปเดตตัวยึดตำแหน่งในเทมเพลตหรือดำเนินการจัดการข้อความที่ซับซ้อนมากขึ้น Aspose.Words สำหรับ Java สามารถช่วยให้คุณบรรลุเป้าหมายได้อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกรายละเอียดของการค้นหาและแทนที่ข้อความ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- สภาพแวดล้อมการพัฒนาจาวา
- Aspose.Words สำหรับไลบรารี Java
- ตัวอย่างเอกสาร Word ที่จะใช้งาน

 คุณสามารถดาวน์โหลดไลบรารี Aspose.Words สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/words/java/).

## การค้นหาและการจำลองข้อความอย่างง่าย

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// สร้าง DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// ค้นหาและแทนที่ข้อความ
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

 ในตัวอย่างนี้ เราโหลดเอกสาร Word สร้างไฟล์`DocumentBuilder` และใช้`replace` วิธีค้นหาและแทนที่ "ข้อความเก่า" ด้วย "ข้อความใหม่" ภายในเอกสาร

## การใช้นิพจน์ทั่วไป

นิพจน์ทั่วไปมีความสามารถในการจับคู่รูปแบบที่มีประสิทธิภาพสำหรับการค้นหาและการแทนที่ข้อความ Aspose.Words สำหรับ Java รองรับนิพจน์ทั่วไปเพื่อการค้นหาและแทนที่ขั้นสูงยิ่งขึ้น

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// สร้าง DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// ใช้นิพจน์ทั่วไปในการค้นหาและแทนที่ข้อความ
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

ในตัวอย่างนี้ เราใช้รูปแบบนิพจน์ทั่วไปเพื่อค้นหาและแทนที่ข้อความภายในเอกสาร

## ละเว้นข้อความภายในช่อง

คุณสามารถกำหนดค่า Aspose. Words ให้ละเว้นข้อความภายในฟิลด์เมื่อดำเนินการค้นหาและแทนที่

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// สร้างอินสแตนซ์ FindReplaceOptions และตั้งค่า IgnoreFields เป็นจริง
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// ใช้ตัวเลือกเมื่อแทนที่ข้อความ
doc.getRange().replace("text-to-replace", "new-text", options);

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

สิ่งนี้มีประโยชน์เมื่อคุณต้องการยกเว้นข้อความภายในฟิลด์ เช่น ฟิลด์ผสาน ไม่ให้ถูกแทนที่

## ละเว้นข้อความภายในการลบการแก้ไข

คุณสามารถกำหนดค่า Aspose. Words ให้ละเว้นข้อความภายในการแก้ไขการลบระหว่างการดำเนินการค้นหาและแทนที่

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// สร้างอินสแตนซ์ FindReplaceOptions และตั้งค่า IgnoreDeleted เป็นจริง
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// ใช้ตัวเลือกเมื่อแทนที่ข้อความ
doc.getRange().replace("text-to-replace", "new-text", options);

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

ซึ่งจะทำให้คุณสามารถยกเว้นข้อความที่ถูกทำเครื่องหมายเพื่อลบในการเปลี่ยนแปลงที่ติดตามไม่ให้ถูกแทนที่

## ละเว้นข้อความภายในแทรกการแก้ไข

คุณสามารถกำหนดค่า Aspose. Words ให้ละเว้นข้อความภายในการแก้ไขการแทรกระหว่างการดำเนินการค้นหาและแทนที่

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// สร้างอินสแตนซ์ FindReplaceOptions และตั้งค่า IgnoreInserted เป็นจริง
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// ใช้ตัวเลือกเมื่อแทนที่ข้อความ
doc.getRange().replace("text-to-replace", "new-text", options);

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

ซึ่งจะทำให้คุณสามารถยกเว้นข้อความที่ถูกทำเครื่องหมายว่าแทรกในการเปลี่ยนแปลงที่ติดตามไม่ให้ถูกแทนที่

## การแทนที่ข้อความด้วย HTML

คุณสามารถใช้ Aspose.Words สำหรับ Java เพื่อแทนที่ข้อความด้วยเนื้อหา HTML

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// สร้างอินสแตนซ์ FindReplaceOptions ด้วยการโทรกลับแทนที่แบบกำหนดเอง
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// ใช้ตัวเลือกเมื่อแทนที่ข้อความ
doc.getRange().replace("text-to-replace", "new-html-content", options);

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

 ในตัวอย่างนี้ เราใช้แบบกำหนดเอง`ReplaceWithHtmlEvaluator` เพื่อแทนที่ข้อความด้วยเนื้อหา HTML

## การแทนที่ข้อความในส่วนหัวและส่วนท้าย

คุณสามารถค้นหาและแทนที่ข้อความภายในส่วนหัวและส่วนท้ายของเอกสาร Word ของคุณได้

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// รับคอลเลกชันของส่วนหัวและส่วนท้าย
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// เลือกประเภทส่วนหัวหรือส่วนท้ายที่คุณต้องการแทนที่ข้อความ (เช่น HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// สร้างอินสแตนซ์ FindReplaceOptions และนำไปใช้กับช่วงของส่วนท้าย
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

สิ่งนี้ทำให้คุณสามารถทำการแทนที่ข้อความโดยเฉพาะในส่วนหัวและส่วนท้าย

## กำลังแสดงการเปลี่ยนแปลงสำหรับลำดับส่วนหัวและส่วนท้าย

คุณสามารถใช้ Aspose.Words เพื่อแสดงการเปลี่ยนแปลงสำหรับลำดับส่วนหัวและส่วนท้ายในเอกสารของคุณ

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// รับภาคแรก
Section firstPageSection = doc.getFirstSection();

// สร้างอินสแตนซ์ FindReplaceOptions และนำไปใช้กับช่วงของเอกสาร
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//แทนที่ข้อความที่ส่งผลต่อลำดับส่วนหัวและส่วนท้าย
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

ซึ่งช่วยให้คุณเห็นภาพการเปลี่ยนแปลงที่เกี่ยวข้องกับลำดับส่วนหัวและส่วนท้ายในเอกสารของคุณ

## การแทนที่ข้อความด้วยฟิลด์

คุณสามารถแทนที่ข้อความด้วยฟิลด์โดยใช้ Aspose.Words สำหรับ Java

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// สร้างอินสแตนซ์ FindReplaceOptions และตั้งค่าการเรียกกลับแทนที่แบบกำหนดเองสำหรับฟิลด์
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// ใช้ตัวเลือกเมื่อแทนที่ข้อความ
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

 ในตัวอย่างนี้ เราแทนที่ข้อความด้วยฟิลด์และระบุประเภทฟิลด์ (เช่น`FieldType.FIELD_MERGE_FIELD`-

## แทนที่ด้วยผู้ประเมิน

คุณสามารถใช้ตัวประเมินแบบกำหนดเองเพื่อกำหนดข้อความแทนที่แบบไดนามิกได้

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// สร้างอินสแตนซ์ FindReplaceOptions และตั้งค่าการโทรกลับแทนที่แบบกำหนดเอง
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// ใช้ตัวเลือกเมื่อแทนที่ข้อความ
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

ในตัวอย่างนี้ เราใช้ตัวประเมินที่กำหนดเอง (`MyReplaceEvaluator`) เพื่อแทนที่ข้อความ

## แทนที่ด้วย Regex

Aspose.Words สำหรับ Java ช่วยให้คุณสามารถแทนที่ข้อความโดยใช้นิพจน์ทั่วไป

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// ใช้นิพจน์ทั่วไปในการค้นหาและแทนที่ข้อความ
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

ในตัวอย่างนี้ เราใช้รูปแบบนิพจน์ทั่วไปเพื่อค้นหาและแทนที่ข้อความภายในเอกสาร

## การรับรู้และการทดแทนภายในรูปแบบการแทนที่

คุณสามารถจดจำและทำการทดแทนภายในรูปแบบการแทนที่ได้โดยใช้ Aspose.Words สำหรับ Java

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

//สร้างอินสแตนซ์ FindReplaceOptions โดยตั้งค่า UseSubstitutions เป็นจริง
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// ใช้ตัวเลือกเมื่อแทนที่ข้อความด้วยรูปแบบ
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

ซึ่งจะทำให้คุณสามารถทำการทดแทนภายในรูปแบบการทดแทนเพื่อการทดแทนขั้นสูงยิ่งขึ้น

## การแทนที่ด้วยสตริง

คุณสามารถแทนที่ข้อความด้วยสตริงธรรมดาได้โดยใช้ Aspose.Words สำหรับ Java

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// แทนที่ข้อความด้วยสตริง
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

ในตัวอย่างนี้ เราแทนที่ "ข้อความที่จะแทนที่" ด้วย "สตริงใหม่" ภายในเอกสาร

## การใช้LegacyOrder

คุณสามารถใช้ลำดับเดิมเมื่อดำเนินการค้นหาและแทนที่

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// สร้างอินสแตนซ์ FindReplaceOptions และตั้งค่า UseLegacyOrder เป็นจริง
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// ใช้ตัวเลือกเมื่อแทนที่ข้อความ
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

ซึ่งจะทำให้คุณสามารถใช้ใบสั่งเดิมสำหรับการดำเนินการค้นหาและแทนที่ได้

## การแทนที่ข้อความในตาราง

คุณสามารถค้นหาและแทนที่ข้อความภายในตารางในเอกสาร Word ของคุณได้

```java
// โหลดเอกสาร
Document doc = new Document("your-document.docx");

// รับตารางเฉพาะ (เช่น ตารางแรก)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// ใช้ FindReplaceOptions เพื่อแทนที่ข้อความในตาราง
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// บันทึกเอกสารที่แก้ไข
doc.save("modified-document.docx");
```

สิ่งนี้ทำให้คุณสามารถทำการแทนที่ข้อความโดยเฉพาะภายในตารางได้

## บทสรุป

Aspose.Words for Java มีความสามารถที่ครอบคลุมในการค้นหาและแทนที่ข้อความภายในเอกสาร Word ไม่ว่าคุณจะต้องทำการแทนที่ข้อความแบบธรรมดาหรือการดำเนินการขั้นสูงโดยใช้นิพจน์ทั่วไป การปรับแต่งฟิลด์ หรือตัวประเมินแบบกำหนดเอง Aspose.Words สำหรับ Java ก็ครอบคลุมทุกอย่างแล้ว อย่าลืมสำรวจเอกสารและตัวอย่างที่ครอบคลุมจาก Aspose เพื่อใช้ประโยชน์จากไลบรารี Java อันทรงพลังนี้อย่างเต็มศักยภาพ

## คำถามที่พบบ่อย

### ฉันจะดาวน์โหลด Aspose.Words สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Words สำหรับ Java ได้จากเว็บไซต์โดยไปที่[ลิงค์นี้](https://releases.aspose.com/words/java/).

### ฉันสามารถใช้นิพจน์ทั่วไปเพื่อแทนที่ข้อความได้หรือไม่

ได้ คุณสามารถใช้นิพจน์ทั่วไปสำหรับการแทนที่ข้อความใน Aspose.Words สำหรับ Java สิ่งนี้ทำให้คุณสามารถดำเนินการค้นหาและแทนที่ขั้นสูงและยืดหยุ่นมากขึ้น

### ฉันจะเพิกเฉยต่อข้อความในช่องระหว่างการเปลี่ยนได้อย่างไร

 หากต้องการละเว้นข้อความภายในช่องระหว่างการแทนที่ คุณสามารถตั้งค่า`IgnoreFields` ทรัพย์สินของ`FindReplaceOptions` ถึง`true`เพื่อให้แน่ใจว่าข้อความภายในฟิลด์ เช่น ฟิลด์ผสาน จะไม่รวมอยู่ในการแทนที่

### ฉันสามารถแทนที่ข้อความภายในส่วนหัวและส่วนท้ายได้หรือไม่

 ได้ คุณสามารถแทนที่ข้อความภายในส่วนหัวและส่วนท้ายของเอกสาร Word ของคุณได้ เพียงเข้าถึงส่วนหัวหรือส่วนท้ายที่เหมาะสมแล้วใช้`replace` ด้วยวิธีที่ต้องการ`FindReplaceOptions`.

### ตัวเลือก UseLegacyOrder มีไว้เพื่ออะไร?

 ที่`UseLegacyOrder` ตัวเลือกใน`FindReplaceOptions` ช่วยให้คุณใช้ลำดับเดิมเมื่อดำเนินการค้นหาและแทนที่ สิ่งนี้อาจมีประโยชน์ในบางสถานการณ์ที่ต้องการลักษณะการทำงานของใบสั่งแบบเดิม