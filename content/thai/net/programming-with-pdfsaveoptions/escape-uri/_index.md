---
title: หลบหนี URI ในเอกสาร PDF
linktitle: หลบหนี URI ในเอกสาร PDF
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนวิธีการ Escape URI ในเอกสาร PDF ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-pdfsaveoptions/escape-uri/
---

บทความนี้ให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการ Escape URI ในเอกสาร PDF ด้วย Aspose.Words สำหรับ .NET เราจะอธิบายโค้ดแต่ละส่วนอย่างละเอียด ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถเข้าใจวิธีแทรกไฮเปอร์ลิงก์ที่มี Uri ที่เป็น Escape ในเอกสารได้

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Words สำหรับ .NET ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดูไลบรารีและคำแนะนำในการติดตั้งได้จากเว็บไซต์ Aspose

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ในการเริ่มต้น คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่มีเอกสารของคุณอยู่ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารและ DocumentBuilder

 ต่อไปเราต้องสร้างใหม่`Document` วัตถุและก`DocumentBuilder` วัตถุเพื่อสร้างเอกสาร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: แทรกไฮเปอร์ลิงก์ด้วย Escape Uri

 ใช้`InsertHyperlink` วิธีการของ`DocumentBuilder` วัตถุเพื่อแทรกไฮเปอร์ลิงก์ลงในเอกสาร Uri จะต้องหลบหนีโดยใช้`Uri.EscapeUriString` ฟังก์ชั่นเพื่อหลีกเลี่ยงข้อผิดพลาดของรูปแบบ

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), เท็จ);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), เท็จ);
```

## ขั้นตอนที่ 4: บันทึกเอกสารเป็น PDF

 สุดท้ายเราสามารถบันทึกเอกสารเป็น PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ. ระบุชื่อไฟล์เอาต์พุต

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

นั่นคือทั้งหมดที่ ! คุณได้แทรกไฮเปอร์ลิงก์ที่มี Escape Uri's สำเร็จในเอกสารโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับการหลบหนี Uri ด้วย Aspose.Words สำหรับ .NET


```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงวิธีการหลีกเลี่ยง URI ในเอกสาร PDF โดยใช้ Aspose.Words สำหรับ .NET ด้วยการหลีกเลี่ยง URI คุณสามารถหลีกเลี่ยงข้อผิดพลาดในการจัดรูปแบบและให้แน่ใจว่าไฮเปอร์ลิงก์ได้รับการตีความและแสดงในเอกสาร PDF อย่างถูกต้อง ทำตามขั้นตอนที่ระบุไว้เพื่อแทรกไฮเปอร์ลิงก์ที่มี URI ที่ใช้ Escape ลงในเอกสาร PDF ของคุณ ให้แน่ใจว่าได้หลบหนี

### คำถามที่พบบ่อย

#### ถาม: Escape URI ในเอกสาร PDF คืออะไร และเหตุใดจึงสำคัญ
ตอบ: Escape URI ในเอกสาร PDF หมายถึงวิธีการแปลงอักขระพิเศษใน URL ให้เป็นลำดับ Escape เพื่อหลีกเลี่ยงข้อผิดพลาดของรูปแบบ นี่เป็นสิ่งสำคัญเนื่องจากอักขระพิเศษใน URL อาจรบกวนโครงสร้างของ URL และนำไปสู่การตีความที่ผิดหรือการแสดงผลที่ไม่ถูกต้อง ด้วยการหลีกอักขระพิเศษ เรารับประกันว่า URL จะได้รับการตีความและแสดงในเอกสาร PDF อย่างถูกต้อง

#### ถาม: ฉันจะใช้ Aspose.Words สำหรับ .NET เพื่อ Escape URI ในเอกสาร PDF ได้อย่างไร
ตอบ: หากต้องการหลีกเลี่ยง URI ในเอกสาร PDF โดยใช้ Aspose.Words สำหรับ .NET ให้ทำตามขั้นตอนเหล่านี้:

 กำหนดเส้นทางไดเร็กทอรีที่มีเอกสารของคุณอยู่โดยการแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีเอกสารของคุณ

 สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`DocumentBuilder` วัตถุเพื่อสร้างเอกสาร

 ใช้`InsertHyperlink` วิธีการของ`DocumentBuilder` วัตถุเพื่อแทรกไฮเปอร์ลิงก์ลงในเอกสาร อย่าลืมหลีกเลี่ยง URI โดยใช้ไฟล์`Uri.EscapeUriString` ฟังก์ชั่นเพื่อหลีกเลี่ยงข้อผิดพลาดของรูปแบบ

 ใช้`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสารในรูปแบบ PDF โดยระบุชื่อของไฟล์เอาต์พุต

#### ถาม: การ Escape URI ในเอกสาร PDF มีประโยชน์อย่างไร
ตอบ: ข้อดีของการ Escape URI ในเอกสาร PDF คือ:

การป้องกันข้อผิดพลาดของรูปแบบ: การ Escape URI ช่วยป้องกันข้อผิดพลาดของรูปแบบที่เกิดจากอักขระพิเศษใน URL ช่วยให้มั่นใจว่า URL ได้รับการตีความและแสดงในเอกสาร PDF อย่างถูกต้อง

ความเข้ากันได้กับโปรแกรมอ่าน PDF: โดยทั่วไปแล้ว Escaped URI จะได้รับการสนับสนุนอย่างดีจากโปรแกรมอ่าน PDF ทำให้มั่นใจได้ถึงความเข้ากันได้ที่ดีขึ้นและประสบการณ์ผู้ใช้ที่สอดคล้องกัน

#### ถาม: อักขระพิเศษใดที่ควรหลีกเลี่ยงใน URI
 ตอบ: อักขระพิเศษที่ต้องหลีกเลี่ยงใน URI คือ: ช่องว่าง, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.