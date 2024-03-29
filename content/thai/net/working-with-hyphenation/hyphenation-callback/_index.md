---
title: การโทรกลับด้วยยัติภังค์
linktitle: การโทรกลับด้วยยัติภังค์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้การเรียกกลับด้วยยัติภังค์ใน Aspose.Words สำหรับ .NET เพื่อจัดการการใส่ยติภังค์คำ
type: docs
weight: 10
url: /th/net/working-with-hyphenation/hyphenation-callback/
---

ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแสดงวิธีใช้ฟีเจอร์การโทรกลับด้วยการใส่ยัติภังค์ใน Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง

 ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่า Aspose.Words สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Releases]https://releases.aspose.com/words/net/

## ขั้นตอนที่ 1: บันทึกการแจ้งเตือนการใส่ยัติภังค์

 ขั้นแรก เราจะลงทะเบียนการเรียกกลับด้วยยัติภังค์โดยใช้แบบกำหนดเอง`CustomHyphenationCallback` ระดับ. สิ่งนี้จะทำให้เราสามารถจัดการกับการใส่ยติภังค์คำได้ตามกฎของเราเอง:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 ตรวจสอบให้แน่ใจว่าคุณได้ดำเนินการ`CustomHyphenationCallback` ชั้นเรียนตามความต้องการเฉพาะของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสารและใช้การใส่ยัติภังค์

จากนั้น โหลดเอกสารของคุณจากไดเร็กทอรีที่ระบุและใส่ยัติภังค์คำโดยใช้ Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## ขั้นตอนที่ 3: การจัดการข้อผิดพลาดของพจนานุกรมที่หายไป

ในกรณีที่พจนานุกรมการใส่ยัติภังค์หายไป เราจะจับข้อยกเว้นที่เกี่ยวข้องและแสดงข้อความแสดงข้อผิดพลาด:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## ขั้นตอนที่ 4: ล้างข้อมูลและปิดใช้งานการแจ้งเตือนการใส่ยัติภังค์

สุดท้าย เพื่อความสะอาดและปิดตัวเตือนการใส่ยัติภังค์ ให้ทำตามขั้นตอนต่อไปนี้:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

วิธีนี้จะล้างข้อมูลและปิดใช้งานการแจ้งเตือนการใส่ยัติภังค์หลังจากเสร็จสิ้นการประมวลผล

ดังนั้น ! คุณใช้การเรียกกลับด้วยยัติภังค์ใน Aspose.Words สำหรับ .NET สำเร็จแล้ว

### ตัวอย่างซอร์สโค้ดสำหรับการโทรกลับด้วยยัติภังค์ด้วย Aspose.Words สำหรับ .NET

```csharp
try
{
	 // ลงทะเบียนการโทรกลับด้วยการใส่ยัติภังค์
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

คุณสามารถใช้โค้ดนี้ในโครงการของคุณเองและแก้ไขให้เหมาะกับความต้องการเฉพาะของคุณได้

### คำถามที่พบบ่อย

#### ถาม: ตัวเตือนพยางค์ใน Aspose.Words คืออะไร

ตอบ: การเตือนความจำใน Aspose.Words เป็นคุณสมบัติที่ช่วยให้คุณปรับแต่งวิธีการจัดคำศัพท์ในเอกสารของคุณได้ ด้วยการใช้ตัวเตือนพยางค์ คุณสามารถระบุกฎที่กำหนดเองสำหรับการจัดพยางค์คำได้ ซึ่งอาจมีประโยชน์สำหรับภาษาเฉพาะหรือสถานการณ์เฉพาะที่การพยางค์เริ่มต้นไม่ได้ให้ผลลัพธ์ที่ต้องการ

#### ถาม: จะตั้งค่าตัวเตือนพยางค์ใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการกำหนดการเรียกกลับด้วยยัติภังค์ใน Aspose.Words คุณต้องสร้างคลาสที่ใช้`HyphenationCallback` อินเตอร์เฟซและดำเนินการ`HandleWord()` วิธี. วิธีการนี้จะถูกเรียกสำหรับแต่ละคำที่พบในระหว่างการแยกพยางค์ คุณสามารถใช้กฎการจัดพยางค์แบบกำหนดเองกับคำดังกล่าวและส่งกลับคำในพยางค์ได้ จากนั้นคุณสามารถผูกการโทรกลับด้วยยัติภังค์โดยใช้`Document.HyphenationCallback` ทรัพย์สินของเอกสารของคุณ

#### ถาม: ข้อดีของการใช้การเตือนความจำพยางค์ใน Aspose.Words คืออะไร

ตอบ: ประโยชน์ของการใช้การเตือนความจำพยางค์ใน Aspose.Words คือความสามารถในการปรับแต่งวิธีการจัดพยางค์คำในเอกสารของคุณ สิ่งนี้ช่วยให้คุณควบคุมการออกเสียงพยางค์ได้มากขึ้น โดยเฉพาะอย่างยิ่งสำหรับภาษาหรือสถานการณ์เฉพาะที่การพยางค์เริ่มต้นไม่ให้ผลลัพธ์ที่ต้องการ คุณสามารถใช้กฎเฉพาะกับแต่ละคำเพื่อให้ได้พยางค์ที่แม่นยำตามความต้องการของคุณ

#### ถาม: สถานการณ์ทั่วไปใดบ้างที่การใช้การเตือนความจำพยางค์อาจเป็นประโยชน์ได้

ตอบ: การใช้ตัวขยายพยางค์อาจมีประโยชน์ได้ในหลายสถานการณ์ เช่น:
- การเรียงคำในภาษาเฉพาะที่มีกฎการกำหนดพยางค์เฉพาะ
- การใช้กฎการกำหนดพยางค์ส่วนบุคคลสำหรับคำย่อหรือคำศัพท์ทางเทคนิค
- การปรับเปลี่ยนพยางค์ตามความต้องการด้านโวหารหรือมาตรฐานการพิมพ์

#### ถาม: ฉันจะทดสอบการออกเสียงพยางค์แบบกำหนดเองด้วยตัวเตือนการออกเสียงพยางค์ใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการทดสอบการจัดพยางค์ที่กำหนดเองด้วยตัวเตือนการจัดพยางค์ใน Aspose.Words คุณสามารถสร้างเอกสารทดสอบที่มีคำที่คุณต้องการใช้กฎการจัดพยางค์ที่กำหนดเองได้ จากนั้นคุณสามารถตั้งค่าการโทรกลับของพยางค์ที่คุณกำหนดเองได้ โทรไปที่`Document.Range.Replace()` วิธีการแทนที่คำในเอกสารและใช้`Hyphenate()` วิธีการของ`Hyphenation` ชั้นเรียนเพื่อรับพยางค์ของคำ จากนั้น คุณสามารถจัดรูปแบบคำในพยางค์ได้ตามต้องการ เช่น โดยการเพิ่มเครื่องหมายยัติภังค์ระหว่างพยางค์