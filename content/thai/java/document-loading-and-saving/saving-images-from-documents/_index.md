---
title: การบันทึกรูปภาพจากเอกสารใน Aspose.Words สำหรับ Java
linktitle: การบันทึกภาพจากเอกสาร
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีบันทึกรูปภาพจากเอกสารโดยใช้ Aspose.Words สำหรับ Java พร้อมคำแนะนำทีละขั้นตอนที่ครอบคลุมของเรา ปรับแต่งรูปแบบ การบีบอัด และอื่นๆ
type: docs
weight: 17
url: /th/java/document-loading-and-saving/saving-images-from-documents/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการบันทึกรูปภาพจากเอกสารใน Aspose.Words สำหรับ Java

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการบันทึกรูปภาพจากเอกสารโดยใช้ Aspose.Words สำหรับ Java เราจะครอบคลุมสถานการณ์ต่างๆ และตัวเลือกการปรับแต่งสำหรับการบันทึกรูปภาพ คู่มือนี้ให้คำแนะนำทีละขั้นตอนพร้อมตัวอย่างซอร์สโค้ด

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Words สำหรับ Java เข้ากับโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/java/).

## ขั้นตอนที่ 1: บันทึกรูปภาพเป็น TIFF พร้อมการควบคุมเกณฑ์

หากต้องการบันทึกรูปภาพเป็นรูปแบบ TIFF พร้อมการควบคุมเกณฑ์ ให้ทำตามขั้นตอนเหล่านี้:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
doc.save("Your Directory Path" + "ThresholdControlledImage.tiff", saveOptions);
```

## ขั้นตอนที่ 2: บันทึกหน้าเฉพาะเป็น TIFF หลายหน้า

หากต้องการบันทึกหน้าใดหน้าหนึ่งเป็น TIFF หลายหน้า ให้ใช้รหัสต่อไปนี้:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setPageSet(new PageSet(new PageRange(0, 1)));
saveOptions.setTiffCompression(TiffCompression.CCITT_4);
saveOptions.setResolution(160f);
doc.save("Your Directory Path" + "SpecificPageMultipage.tiff", saveOptions);
```

## ขั้นตอนที่ 3: บันทึกรูปภาพเป็น 1 PNG ที่จัดทำดัชนี BPP

หากต้องการบันทึกรูปภาพเป็น PNG ที่จัดทำดัชนี BPP 1 รายการ ให้ทำตามขั้นตอนเหล่านี้:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(1));
saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
doc.save("Your Directory Path" + "1BPPIndexed.png", saveOptions);
```

## ขั้นตอนที่ 4: บันทึกเพจเป็น JPEG พร้อมการปรับแต่ง

หากต้องการบันทึกหน้าเฉพาะเป็น JPEG พร้อมตัวเลือกการปรับแต่ง ให้ใช้รหัสนี้:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
options.setPageSet(new PageSet(0));
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
options.setHorizontalResolution(72f);
doc.save("Your Directory Path" + "CustomizedJPEG.jpeg", options);
```

## ขั้นตอนที่ 5: การใช้การโทรกลับการบันทึกหน้า

คุณสามารถใช้การโทรกลับเพื่อปรับแต่งการบันทึกหน้าได้ นี่คือตัวอย่าง:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.PNG);
imageSaveOptions.setPageSet(new PageSet(new PageRange(0, doc.getPageCount() - 1)));
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
doc.save("Your Directory Path" + "PageSavingCallback.png", imageSaveOptions);
```

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```

## กรอกซอร์สโค้ดสำหรับการบันทึกรูปภาพจากเอกสารใน Aspose.Words สำหรับ Java

