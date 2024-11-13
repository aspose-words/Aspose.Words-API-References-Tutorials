---
title: การสร้างฉลากบาร์โค้ดแบบกำหนดเองใน Aspose.Words สำหรับ Java
linktitle: การสร้างฉลากบาร์โค้ดแบบกำหนดเอง
second_title: API การประมวลผลเอกสาร Java ของ Aspose.Words
description: สร้างฉลากบาร์โค้ดแบบกำหนดเองใน Aspose.Words สำหรับ Java เรียนรู้วิธีสร้างโซลูชันบาร์โค้ดส่วนบุคคลโดยใช้ Aspose.Words สำหรับ Java ในคู่มือทีละขั้นตอนนี้
type: docs
weight: 10
url: /th/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## บทนำสู่การสร้างฉลากบาร์โค้ดแบบกำหนดเองใน Aspose.Words สำหรับ Java

ในคู่มือฉบับสมบูรณ์นี้ เราจะเจาะลึกกระบวนการสร้างฉลากบาร์โค้ดแบบกำหนดเองโดยใช้ Aspose.Words สำหรับ Java Aspose.Words สำหรับ Java เป็น API ที่มีประสิทธิภาพที่ช่วยให้ผู้พัฒนาสามารถจัดการเอกสาร Word ได้ด้วยโปรแกรม คุณลักษณะที่โดดเด่นอย่างหนึ่งคือความสามารถในการทำงานกับฉลากบาร์โค้ด ทำให้เป็นเครื่องมือที่มีประโยชน์สำหรับธุรกิจและองค์กรที่ต้องการโซลูชันบาร์โค้ดแบบกำหนดเอง

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกรายละเอียดของการสร้างฉลากบาร์โค้ดที่กำหนดเอง เรามาแน่ใจก่อนว่าเรามีข้อกำหนดเบื้องต้นแล้ว:

1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java และสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ไว้ในระบบของคุณแล้ว

2.  Aspose.Words สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Words สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/words/java/).

3. ความรู้พื้นฐานเกี่ยวกับ Java: ความคุ้นเคยกับการเขียนโปรแกรม Java จะเป็นประโยชน์เนื่องจากเราจะเขียนโค้ด Java เพื่อสร้างฉลากบาร์โค้ดแบบกำหนดเอง

## การสร้างฉลากบาร์โค้ดแบบกำหนดเอง

ตอนนี้เรามาเริ่มสร้างฉลากบาร์โค้ดแบบกำหนดเองโดยใช้ Aspose.Words สำหรับ Java กัน เราจะแบ่งกระบวนการออกเป็นขั้นตอนต่างๆ และให้ตัวอย่างโค้ด Java สำหรับแต่ละขั้นตอน

## การตั้งค่าความสูงของบาร์โค้ด

ในการเริ่มต้น เราต้องกำหนดความสูงของบาร์โค้ดเป็นหน่วยสองหน่วย (1/1440 นิ้ว) จากนั้นเราจะแปลงค่าดังกล่าวเป็นมิลลิเมตร (mm) นี่คือโค้ดสำหรับทำสิ่งนี้:

