---
title: การบันทึกเอกสารเป็นรูปแบบ OOXML ใน Aspose.Words สำหรับ Java
linktitle: บันทึกเอกสารเป็นรูปแบบ OOXML
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีบันทึกเอกสารในรูปแบบ OOXML ด้วย Aspose.Words สำหรับ Java รักษาความปลอดภัย เพิ่มประสิทธิภาพ และปรับแต่งไฟล์ของคุณได้อย่างง่ายดาย
type: docs
weight: 20
url: /th/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการบันทึกเอกสารเป็นรูปแบบ OOXML ใน Aspose.Words สำหรับ Java

ในคู่มือนี้ เราจะสำรวจวิธีการบันทึกเอกสารในรูปแบบ OOXML โดยใช้ Aspose.Words สำหรับ Java OOXML (Office Open XML) เป็นรูปแบบไฟล์ที่ใช้โดย Microsoft Word และแอปพลิเคชันสำนักงานอื่นๆ เราจะกล่าวถึงตัวเลือกและการตั้งค่าต่างๆ สำหรับการบันทึกเอกสารในรูปแบบ OOXML

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Words สำหรับ Java ในโครงการของคุณแล้ว

## การบันทึกเอกสารด้วยการเข้ารหัสรหัสผ่าน

คุณสามารถเข้ารหัสเอกสารของคุณด้วยรหัสผ่านในขณะที่บันทึกในรูปแบบ OOXML ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// โหลดเอกสาร
Document doc = new Document("Document.docx");

// สร้าง OoxmlSaveOptions และตั้งรหัสผ่าน
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// บันทึกเอกสารด้วยการเข้ารหัส
doc.save("EncryptedDoc.docx", saveOptions);
```

## การตั้งค่าการปฏิบัติตาม OOXML

คุณสามารถระบุระดับการปฏิบัติตามข้อกำหนด OOXML เมื่อบันทึกเอกสาร ตัวอย่างเช่น คุณสามารถตั้งค่าเป็น ISO 29500:2008 (เข้มงวด) มีวิธีดังนี้:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// โหลดเอกสาร
Document doc = new Document("Document.docx");

// ปรับให้เหมาะสมสำหรับ Word 2016
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// สร้าง OoxmlSaveOptions และตั้งค่าระดับการปฏิบัติตามข้อกำหนด
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// บันทึกเอกสารด้วยการตั้งค่าการปฏิบัติตามข้อกำหนด
doc.save("ComplianceDoc.docx", saveOptions);
```

## กำลังอัปเดตคุณสมบัติเวลาที่บันทึกไว้ล่าสุด

คุณสามารถเลือกที่จะอัปเดตคุณสมบัติ "เวลาที่บันทึกไว้ล่าสุด" ของเอกสารได้เมื่อทำการบันทึก มีวิธีดังนี้:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// โหลดเอกสาร
Document doc = new Document("Document.docx");

// สร้าง OoxmlSaveOptions และเปิดใช้งานการอัปเดตคุณสมบัติ Last Saved Time
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// บันทึกเอกสารด้วยคุณสมบัติที่อัปเดต
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## การรักษาอักขระควบคุมแบบเดิม

หากเอกสารของคุณมีอักขระควบคุมแบบเดิม คุณสามารถเลือกที่จะเก็บไว้ในขณะที่บันทึกได้ มีวิธีดังนี้:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

// โหลดเอกสารที่มีอักขระควบคุมแบบเดิม
Document doc = new Document("LegacyControlChars.doc");

//สร้าง OoxmlSaveOptions ด้วยรูปแบบ FLAT_OPC และเปิดใช้งานการรักษาอักขระควบคุมแบบเดิม
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// บันทึกเอกสารด้วยอักขระควบคุมแบบเดิม
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## การตั้งค่าระดับการบีบอัด

