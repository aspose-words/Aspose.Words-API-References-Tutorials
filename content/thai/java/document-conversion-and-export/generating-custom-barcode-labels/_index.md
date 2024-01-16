---
title: การสร้างฉลากบาร์โค้ดที่กำหนดเองใน Aspose.Words สำหรับ Java
linktitle: การสร้างฉลากบาร์โค้ดแบบกำหนดเอง
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: สร้างฉลากบาร์โค้ดที่กำหนดเองใน Aspose.Words สำหรับ Java เรียนรู้วิธีสร้างโซลูชันบาร์โค้ดส่วนบุคคลโดยใช้ Aspose.Words สำหรับ Java ในคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 10
url: /th/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการสร้างฉลากบาร์โค้ดแบบกำหนดเองใน Aspose.Words สำหรับ Java

ในคู่มือที่ครอบคลุมนี้ เราจะเจาะลึกกระบวนการสร้างฉลากบาร์โค้ดแบบกำหนดเองโดยใช้ Aspose.Words สำหรับ Java Aspose.Words สำหรับ Java เป็น API ที่ทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการเอกสาร Word โดยทางโปรแกรมได้ คุณสมบัติที่โดดเด่นประการหนึ่งคือความสามารถในการทำงานกับฉลากบาร์โค้ด ทำให้เป็นเครื่องมือที่มีค่าสำหรับธุรกิจและองค์กรที่ต้องการโซลูชันบาร์โค้ดที่ปรับแต่งได้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกรายละเอียดของการสร้างฉลากบาร์โค้ดแบบกำหนดเอง เราต้องแน่ใจว่าเรามีข้อกำหนดเบื้องต้นดังนี้:

1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java และ Integrated Development Environment (IDE) บนระบบของคุณ

2.  Aspose.Words สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Words สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/words/java/).

3. ความรู้พื้นฐานของ Java: ความคุ้นเคยกับการเขียนโปรแกรม Java จะเป็นประโยชน์ เนื่องจากเราจะเขียนโค้ด Java เพื่อสร้างฉลากบาร์โค้ดแบบกำหนดเอง

## การสร้างฉลากบาร์โค้ดแบบกำหนดเอง

ตอนนี้ เรามาเริ่มสร้างฉลากบาร์โค้ดแบบกำหนดเองโดยใช้ Aspose.Words สำหรับ Java กันดีกว่า เราจะแบ่งกระบวนการออกเป็นขั้นตอนและจัดเตรียมข้อมูลโค้ด Java สำหรับแต่ละขั้นตอน

## การตั้งค่าความสูงของบาร์โค้ด

ในการเริ่มต้น เราต้องตั้งค่าความสูงของบาร์โค้ดเป็น 2 เท่า (1/1440 นิ้ว) จากนั้นเราจะแปลงค่านี้เป็นมิลลิเมตร (mm) นี่คือรหัสเพื่อทำสิ่งนี้ให้สำเร็จ:

```java
	// ค่าอินพุตเป็น 1/1440 นิ้ว (twips)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// แปลงเป็นมม
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## การแปลงสีของภาพบาร์โค้ด

ต่อไป เราจะแปลงสีของภาพบาร์โค้ดจาก Word เป็น Aspose.BarCode สีที่ป้อนควรอยู่ในรูปแบบ "0xRRGGBB" (เลขฐานสิบหก) นี่คือรหัสสำหรับการแปลง:

```java
/// <สรุป>
/// แปลงสีของภาพบาร์โค้ดจาก Word เป็น Aspose.BarCode
/// </สรุป>
/// <ชื่อพารามิเตอร์="inputColor"></param>
/// <ผลตอบแทน</ผลตอบแทน>
private static Color convertColor(String inputColor) throws Exception {
	// อินพุตควรอยู่ระหว่าง "0x000000" ถึง "0xFFFFFF"
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## การแปลงปัจจัยมาตราส่วนบาร์โค้ด

ตอนนี้ เราจะแปลงปัจจัยมาตราส่วนบาร์โค้ดจากเปอร์เซ็นต์เป็นค่าทศนิยม ปัจจัยมาตราส่วนนี้จะกำหนดขนาดของบาร์โค้ด นี่คือรหัสสำหรับการแปลง:

```java
/// <สรุป>
/// แปลงตัวคูณมาตราส่วนของบาร์โค้ดจากเปอร์เซ็นต์เป็นแบบลอยตัว
/// </สรุป>
/// <param name="scalingFactor"></param>
/// <ผลตอบแทน</ผลตอบแทน>
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

## การใช้เมธอด GetBarCodeImage()

 ในขั้นตอนนี้ เราจะดำเนินการ`getBarcodeImage` วิธีการซึ่งสร้างภาพบาร์โค้ดตามพารามิเตอร์ที่ให้ไว้ เราจะจัดการบาร์โค้ดประเภทต่างๆ กำหนดสี ปรับขนาด และอื่นๆ นี่คือรหัสสำหรับวิธีนี้:

```java
/// <สรุป>
/// การใช้งานเมธอด GetBarCodeImage() สำหรับอินเทอร์เฟซ IBarCodeGenerator
/// </สรุป>
/// <param name="parameters"></param>
/// <ผลตอบแทน</ผลตอบแทน>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// ตรวจสอบว่าระบุประเภทและค่าบาร์โค้ดหรือไม่
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// สร้าง BarcodeGenerator ตามประเภทบาร์โค้ด
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// จัดการบาร์โค้ดประเภทอื่นๆ ที่นี่
	}
	
	// ตั้งค่าข้อความบาร์โค้ด
	generator.setCodeText(parameters.getBarcodeValue());
	
	// ตั้งค่าสีบาร์โค้ด
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// กำหนดความสูงและขนาดของสัญลักษณ์
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//ปรับแต่งตำแหน่งข้อความโค้ด
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// การปรับเปลี่ยนเพิ่มเติมสำหรับรหัส QR
	final float SCALE = 2.4f; // ปัจจัยการปรับสเกลเชิงประจักษ์สำหรับการแปลงบาร์โค้ด Word เป็น Aspose.BarCode
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

