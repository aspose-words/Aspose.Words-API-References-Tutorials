---
title: การบันทึกเอกสารเป็นไฟล์ข้อความใน Aspose.Words สำหรับ Java
linktitle: การบันทึกเอกสารเป็นไฟล์ข้อความ
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีบันทึกเอกสารเป็นไฟล์ข้อความใน Aspose.Words สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด Java
type: docs
weight: 24
url: /th/java/document-loading-and-saving/saving-documents-as-text-files/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการบันทึกเอกสารเป็นไฟล์ข้อความใน Aspose.Words สำหรับ Java

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการบันทึกเอกสารเป็นไฟล์ข้อความโดยใช้ไลบรารี Aspose.Words สำหรับ Java Aspose.Words เป็น Java API ที่ทรงพลังสำหรับการทำงานกับเอกสาร Word และมีตัวเลือกมากมายสำหรับการบันทึกเอกสารในรูปแบบต่าง ๆ รวมถึงข้อความธรรมดา เราจะอธิบายขั้นตอนต่างๆ เพื่อให้บรรลุเป้าหมายนี้ และจัดเตรียมโค้ด Java ตัวอย่างไปพร้อมกัน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Words สำหรับไลบรารี Java ที่ผสานรวมเข้ากับโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/java/).
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java

## ขั้นตอนที่ 1: สร้างเอกสาร

หากต้องการบันทึกเอกสารเป็นไฟล์ข้อความ เราต้องสร้างเอกสารโดยใช้ Aspose.Words ก่อน ต่อไปนี้คือตัวอย่างโค้ด Java ง่ายๆ เพื่อสร้างเอกสารที่มีเนื้อหาบางส่วน:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

ในโค้ดนี้ เราสร้างเอกสารใหม่และเพิ่มข้อความ รวมถึงข้อความในภาษาต่างๆ

## ขั้นตอนที่ 2: กำหนดตัวเลือกการบันทึกข้อความ

ต่อไปเราต้องกำหนดตัวเลือกการบันทึกข้อความที่ระบุวิธีการบันทึกเอกสารเป็นไฟล์ข้อความ เราสามารถกำหนดการตั้งค่าต่างๆ ได้ เช่น การเพิ่มเครื่องหมาย bidi การระบุรายการ และอื่นๆ ลองดูสองตัวอย่าง:

### ตัวอย่างที่ 1: การเพิ่มเครื่องหมาย Bidi

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 ในตัวอย่างนี้ เราสร้าง a`TxtSaveOptions` วัตถุและตั้งค่า`AddBidiMarks`ทรัพย์สินเพื่อ`true` หากต้องการรวมเครื่องหมาย bidi ในเอาต์พุตข้อความ

### ตัวอย่างที่ 2: การใช้อักขระแท็บสำหรับการเยื้องรายการ

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

ที่นี่ เรากำหนดค่าตัวเลือกการบันทึกเพื่อใช้อักขระแท็บเพื่อระบุรายการด้วยการนับ 1

## ขั้นตอนที่ 3: บันทึกเอกสารเป็นข้อความ

ตอนนี้เราได้กำหนดตัวเลือกการบันทึกข้อความแล้ว เราก็สามารถบันทึกเอกสารเป็นไฟล์ข้อความได้ รหัสต่อไปนี้สาธิตวิธีการทำเช่นนี้:

```java
doc.save("output.txt", saveOptions);
```

 แทนที่`"output.txt"` ด้วยเส้นทางไฟล์ที่ต้องการซึ่งคุณต้องการบันทึกไฟล์ข้อความ

## กรอกซอร์สโค้ดสำหรับการบันทึกเอกสารเป็นไฟล์ข้อความใน Aspose.Words สำหรับ Java

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // สร้างรายการที่มีการระบุตัวตนสามระดับ
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // สร้างรายการที่มีการระบุตัวตนสามระดับ
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีบันทึกเอกสารเป็นไฟล์ข้อความใน Aspose.Words สำหรับ Java เราได้กล่าวถึงขั้นตอนต่างๆ ในการสร้างเอกสาร กำหนดตัวเลือกการบันทึกข้อความ และบันทึกเอกสารในรูปแบบข้อความ Aspose.Words มอบความยืดหยุ่นอย่างกว้างขวางในการบันทึกเอกสาร ซึ่งช่วยให้คุณปรับแต่งผลลัพธ์ให้ตรงกับความต้องการเฉพาะของคุณได้

## คำถามที่พบบ่อย

### ฉันจะเพิ่มเครื่องหมาย bidi ลงในเอาต์พุตข้อความได้อย่างไร

 หากต้องการเพิ่มเครื่องหมาย bidi ให้กับเอาต์พุตข้อความ ให้ตั้งค่า`AddBidiMarks` ทรัพย์สินของ`TxtSaveOptions` ถึง`true`- ตัวอย่างเช่น:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### ฉันสามารถปรับแต่งการระบุอักขระรายการได้หรือไม่

 ใช่ คุณสามารถปรับแต่งอักขระการเยื้องรายการได้โดยการกำหนดค่า`ListIndentation` ทรัพย์สินของ`TxtSaveOptions`- ตัวอย่างเช่น เมื่อต้องการใช้อักขระแท็บสำหรับการเยื้องรายการ คุณสามารถทำสิ่งต่อไปนี้:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Aspose.Words สำหรับ Java เหมาะสำหรับการจัดการข้อความหลายภาษาหรือไม่

ใช่ Aspose.Words สำหรับ Java เหมาะสำหรับการจัดการข้อความหลายภาษา รองรับภาษาและการเข้ารหัสอักขระที่หลากหลาย ทำให้เป็นตัวเลือกที่หลากหลายสำหรับการทำงานกับเอกสารในภาษาต่างๆ

### ฉันจะเข้าถึงเอกสารและทรัพยากรเพิ่มเติมสำหรับ Aspose.Words สำหรับ Java ได้อย่างไร

 คุณสามารถค้นหาเอกสารและทรัพยากรที่ครอบคลุมสำหรับ Aspose.Words สำหรับ Java บนเว็บไซต์เอกสารประกอบของ Aspose:[Aspose.Words สำหรับเอกสาร Java](https://reference.aspose.com/words/java/).

### ฉันจะดาวน์โหลด Aspose.Words สำหรับ Java ได้ที่ไหน

 คุณสามารถดาวน์โหลดไลบรารี Aspose.Words สำหรับ Java ได้จากเว็บไซต์ Aspose:[ดาวน์โหลด Aspose.Words สำหรับ Java](https://releases.aspose.com/words/java/).