```java
	// ค่าอินพุตเป็น 1/1440 นิ้ว (สองนิ้ว)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// แปลงเป็นมิลลิเมตร
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## การแปลงสีภาพบาร์โค้ด

ต่อไปเราจะแปลงสีของภาพบาร์โค้ดจาก Word เป็น Aspose.BarCode สีที่ป้อนควรอยู่ในรูปแบบ "0xRRGGBB" (เลขฐานสิบหก) นี่คือโค้ดสำหรับการแปลง:

```java
/// <สรุป>
/// แปลงสีภาพบาร์โค้ดจาก Word เป็น Aspose.BarCode
/// </สรุป>
/// <param name="inputColor"></param>
/// <กลับ></กลับ>
private static Color convertColor(String inputColor) throws Exception {
	// อินพุตควรเป็นตั้งแต่ "0x000000" ถึง "0xFFFFFF"
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## ปัจจัยการแปลงมาตราส่วนของบาร์โค้ด

ตอนนี้เราจะแปลงค่ามาตราส่วนของบาร์โค้ดจากเปอร์เซ็นต์เป็นค่าทศนิยม ค่ามาตราส่วนนี้จะกำหนดขนาดของบาร์โค้ด นี่คือโค้ดสำหรับการแปลง:

```java
/// <สรุป>
/// แปลงค่ามาตราส่วนของบาร์โค้ดจากเปอร์เซ็นต์เป็นหน่วยลอยตัว
/// </สรุป>
/// <param name="ปัจจัยการปรับขนาด"></param>
/// <กลับ></กลับ>
private static float convertScalingFactor(String scalingFactor) throws Exception {
	boolean isParsed = false;
	int percent = tryParseInt(scalingFactor);
	if (percent != Integer.MIN_VALUE && percent >= 10 && percent <= 10000)
		isParsed = true;
	if (!isParsed)
		throw new Exception("Error! Incorrect scaling factor - " + scalingFactor + ".");
	return percent / 100.0f;
}
```

## การใช้งานเมธอด GetBarCodeImage()

 ในขั้นตอนนี้เราจะดำเนินการ`getBarcodeImage`วิธีการนี้จะสร้างภาพบาร์โค้ดตามพารามิเตอร์ที่ให้มา เราจะจัดการกับบาร์โค้ดประเภทต่างๆ ตั้งค่าสี ปรับขนาด และอื่นๆ อีกมากมาย นี่คือโค้ดสำหรับวิธีการนี้:

```java
/// <สรุป>
/// การใช้งานของวิธี GetBarCodeImage() สำหรับอินเทอร์เฟซ IBarCodeGenerator
/// </สรุป>
/// <param name="พารามิเตอร์"></param>
/// <กลับ></กลับ>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// ตรวจสอบว่ามีการให้ประเภทและค่าของบาร์โค้ดไว้หรือไม่
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// สร้าง BarcodeGenerator โดยอิงตามประเภทบาร์โค้ด
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// จัดการประเภทบาร์โค้ดอื่น ๆ ที่นี่
	}
	
	// ตั้งค่าข้อความบาร์โค้ด
	generator.setCodeText(parameters.getBarcodeValue());
	
	// ตั้งค่าสีบาร์โค้ด
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// ตั้งค่าความสูงและขนาดของสัญลักษณ์
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// ปรับแต่งตำแหน่งข้อความโค้ด
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// การปรับปรุงเพิ่มเติมสำหรับรหัส QR
	final float SCALE = 2.4f; // ปัจจัยการปรับขนาดเชิงประจักษ์สำหรับการแปลงบาร์โค้ด Word เป็น Aspose.BarCode
	float xdim = 1.0f;
	if (generator.getBarcodeType().equals(EncodeTypes.QR))
	{
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NEAREST);
		generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageWidth().getInches() * SCALE);
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageWidth().getInches());
		xdim = generator.getParameters().getImageHeight().getInches() / 25;
		generator.getParameters().getBarcode().getXDimension().setInches(xdim);
		generator.getParameters().getBarcode().getBarHeight().setInches(xdim);
	}
	
	// ใช้ปัจจัยการปรับขนาด
	if (parameters.getScalingFactor() != null)
	{
		float scalingFactor = convertScalingFactor(parameters.getScalingFactor());
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageHeight().getInches() * scalingFactor);
		if (generator.getBarcodeType().equals(EncodeTypes.QR))
		{
			generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageHeight().getInches());
			generator.getParameters().getBarcode().getXDimension().setInches(xdim * scalingFactor);
			generator.getParameters().getBarcode().getBarHeight().setInches(xdim * scalingFactor);
		}
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// สร้างและส่งคืนภาพบาร์โค้ด
	return generator.generateBarCodeImage();
}
```

## การใช้งานวิธี GetOldBarcodeImage()

 ในขั้นตอนนี้เราจะดำเนินการ`getOldBarcodeImage`วิธีการนี้จะสร้างภาพบาร์โค้ดสำหรับบาร์โค้ดแบบเก่า ในที่นี้ เราจะจัดการกับบาร์โค้ดประเภทเฉพาะ เช่น POSTNET นี่คือโค้ดสำหรับวิธีการนี้:

```java
/// <สรุป>
/// การใช้งานวิธี GetOldBarcodeImage() สำหรับอินเทอร์เฟซ IBarCodeGenerator
/// </สรุป>
/// <param name="พารามิเตอร์"></param>
/// <กลับ></กลับ>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// ประเภทฮาร์ดโค้ดสำหรับบาร์โค้ดแบบเก่า
	return generator.generateBarCodeImage();
}
```

## บทสรุป

ในบทความนี้ เราได้สำรวจกระบวนการสร้างฉลากบาร์โค้ดแบบกำหนดเองโดยใช้ Aspose.Words สำหรับ Java เราได้ครอบคลุมขั้นตอนสำคัญต่างๆ ตั้งแต่การกำหนดความสูงของบาร์โค้ดไปจนถึงการใช้เมธอดในการสร้างบาร์โค้ด Aspose.Words สำหรับ Java ช่วยให้ผู้พัฒนาสามารถสร้างฉลากบาร์โค้ดแบบไดนามิกและแบบกำหนดเองได้ ทำให้เป็นเครื่องมือที่มีประโยชน์สำหรับอุตสาหกรรมต่างๆ

## คำถามที่พบบ่อย

### ฉันจะปรับขนาดบาร์โค้ดที่สร้างขึ้นได้อย่างไร

คุณสามารถปรับขนาดของบาร์โค้ดที่สร้างขึ้นได้โดยตั้งค่าความสูงของสัญลักษณ์บาร์โค้ดและปัจจัยการปรับมาตราส่วนในสไนปเป็ตโค้ดที่ให้มา พารามิเตอร์เหล่านี้ช่วยให้คุณควบคุมขนาดของบาร์โค้ดได้ตามความต้องการของคุณ

### ฉันสามารถเปลี่ยนสีบาร์โค้ดได้หรือไม่?

ใช่ คุณสามารถเปลี่ยนสีของบาร์โค้ดได้โดยระบุสีพื้นหน้าและพื้นหลังในรหัส การปรับแต่งนี้ช่วยให้คุณจับคู่รูปลักษณ์ของบาร์โค้ดกับการออกแบบเอกสารของคุณได้

### Aspose.Words สำหรับ Java รองรับประเภทบาร์โค้ดใดบ้าง

Aspose.Words สำหรับ Java รองรับบาร์โค้ดหลายประเภท เช่น รหัส QR, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 และอื่นๆ คุณสามารถเลือกประเภทบาร์โค้ดที่เหมาะกับความต้องการของแอปพลิเคชันของคุณได้

### ฉันจะรวมบาร์โค้ดที่สร้างขึ้นลงในเอกสาร Word ของฉันได้อย่างไร

หากต้องการรวมบาร์โค้ดที่สร้างขึ้นลงในเอกสาร Word ของคุณ คุณสามารถใช้ความสามารถในการจัดการเอกสารของ Aspose.Words สำหรับ Java คุณสามารถแทรกภาพบาร์โค้ดลงในเอกสารของคุณที่ตำแหน่งที่ต้องการได้

### มีโค้ดตัวอย่างสำหรับปรับแต่งเพิ่มเติมหรือไม่

 ใช่ คุณสามารถค้นหาตัวอย่างโค้ดและเอกสารเพิ่มเติมได้จากไซต์อ้างอิง Aspose.Words สำหรับ Java:[เอกสารอ้างอิง API Aspose.Words สำหรับ Java](https://reference.aspose.com/words/java/).