---
title: แปลง Docx เป็น Mhtml และส่งอีเมล
linktitle: แปลง Docx เป็น Mhtml และส่งอีเมล
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแปลง DOCX เป็น MHTML และส่งอีเมลโดยใช้ Aspose.Words สำหรับ .NET ในคำแนะนำทีละขั้นตอนนี้ เพิ่มผลผลิตของคุณด้วยระบบอัตโนมัติที่ง่ายดาย
type: docs
weight: 10
url: /th/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## การแนะนำ

ในยุคดิจิทัลปัจจุบัน การแปลงเอกสารจากรูปแบบหนึ่งไปเป็นอีกรูปแบบหนึ่งและส่งทางอีเมลถือเป็นงานทั่วไป บทความนี้จะแนะนำคุณตลอดขั้นตอนการแปลงไฟล์ DOCX เป็นรูปแบบ MHTML จากนั้นส่งเป็นอีเมลโดยใช้ Aspose.Words สำหรับ .NET เราจะแจกแจงแต่ละขั้นตอนโดยละเอียดและง่ายต่อการปฏิบัติตาม เพื่อให้แน่ใจว่าคุณจะเข้าใจกระบวนการตั้งแต่ต้นจนจบ มาดำน้ำกันเถอะ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Aspose.Words for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Words for .NET จาก[กำหนดหน้าการเผยแพร่](https://releases.aspose.com/words/net/).
2.  Aspose.Email for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Email for .NET จากไฟล์[กำหนดหน้าการเผยแพร่](https://releases.aspose.com/email/net/).
3. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework บนเครื่องของคุณ
4. เซิร์ฟเวอร์ SMTP: คุณต้องเข้าถึงเซิร์ฟเวอร์ SMTP เพื่อส่งอีเมล

## นำเข้าเนมสเปซ

หากต้องการใช้ Aspose.Words และ Aspose.Email ในโปรเจ็กต์ของคุณ คุณจะต้องนำเข้าเนมสเปซที่จำเป็น เพิ่มคำสั่งต่อไปนี้ที่ด้านบนของไฟล์ C# ของคุณ:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

มาแบ่งกระบวนการออกเป็นหลายขั้นตอนเพื่อให้แน่ใจว่าคุณเข้าใจแต่ละส่วนอย่างชัดเจน

## ขั้นตอนที่ 1: โหลดเอกสาร DOCX

 ขั้นแรก คุณต้องโหลดเอกสาร DOCX ที่คุณต้องการแปลง ใช้`Document` คลาสจาก Aspose.Words เพื่อโหลดไฟล์ DOCX ของคุณ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## ขั้นตอนที่ 2: บันทึกเอกสารเป็น MHTML

 จากนั้น ให้บันทึกเอกสารที่โหลดเป็นไฟล์ MHTML นี้จะกระทำโดยใช้`Save` วิธีการของ`Document` ระดับ.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// ย้อนกลับสตรีมไปที่จุดเริ่มต้นเพื่อให้ Aspose.Email สามารถอ่านได้
stream.Position = 0;
```

## ขั้นตอนที่ 3: สร้างข้อความอีเมล

ตอนนี้ ให้สร้างข้อความอีเมลจากสตรีม MHTML โดยใช้ Aspose.Email คุณจะใช้`MailMessage` ชั้นเรียนเพื่อการนี้

```csharp
// สร้างข้อความอีเมล Aspose.Email MIME จากสตรีม
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## ขั้นตอนที่ 4: ส่งอีเมล

 สุดท้าย ส่งอีเมลโดยใช้ไคลเอ็นต์ SMTP กำหนดค่าไคลเอ็นต์ SMTP ด้วยรายละเอียดเซิร์ฟเวอร์ SMTP ของคุณ และใช้`Send` วิธีการส่งข้อความ

```csharp
// ส่งข้อความโดยใช้ Aspose.Email
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## บทสรุป

ยินดีด้วย! คุณได้แปลงเอกสาร DOCX เป็น MHTML และส่งทางอีเมลโดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว กระบวนการนี้เกี่ยวข้องกับการโหลดเอกสาร แปลงเป็น MHTML การสร้างข้อความอีเมล และส่งโดยใช้ไคลเอ็นต์ SMTP ด้วยขั้นตอนเหล่านี้ คุณสามารถทำให้การแปลงและการส่งอีเมลเอกสารในแอปพลิเคชันของคุณเป็นแบบอัตโนมัติได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### ฉันสามารถใช้วิธีนี้แปลงรูปแบบเอกสารอื่นได้หรือไม่
ใช่ Aspose.Words รองรับรูปแบบต่างๆ และคุณสามารถแปลงเอกสาร เช่น DOC, DOCX, RTF และอื่นๆ เป็น MHTML ได้

### ฉันจะเพิ่มไฟล์แนบในอีเมลได้อย่างไร?
 คุณสามารถใช้`Attachments` ทรัพย์สินของ`MailMessage`คลาสเพื่อเพิ่มไฟล์แนบในอีเมลของคุณ

### Aspose.Words เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.Words เข้ากันได้กับ .NET Core คุณสามารถใช้มันในแอปพลิเคชัน .NET Core ได้เช่นกัน

### ฉันต้องมีใบอนุญาตสำหรับ Aspose.Words และ Aspose.Email หรือไม่
 ใช่ ห้องสมุดทั้งสองแห่งจำเป็นต้องมีใบอนุญาต คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[กำหนดหน้าการซื้อ](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการประเมินผล

### ฉันจะหาเอกสารเพิ่มเติมได้จากที่ไหน?
 คุณสามารถดูเอกสารประกอบโดยละเอียดสำหรับ Aspose.Words[ที่นี่](https://reference.aspose.com/words/net/) และสำหรับ Aspose.Email[ที่นี่](https://reference.aspose.com/email/net/).
