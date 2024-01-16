---
title: การบันทึกเอกสาร HTML ด้วยเค้าโครงคงที่ใน Aspose.Words สำหรับ Java
linktitle: การบันทึกเอกสาร HTML ด้วยเค้าโครงคงที่
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีบันทึกเอกสาร HTML ด้วยเค้าโครงคงที่ใน Aspose.Words สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดรูปแบบเอกสารที่ราบรื่น
type: docs
weight: 15
url: /th/java/document-loading-and-saving/saving-html-documents-with-fixed-layout/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการบันทึกเอกสาร HTML ด้วยเค้าโครงคงที่ใน Aspose.Words สำหรับ Java

ในคู่มือที่ครอบคลุมนี้ เราจะแนะนำคุณตลอดขั้นตอนการบันทึกเอกสาร HTML ด้วยเลย์เอาต์คงที่โดยใช้ Aspose.Words สำหรับ Java ด้วยคำแนะนำทีละขั้นตอนและตัวอย่างโค้ด คุณจะได้เรียนรู้วิธีการบรรลุเป้าหมายนี้ได้อย่างราบรื่น เอาล่ะ มาดำดิ่งกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ตั้งค่าสภาพแวดล้อมการพัฒนา Java
- ติดตั้งและกำหนดค่า Aspose.Words สำหรับไลบรารี Java แล้ว

## ขั้นตอนที่ 1: การโหลดเอกสาร

ขั้นแรก เราต้องโหลดเอกสารที่เราต้องการบันทึกในรูปแบบ HTML ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
Document doc = new Document("Your Directory Path" + "YourDocument.docx");
```

 แทนที่`"YourDocument.docx"` พร้อมเส้นทางไปยังเอกสาร Word ของคุณ

## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการบันทึกคงที่ HTML

 หากต้องการบันทึกเอกสารด้วยรูปแบบคงที่ เราจำเป็นต้องกำหนดค่า`HtmlFixedSaveOptions` ระดับ. เราจะตั้งค่า`useTargetMachineFonts`ทรัพย์สินเพื่อ`true` เพื่อให้แน่ใจว่าแบบอักษรของเครื่องเป้าหมายถูกใช้ในเอาต์พุต HTML:

```java
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions();
saveOptions.setUseTargetMachineFonts(true);
```

## ขั้นตอนที่ 3: บันทึกเอกสารเป็น HTML

ตอนนี้ มาบันทึกเอกสารเป็น HTML ด้วยเค้าโครงคงที่โดยใช้ตัวเลือกที่กำหนดค่าไว้ก่อนหน้านี้:

```java
doc.save("Your Directory Path" + "FixedLayoutDocument.html", saveOptions);
```

 แทนที่`"FixedLayoutDocument.html"` ด้วยชื่อที่ต้องการสำหรับไฟล์ HTML ของคุณ

## กรอกซอร์สโค้ดสำหรับการบันทึกเอกสาร HTML ด้วยเค้าโครงคงที่ใน Aspose.Words สำหรับ Java

```java
        Document doc = new Document("Your Directory Path" + "Bullet points with alternative font.docx");
        HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions();
        {
            saveOptions.setUseTargetMachineFonts(true);
        }
        doc.save("Your Directory Path" + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
    }
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีบันทึกเอกสาร HTML ด้วยเลย์เอาต์คงที่โดยใช้ Aspose.Words สำหรับ Java ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถมั่นใจได้ว่าเอกสารของคุณรักษาโครงสร้างภาพที่สอดคล้องกันบนแพลตฟอร์มต่างๆ

## คำถามที่พบบ่อย

### ฉันจะตั้งค่า Aspose.Words สำหรับ Java ในโปรเจ็กต์ของฉันได้อย่างไร

 การตั้งค่า Aspose.Words สำหรับ Java นั้นตรงไปตรงมา คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/words/java/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบ[ที่นี่](https://reference.aspose.com/words/java/).

### มีข้อกำหนดสิทธิ์การใช้งานสำหรับการใช้ Aspose.Words สำหรับ Java หรือไม่

ใช่ Aspose.Words สำหรับ Java ต้องมีใบอนุญาตที่ถูกต้องเพื่อใช้ในสภาพแวดล้อมการใช้งานจริง คุณสามารถขอรับใบอนุญาตได้จากเว็บไซต์ Aspose รายละเอียดเพิ่มเติมสามารถพบได้ในเอกสารประกอบ

### ฉันสามารถปรับแต่งเอาต์พุต HTML เพิ่มเติมได้หรือไม่

แน่นอน! Aspose.Words for Java มีตัวเลือกมากมายสำหรับการปรับแต่งเอาต์พุต HTML ให้ตรงตามความต้องการเฉพาะของคุณ คุณสามารถสำรวจเอกสารประกอบเพื่อดูข้อมูลโดยละเอียดเกี่ยวกับตัวเลือกการปรับแต่งได้

### Aspose.Words สำหรับ Java เข้ากันได้กับ Java เวอร์ชันต่างๆ หรือไม่

ใช่ Aspose.Words สำหรับ Java เข้ากันได้กับ Java เวอร์ชันต่างๆ ตรวจสอบให้แน่ใจว่าคุณใช้ Aspose.Words สำหรับ Java เวอร์ชันที่เข้ากันได้ซึ่งตรงกับสภาพแวดล้อมการพัฒนา Java ของคุณ