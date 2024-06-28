---
title: การใช้ตัวเลือกการโหลดใน Aspose.Words สำหรับ Java
linktitle: การใช้ตัวเลือกการโหลด
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: การเรียนรู้ตัวเลือกการโหลดใน Aspose.Words สำหรับ Java ปรับแต่งการโหลดเอกสาร จัดการการเข้ารหัส แปลงรูปร่าง ตั้งค่าเวอร์ชัน Word และอื่นๆ เพื่อการประมวลผลเอกสาร Java ที่มีประสิทธิภาพ
type: docs
weight: 11
url: /th/java/document-loading-and-saving/using-load-options/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการทำงานกับตัวเลือกการโหลดใน Aspose.Words สำหรับ Java

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับตัวเลือกการโหลดใน Aspose.Words สำหรับ Java ตัวเลือกการโหลดช่วยให้คุณสามารถปรับแต่งวิธีการโหลดและประมวลผลเอกสารได้ เราจะครอบคลุมสถานการณ์ต่างๆ รวมถึงการอัปเดตฟิลด์สกปรก การโหลดเอกสารที่เข้ารหัส การแปลงรูปร่างเป็น Office Math การตั้งค่าเวอร์ชัน MS Word การระบุโฟลเดอร์ชั่วคราว การจัดการคำเตือน และการแปลงเมตาไฟล์เป็น PNG มาดำน้ำกันทีละขั้นตอน

## อัปเดตฟิลด์สกปรก

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setUpdateDirtyFields(true);

Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

 ข้อมูลโค้ดนี้สาธิตวิธีอัปเดตฟิลด์สกปรกในเอกสาร ที่`setUpdateDirtyFields(true)` วิธีการนี้ใช้เพื่อให้แน่ใจว่าฟิลด์สกปรกได้รับการอัปเดตระหว่างการโหลดเอกสาร

## โหลดเอกสารที่เข้ารหัส

```java
@Test
public void loadEncryptedDocument() throws Exception {
    Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
```

 ที่นี่ เราโหลดเอกสารที่เข้ารหัสโดยใช้รหัสผ่าน ที่`LoadOptions` ตัวสร้างยอมรับรหัสผ่านเอกสาร และคุณยังสามารถระบุรหัสผ่านใหม่เมื่อบันทึกเอกสารโดยใช้`OdtSaveOptions`.

## แปลงรูปร่างเป็น Office Math

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setConvertShapeToOfficeMath(true);

Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
```

 รหัสนี้สาธิตวิธีการแปลงรูปร่างเป็นวัตถุ Office Math ในระหว่างการโหลดเอกสาร ที่`setConvertShapeToOfficeMath(true)`วิธีการเปิดใช้งานการแปลงนี้

## ตั้งค่าเวอร์ชัน MS Word

```java
@Test
public void setMsWordVersion() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setMswVersion(MsWordVersion.WORD_2010);

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
```

 คุณสามารถระบุเวอร์ชัน MS Word สำหรับการโหลดเอกสารได้ ในตัวอย่างนี้ เราตั้งค่าเวอร์ชันเป็น Microsoft Word 2010 โดยใช้`setMswVersion`.

## ใช้โฟลเดอร์ชั่วคราว

```java
@Test
public void useTempFolder() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setTempFolder("Your Directory Path");

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
```

 โดยการตั้งค่าโฟลเดอร์ชั่วคราวโดยใช้`setTempFolder`คุณสามารถควบคุมตำแหน่งที่จะจัดเก็บไฟล์ชั่วคราวระหว่างการประมวลผลเอกสารได้

## คำเตือน โทรกลับ

```java
@Test
public void warningCallback() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}

public static class DocumentLoadingWarningCallback implements IWarningCallback {
    public void warning(WarningInfo info) {
        // จัดการคำเตือนที่เกิดขึ้นระหว่างการโหลดเอกสาร
        System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
        System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
    }
}
```

รหัสนี้สาธิตวิธีตั้งค่าการโทรกลับคำเตือนเพื่อจัดการคำเตือนระหว่างการโหลดเอกสาร คุณสามารถปรับแต่งลักษณะการทำงานของแอปพลิเคชันของคุณเมื่อมีคำเตือนเกิดขึ้น

## แปลง Metafiles เป็น PNG

```java
@Test
public void convertMetafilesToPng() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setConvertMetafilesToPng(true);

    Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
