---
title: ตรวจสอบเอฟเฟกต์ข้อความ DrawingML
linktitle: ตรวจสอบเอฟเฟกต์ข้อความ DrawingML
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีตรวจสอบเอฟเฟกต์ข้อความ DrawingML ในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fonts/check-drawingml-text-effect/
---

ในบทช่วยสอนนี้ เราจะอธิบายวิธีการตรวจสอบเอฟเฟกต์ข้อความ DrawingML ในเอกสาร Word โดยใช้ Aspose.Words Library สำหรับ .NET การตรวจสอบเอฟเฟกต์ข้อความ DrawingML ช่วยให้คุณสามารถระบุได้ว่ามีการใช้เอฟเฟกต์เฉพาะกับส่วนของข้อความหรือไม่ เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีรายการต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
- ไลบรารี Aspose.Words สำหรับ .NET ที่ติดตั้งในโครงการของคุณ
- เอกสาร Word ที่มีเอฟเฟกต์ข้อความ DrawingML

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
 ขั้นแรก คุณต้องตั้งค่าเส้นทางไดเรกทอรีไปยังตำแหน่งของเอกสาร Word ของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้วยเส้นทางที่เหมาะสม

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารและตรวจสอบเอฟเฟกต์ข้อความ
ต่อไป เราจะโหลดเอกสาร Word และเข้าถึงคอลเลกชันของการรัน (ลำดับอักขระ) ในย่อหน้าแรกของเนื้อหาของเอกสาร ต่อไป เราจะตรวจสอบว่ามีการใช้เอฟเฟกต์ข้อความ DrawingML เฉพาะกับแบบอักษรของการเรียกใช้ครั้งแรกหรือไม่

```csharp
// โหลดเอกสาร
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// ตรวจสอบเอฟเฟกต์ข้อความ DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### ตัวอย่างซอร์สโค้ดสำหรับตรวจสอบเอฟเฟกต์ DMLText โดยใช้ Aspose.Words สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// การเรียกใช้หนึ่งครั้งอาจมีเอฟเฟกต์ข้อความ Dml หลายรายการ
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เห็นวิธีการตรวจสอบเอฟเฟกต์ข้อความ DrawingML ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET การตรวจสอบเอฟเฟกต์ข้อความ DrawingML ช่วยให้คุณสามารถระบุส่วนของข้อความที่ใช้เอฟเฟกต์เฉพาะได้ คุณสามารถใช้คุณสมบัตินี้เพื่อจัดการและวิเคราะห์เอฟเฟกต์ข้อความในเอกสาร Word ของคุณได้

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเข้าถึงเอฟเฟกต์ข้อความ DrawingML ในเอกสาร Word โดยใช้ Aspose.Words ได้อย่างไร

ตอบ: ด้วย Aspose.Words คุณสามารถเข้าถึงเอฟเฟกต์ข้อความ DrawingML ในเอกสาร Word ได้โดยใช้ API ที่ให้มา คุณสามารถเรียกดูองค์ประกอบข้อความและตรวจสอบคุณสมบัติเฉพาะของเอฟเฟกต์ข้อความ เช่น สี ขนาด ฯลฯ

#### ถาม: เอฟเฟกต์ข้อความ DrawingML ประเภทใดที่มักใช้ในเอกสาร Word

ตอบ: เอฟเฟกต์ข้อความ DrawingML ที่ใช้กันทั่วไปในเอกสาร Word ได้แก่ เงา การสะท้อน การเรืองแสง การไล่ระดับสี ฯลฯ เอฟเฟ็กต์เหล่านี้สามารถนำไปใช้เพื่อปรับปรุงลักษณะที่ปรากฏและการจัดรูปแบบของข้อความ

#### ถาม: ฉันจะตรวจสอบสีของเอฟเฟกต์ข้อความ DrawingML ในเอกสาร Word ได้อย่างไร

ตอบ: หากต้องการตรวจสอบสีของเอฟเฟกต์ข้อความ DrawingML ในเอกสาร Word คุณสามารถใช้วิธีการที่ Aspose.Words ให้มาเพื่อเข้าถึงคุณสมบัติสีของเอฟเฟกต์ข้อความ วิธีนี้จะทำให้คุณได้สีที่ใช้สำหรับเอฟเฟกต์ข้อความเฉพาะ

#### ถาม: สามารถตรวจสอบเอฟเฟกต์ข้อความในเอกสาร Word ที่มีหลายส่วนได้หรือไม่

ตอบ: ได้ Aspose.Words อนุญาตให้ตรวจสอบเอฟเฟกต์ข้อความในเอกสาร Word ที่มีหลายส่วน คุณสามารถนำทางผ่านแต่ละส่วนของเอกสารและเข้าถึงเอฟเฟกต์ข้อความสำหรับแต่ละส่วนได้

#### ถาม: ฉันจะตรวจสอบความทึบของเอฟเฟกต์ข้อความ DrawingML ในเอกสาร Word ได้อย่างไร

ตอบ: หากต้องการตรวจสอบความทึบของเอฟเฟกต์ข้อความ DrawingML ในเอกสาร Word คุณสามารถใช้วิธีการที่ Aspose.Words ให้มาเพื่อเข้าถึงคุณสมบัติความทึบของเอฟเฟกต์ข้อความ สิ่งนี้จะช่วยให้คุณได้รับค่าความทึบที่ใช้กับเอฟเฟกต์ข้อความเฉพาะ