คุณสามารถปรับระดับการบีบอัดได้เมื่อบันทึกเอกสาร ตัวอย่างเช่น คุณสามารถตั้งค่าเป็น SUPER_FAST เพื่อการบีบอัดที่น้อยที่สุด มีวิธีดังนี้:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// โหลดเอกสาร
Document doc = new Document("Document.docx");

// สร้าง OoxmlSaveOptions และตั้งค่าระดับการบีบอัด
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// บันทึกเอกสารตามระดับการบีบอัดที่ระบุ
doc.save("FastCompressionDoc.docx", saveOptions);
```

นี่คือตัวเลือกและการตั้งค่าหลักบางส่วนที่คุณสามารถใช้เมื่อบันทึกเอกสารในรูปแบบ OOXML โดยใช้ Aspose.Words สำหรับ Java สำรวจตัวเลือกเพิ่มเติมและปรับแต่งกระบวนการบันทึกเอกสารได้ตามต้องการ

## กรอกซอร์สโค้ดสำหรับการบันทึกเอกสารเป็นรูปแบบ OOXML ใน Aspose.Words สำหรับ Java

```java
public void encryptDocxWithPassword() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
}
@Test
public void ooxmlComplianceIso29500_2008_Strict() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
}
@Test
public void updateLastSavedTimeProperty() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
}
@Test
public void keepLegacyControlChars() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Legacy control character.doc");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC); { saveOptions.setKeepLegacyControlChars(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
}
@Test
public void setCompressionLevel() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
}
```

## บทสรุป

ในคู่มือที่ครอบคลุมนี้ เราได้สำรวจวิธีการบันทึกเอกสารในรูปแบบ OOXML โดยใช้ Aspose.Words สำหรับ Java ไม่ว่าคุณจะต้องเข้ารหัสเอกสารของคุณด้วยรหัสผ่าน ตรวจสอบให้แน่ใจว่าเป็นไปตามมาตรฐาน OOXML เฉพาะ อัปเดตคุณสมบัติของเอกสาร รักษาอักขระควบคุมแบบเดิม หรือปรับระดับการบีบอัด Aspose.Words มีชุดเครื่องมืออเนกประสงค์ที่ตรงกับความต้องการของคุณ

## คำถามที่พบบ่อย

### ฉันจะลบการป้องกันด้วยรหัสผ่านออกจากเอกสารที่มีการป้องกันด้วยรหัสผ่านได้อย่างไร

หากต้องการลบการป้องกันด้วยรหัสผ่านออกจากเอกสารที่มีการป้องกันด้วยรหัสผ่าน คุณสามารถเปิดเอกสารด้วยรหัสผ่านที่ถูกต้อง จากนั้นบันทึกโดยไม่ต้องระบุรหัสผ่านในตัวเลือกการบันทึก การดำเนินการนี้จะบันทึกเอกสารโดยไม่มีการป้องกันด้วยรหัสผ่าน

### ฉันสามารถตั้งค่าคุณสมบัติแบบกำหนดเองเมื่อบันทึกเอกสารในรูปแบบ OOXML ได้หรือไม่

 ได้ คุณสามารถตั้งค่าคุณสมบัติแบบกำหนดเองสำหรับเอกสารก่อนที่จะบันทึกในรูปแบบ OOXML ใช้`BuiltInDocumentProperties`และ`CustomDocumentProperties` คลาสเพื่อตั้งค่าคุณสมบัติต่างๆ เช่น ผู้แต่ง ชื่อเรื่อง คำสำคัญ และคุณสมบัติที่กำหนดเอง

### ระดับการบีบอัดเริ่มต้นเมื่อบันทึกเอกสารในรูปแบบ OOXML คืออะไร

 ระดับการบีบอัดเริ่มต้นเมื่อบันทึกเอกสารในรูปแบบ OOXML โดยใช้ Aspose.Words สำหรับ Java คือ`NORMAL` - คุณสามารถเปลี่ยนระดับการบีบอัดเป็น`SUPER_FAST` หรือ`MAXIMUM` ตามความจำเป็น