```

 หากต้องการแปลงไฟล์เมตา (เช่น WMF) เป็นรูปภาพ PNG ในระหว่างการโหลดเอกสาร คุณสามารถใช้ไฟล์`setConvertMetafilesToPng(true)` วิธี.

## กรอกซอร์สโค้ดสำหรับการทำงานกับตัวเลือกโหลดใน Aspose.Words สำหรับ Java

```java
public void updateDirtyFields() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setUpdateDirtyFields(true);
	}
	Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
}
@Test
public void loadEncryptedDocument() throws Exception {
	Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
@Test
public void convertShapeToOfficeMath() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertShapeToOfficeMath(true);
	}
	Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
}
@Test
public void setMsWordVersion() throws Exception {
	// สร้างวัตถุ LoadOptions ใหม่ ซึ่งจะโหลดเอกสารตามข้อกำหนด MS Word 2019 เป็นค่าเริ่มต้น
	// และเปลี่ยนเวอร์ชั่นโหลดเป็น Microsoft Word 2010
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setMswVersion(MsWordVersion.WORD_2010);
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
@Test
public void useTempFolder() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setTempFolder("Your Directory Path");
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
@Test
public void warningCallback() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
public static class DocumentLoadingWarningCallback implements IWarningCallback {
	public void warning(WarningInfo info) {
		//พิมพ์คำเตือนและรายละเอียดที่เกิดขึ้นระหว่างการโหลดเอกสาร
		System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
		System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
	}
}
@Test
public void convertMetafilesToPng() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertMetafilesToPng(true);
	}
	Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
@Test
public void loadChm() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setEncoding(Charset.forName("windows-1251"));
	}
	Document doc = new Document("Your Directory Path" + "HTML help.chm", loadOptions);
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เจาะลึกแง่มุมต่างๆ ของการทำงานกับตัวเลือกการโหลดใน Aspose.Words สำหรับ Java ตัวเลือกการโหลดมีบทบาทสำคัญในการปรับแต่งวิธีการโหลดและประมวลผลเอกสาร ซึ่งช่วยให้คุณปรับแต่งการประมวลผลเอกสารให้ตรงตามความต้องการเฉพาะของคุณได้ มาสรุปประเด็นสำคัญที่กล่าวถึงในคู่มือนี้กัน:

## คำถามที่พบบ่อย

### ฉันจะจัดการคำเตือนระหว่างการโหลดเอกสารได้อย่างไร

 คุณสามารถตั้งค่าการแจ้งเตือนการโทรกลับได้ตามที่แสดงใน`warningCallback()` วิธีการข้างต้น ปรับแต่ง`DocumentLoadingWarningCallback` คลาสเพื่อจัดการคำเตือนตามความต้องการของแอปพลิเคชันของคุณ

### ฉันสามารถแปลงรูปร่างเป็นวัตถุ Office Math เมื่อโหลดเอกสารได้หรือไม่

 ใช่ คุณสามารถแปลงรูปร่างเป็นวัตถุ Office Math ได้โดยใช้`loadOptions.setConvertShapeToOfficeMath(true)`.

### ฉันจะระบุเวอร์ชัน MS Word สำหรับการโหลดเอกสารได้อย่างไร

 ใช้`loadOptions.setMswVersion(MsWordVersion.WORD_2010)` เพื่อระบุเวอร์ชัน MS Word สำหรับการโหลดเอกสาร

###  จุดประสงค์ของ..คืออะไร.`setTempFolder` method in Load Options?

 ที่`setTempFolder`วิธีการช่วยให้คุณระบุโฟลเดอร์ที่เก็บไฟล์ชั่วคราวระหว่างการประมวลผลเอกสาร