```java
public void exposeThresholdControlForTiffBinarization() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
	{
		saveOptions.setTiffCompression(TiffCompression.CCITT_3);
		saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
		saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
		saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
}
@Test
public void getTiffPageRange() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
	{
		saveOptions.setPageSet(new PageSet(new PageRange(0, 1))); saveOptions.setTiffCompression(TiffCompression.CCITT_4); saveOptions.setResolution(160f);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
}
@Test
public void format1BppIndexed() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
	{
		saveOptions.setPageSet(new PageSet(1));
		saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
		saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
}
@Test
public void getJpegPageRange() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
	// ตั้งค่า "PageSet" เป็น "0" เพื่อแปลงเฉพาะหน้าแรกของเอกสาร
	options.setPageSet(new PageSet(0));
	// เปลี่ยนความสว่างและความคมชัดของภาพ
	// ทั้งคู่อยู่ในระดับ 0-1 และอยู่ที่ 0.5 ตามค่าเริ่มต้น
	options.setImageBrightness(0.3f);
	options.setImageContrast(0.7f);
	// เปลี่ยนความละเอียดแนวนอน
	// ค่าเริ่มต้นสำหรับคุณสมบัติเหล่านี้คือ 96.0 สำหรับความละเอียด 96dpi
	options.setHorizontalResolution(72f);
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
}
@Test
public static void pageSavingCallback() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.PNG);
	{
		imageSaveOptions.setPageSet(new PageSet(new PageRange(0, doc.getPageCount() - 1)));
		imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
}
private static class HandlePageSavingCallback implements IPageSavingCallback
{
	public void pageSaving(PageSavingArgs args)
	{
		args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
	}
```

## บทสรุป

คุณได้เรียนรู้วิธีบันทึกรูปภาพจากเอกสารโดยใช้ Aspose.Words สำหรับ Java แล้ว ตัวอย่างเหล่านี้สาธิตตัวเลือกการปรับแต่งต่างๆ สำหรับการบันทึกภาพ รวมถึงรูปแบบ การบีบอัด และการใช้งานการโทรกลับ สำรวจความเป็นไปได้มากขึ้นด้วย Aspose.Words สำหรับความสามารถอันทรงพลังของ Java

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนรูปแบบภาพเมื่อบันทึกด้วย Aspose.Words สำหรับ Java ได้อย่างไร

 คุณสามารถเปลี่ยนรูปแบบภาพได้โดยระบุรูปแบบที่ต้องการใน`ImageSaveOptions` - เช่น หากต้องการบันทึกเป็น PNG ให้ใช้`SaveFormat.PNG` ดังแสดงในรหัส:

```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
```

### ฉันสามารถปรับแต่งการตั้งค่าการบีบอัดสำหรับภาพ TIFF ได้หรือไม่

ใช่ คุณสามารถปรับแต่งการตั้งค่าการบีบอัดภาพ TIFF ได้ ตัวอย่างเช่น เมื่อต้องการตั้งค่าวิธีการบีบอัดเป็น CCITT_3 ให้ใช้รหัสต่อไปนี้:

```java
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
```

### ฉันจะบันทึกหน้าใดหน้าหนึ่งจากเอกสารเป็นรูปภาพแยกต่างหากได้อย่างไร

 หากต้องการบันทึกหน้าใดหน้าหนึ่งเป็นรูปภาพ ให้ใช้`setPageSet`วิธีการใน`ImageSaveOptions` - ตัวอย่างเช่น หากต้องการบันทึกเฉพาะหน้าแรก ให้ตั้งค่า`PageSet` ถึง`new PageSet(0)`.

```java
saveOptions.setPageSet(new PageSet(0)); // บันทึกหน้าแรกเป็นรูปภาพ
```

### ฉันจะใช้การตั้งค่าแบบกำหนดเองกับภาพ JPEG เมื่อบันทึกได้อย่างไร

คุณสามารถใช้การตั้งค่าแบบกำหนดเองกับภาพ JPEG ได้โดยใช้`ImageSaveOptions`- ปรับคุณสมบัติ เช่น ความสว่าง คอนทราสต์ และความละเอียด ตัวอย่างเช่น หากต้องการเปลี่ยนความสว่างเป็น 0.3 และคอนทราสต์เป็น 0.7 ให้ใช้โค้ดนี้:

```java
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
```

### ฉันจะใช้การโทรกลับเพื่อปรับแต่งการบันทึกรูปภาพได้อย่างไร

 หากต้องการใช้การโทรกลับเพื่อปรับแต่งการบันทึกรูปภาพ ให้ตั้งค่า`PageSavingCallback` ใน`ImageSaveOptions` - สร้างคลาสที่ใช้`IPageSavingCallback` อินเทอร์เฟซและแทนที่ไฟล์`pageSaving` วิธี.

```java
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
```

 จากนั้นสร้างคลาสที่ใช้`IPageSavingCallback` อินเตอร์เฟซและปรับแต่งชื่อไฟล์และตำแหน่งใน`pageSaving` วิธี.

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```