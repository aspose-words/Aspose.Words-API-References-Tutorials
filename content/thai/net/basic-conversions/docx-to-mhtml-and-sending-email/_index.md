---
title: แปลง Docx เป็น Mhtml และส่งอีเมล
linktitle: แปลง Docx เป็น Mhtml และส่งอีเมล
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแปลงเอกสาร Word จาก Docx เป็น MHTML และส่งเป็นอีเมลโดยใช้ Aspose.Words และ Aspose.Email บทช่วยสอนทีละขั้นตอน
type: docs
weight: 10
url: /th/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับวิธีใช้ Aspose.Words สำหรับ .NET เพื่อแปลงเอกสาร Word ในรูปแบบ Docx เป็น MHTML และส่งเป็นอีเมลโดยใช้ Aspose.Email เราจะอธิบายซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง

 ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีทั้งไลบรารี Aspose.Words สำหรับ .NET และ Aspose.Email ติดตั้งและตั้งค่าในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้ดำเนินการ ให้ดาวน์โหลดและติดตั้งไลบรารีจาก[กำหนดเผยแพร่](https://releases.aspose.com/words/net/).

## ขั้นตอนที่ 1: การเริ่มต้นวัตถุเอกสาร

 ขั้นแรกให้เริ่มต้น`Document`วัตถุที่มีเส้นทางไปยังเอกสารต้นฉบับของคุณในรูปแบบ Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## ขั้นตอนที่ 2: บันทึกเอกสารในรูปแบบ MHTML

 จากนั้นบันทึกเอกสารลงในไฟล์`Stream` วัตถุในรูปแบบ MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## ขั้นตอนที่ 3: การกรอกลับสตรีม

เนื่องจาก Aspose.Email จำเป็นต้องอ่านสตรีมตั้งแต่ต้น ให้กรอกลับสตรีมไปที่จุดเริ่มต้น:

```csharp
stream.Position = 0;
```

## ขั้นตอนที่ 4: การสร้างข้อความ MIME ของ Aspose.Email

 สร้างก`MailMessage` วัตถุจากสตรีมโดยใช้`MhtmlLoadOptions`: :

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

คุณสามารถปรับแต่งคุณสมบัติของข้อความ เช่น ผู้ส่ง ผู้รับ และหัวเรื่องได้ตามต้องการ

## ขั้นตอนที่ 5: การส่งอีเมล

 ใช้ Aspose.Email's`SmtpClient` เพื่อส่งอีเมล:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

ตรวจสอบให้แน่ใจว่าคุณระบุที่อยู่โฮสต์เซิร์ฟเวอร์ SMTP ที่ถูกต้อง

แค่นั้นแหละ! คุณได้แปลงเอกสาร Word ในรูปแบบ Docx เป็น MHTML สำเร็จแล้ว และส่งเป็นอีเมลโดยใช้ Aspose.Words สำหรับ .NET และ Aspose.Email

### ตัวอย่างซอร์สโค้ดสำหรับ Docx To Mhtml และการส่งอีเมลโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เอกสาร doc = เอกสารใหม่ (MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//ย้อนกลับสตรีมไปที่จุดเริ่มต้นเพื่อให้ Aspose.Email สามารถอ่านได้
	stream.Position = 0;

	// สร้างข้อความอีเมล Aspose.Email MIME จากสตรีม
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// ส่งข้อความโดยใช้ Aspose.Email
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

คุณสามารถใช้โค้ดนี้ในโครงการของคุณเองและแก้ไขได้ตามความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อย

#### วิธีแปลงไฟล์ DOCX เป็น MHTML

หากต้องการแปลงไฟล์ DOCX เป็น MHTML คุณสามารถใช้เครื่องมือซอฟต์แวร์หรือไลบรารีที่มีฟังก์ชันนี้ได้ Aspose.Words สำหรับ .NET เป็นตัวเลือกที่เชื่อถือได้สำหรับการแปลงนี้ คุณสามารถใช้ไลบรารี API เพื่อโหลดไฟล์ DOCX และบันทึกในรูปแบบ MHTML

#### ฉันจะส่งอีเมลพร้อมไฟล์แนบ MHTML ได้อย่างไร

หากต้องการส่งอีเมลพร้อมไฟล์ MHTML เป็นไฟล์แนบ คุณสามารถใช้ไลบรารีหรือเครื่องมือเฉพาะสำหรับการส่งอีเมล เช่น System.Net.Mail ใน .NET คุณต้องสร้างข้อความอีเมล ระบุผู้รับ หัวเรื่อง และเนื้อหา จากนั้นเพิ่มไฟล์ MHTML เป็นสิ่งที่แนบมาในข้อความก่อนที่จะส่ง

#### ข้อจำกัดของการแปลงและกระบวนการส่งอีเมลมีอะไรบ้าง

ข้อจำกัดของการแปลงและกระบวนการส่งอีเมลขึ้นอยู่กับเครื่องมือเฉพาะที่คุณใช้ เครื่องมือบางอย่างอาจมีข้อจำกัดเกี่ยวกับขนาดไฟล์ การตั้งค่าความปลอดภัย หรือโปรโตคอลอีเมลที่รองรับ สิ่งสำคัญคือต้องเลือกเครื่องมือที่เหมาะกับความต้องการของคุณและพิจารณาข้อจำกัดเหล่านี้เมื่อนำไปใช้งาน

#### Aspose เป็นเครื่องมือที่เชื่อถือได้สำหรับการแปลง DOCX เป็น MHTML และการส่งอีเมลหรือไม่

ใช่ Aspose.Words สำหรับ .NET เป็นเครื่องมือที่เชื่อถือได้สำหรับการแปลง DOCX เป็น MHTML และการส่งอีเมล นักพัฒนาและผู้เชี่ยวชาญใช้กันอย่างแพร่หลายในด้านประสิทธิภาพและคุณภาพ เครื่องมือนี้นำเสนอเอกสารที่ครอบคลุม คุณสมบัติขั้นสูง และการสนับสนุนด้านเทคนิคโดยเฉพาะ ทำให้เป็นตัวเลือกที่แนะนำสำหรับงานเหล่านี้