## การใช้เมธอด GetOldBarcodeImage()

 ในขั้นตอนนี้ เราจะดำเนินการ`getOldBarcodeImage` วิธีการซึ่งสร้างภาพบาร์โค้ดสำหรับบาร์โค้ดแบบเก่า ที่นี่ เราจะจัดการกับบาร์โค้ดประเภทใดประเภทหนึ่ง เช่น POSTNET นี่คือรหัสสำหรับวิธีนี้:

```java
/// <สรุป>
/// การใช้งานเมธอด GetOldBarcodeImage() สำหรับอินเทอร์เฟซ IBarCodeGenerator
/// </สรุป>
/// <param name="parameters"></param>
/// <ผลตอบแทน</ผลตอบแทน>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// ประเภทฮาร์ดโค้ดสำหรับบาร์โค้ดรุ่นเก่า
	return generator.generateBarCodeImage();
}
```

## บทสรุป

ในบทความนี้ เราได้สำรวจกระบวนการสร้างฉลากบาร์โค้ดแบบกำหนดเองโดยใช้ Aspose.Words สำหรับ Java เราได้กล่าวถึงขั้นตอนสำคัญต่างๆ ตั้งแต่การตั้งค่าความสูงของบาร์โค้ดไปจนถึงการนำวิธีการสร้างบาร์โค้ดไปใช้ Aspose.Words สำหรับ Java ช่วยให้นักพัฒนาสามารถสร้างฉลากบาร์โค้ดแบบไดนามิกและปรับแต่งได้ ทำให้เป็นเครื่องมืออันทรงคุณค่าสำหรับอุตสาหกรรมต่างๆ

## คำถามที่พบบ่อย

### ฉันจะปรับขนาดของบาร์โค้ดที่สร้างขึ้นได้อย่างไร

คุณสามารถปรับขนาดของบาร์โค้ดที่สร้างขึ้นได้โดยการตั้งค่าความสูงของสัญลักษณ์และตัวคูณมาตราส่วนของบาร์โค้ดในตัวอย่างโค้ดที่ให้มา พารามิเตอร์เหล่านี้ช่วยให้คุณสามารถควบคุมขนาดของบาร์โค้ดได้ตามความต้องการของคุณ

### ฉันสามารถเปลี่ยนสีของบาร์โค้ดได้หรือไม่?

ได้ คุณสามารถเปลี่ยนสีของบาร์โค้ดได้โดยการระบุสีพื้นหน้าและพื้นหลังในโค้ด การปรับแต่งนี้ทำให้คุณสามารถจับคู่รูปลักษณ์ของบาร์โค้ดกับการออกแบบเอกสารของคุณได้

### Aspose.Words สำหรับ Java รองรับบาร์โค้ดประเภทใดบ้าง

Aspose.Words สำหรับ Java รองรับบาร์โค้ดหลายประเภท รวมถึงรหัส QR, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 และอื่นๆ คุณสามารถเลือกประเภทบาร์โค้ดที่เหมาะกับความต้องการใช้งานของคุณได้

### ฉันจะรวมบาร์โค้ดที่สร้างขึ้นลงในเอกสาร Word ของฉันได้อย่างไร

หากต้องการรวมบาร์โค้ดที่สร้างขึ้นลงในเอกสาร Word ของคุณ คุณสามารถใช้ Aspose.Words สำหรับความสามารถในการจัดการเอกสารของ Java คุณสามารถแทรกภาพบาร์โค้ดลงในเอกสารของคุณในตำแหน่งที่ต้องการได้

### มีโค้ดตัวอย่างสำหรับการปรับแต่งเพิ่มเติมหรือไม่?

 ใช่ คุณสามารถค้นหาตัวอย่างโค้ดและเอกสารเพิ่มเติมได้จากไซต์อ้างอิงของ Aspose.Words สำหรับ Java:[Aspose.Words สำหรับการอ้างอิง Java API](https://reference.aspose.com/words/java/).