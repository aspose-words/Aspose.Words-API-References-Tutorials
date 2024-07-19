---
title: เข้าถึงและตรวจสอบลายเซ็นในเอกสาร Word
linktitle: เข้าถึงและตรวจสอบลายเซ็นในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เข้าถึงและตรวจสอบลายเซ็นดิจิทัลในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนที่ครอบคลุมนี้ ตรวจสอบความถูกต้องของเอกสารได้อย่างง่ายดาย
type: docs
weight: 10
url: /th/net/programming-with-digital-signatures/access-and-verify-signature/
---
## การแนะนำ

สวัสดีเพื่อน ๆ ที่ชื่นชอบเทคโนโลยี! เคยพบว่าตัวเองอยู่ในสถานการณ์ที่คุณต้องเข้าถึงและตรวจสอบลายเซ็นดิจิทัลในเอกสาร Word แต่ไม่รู้ว่าจะเริ่มต้นจากตรงไหน คุณโชคดี! วันนี้ เรากำลังดำดิ่งสู่โลกมหัศจรรย์ของ Aspose.Words สำหรับ .NET ซึ่งเป็นไลบรารีอันทรงพลังที่ทำให้การจัดการเอกสาร Word เป็นเรื่องง่าย เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน ดังนั้นในตอนท้ายของคู่มือนี้ คุณจะเป็นมืออาชีพในการตรวจสอบลายเซ็นดิจิทัลในเอกสาร Word มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกรายละเอียดที่สำคัญ มีบางสิ่งที่คุณต้องเตรียม:

1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว นี่คือที่ที่คุณจะเขียนและรันโค้ดของคุณ
2.  Aspose.Words สำหรับ .NET: คุณจะต้องติดตั้ง Aspose.Words สำหรับ .NET คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/words/net/) - อย่าลืมรับสิทธิ์ทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/) ถ้าคุณยังไม่ได้!
3. เอกสาร Word ที่เซ็นชื่อแบบดิจิทัล: มีเอกสาร Word ที่เซ็นชื่อแบบดิจิทัลแล้ว นี่คือไฟล์ที่คุณจะใช้งานเพื่อตรวจสอบลายเซ็น

## นำเข้าเนมสเปซ

ก่อนอื่น มานำเข้าเนมสเปซที่จำเป็นกันก่อน เนมสเปซเหล่านี้จะอนุญาตให้คุณใช้ฟีเจอร์ Aspose.Words ในโปรเจ็กต์ของคุณได้

```csharp
using System;
using Aspose.Words;
using Aspose.Words.DigitalSignatures;
```

เอาล่ะ เรามาแบ่งขั้นตอนนี้ออกเป็นขั้นตอนที่สามารถจัดการได้ แต่ละขั้นตอนจะแนะนำคุณตลอดส่วนเฉพาะของกระบวนการ พร้อม? ไปกันเถอะ!

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

ก่อนที่คุณจะสามารถตรวจสอบลายเซ็นดิจิทัลได้ คุณจะต้องตั้งค่าโปรเจ็กต์ของคุณใน Visual Studio มีวิธีดังนี้:

### สร้างโครงการใหม่

1. เปิด Visual Studio
2. คลิกที่สร้างโครงการใหม่
3. เลือกแอปคอนโซล (.NET Core) หรือแอปคอนโซล (.NET Framework) ขึ้นอยู่กับความต้องการของคุณ
4. คลิกถัดไป ตั้งชื่อโครงการของคุณ แล้วคลิกสร้าง

### ติดตั้ง Aspose.Words สำหรับ .NET

1. ใน Solution Explorer คลิกขวาที่ชื่อโปรเจ็กต์ของคุณแล้วเลือกจัดการแพ็คเกจ NuGet
2. ใน NuGet Package Manager ให้ค้นหา Aspose.Words
3. คลิกติดตั้งเพื่อเพิ่มลงในโครงการของคุณ

## ขั้นตอนที่ 2: โหลดเอกสาร Word ที่เซ็นชื่อแบบดิจิทัล

ตอนนี้โครงการของคุณได้รับการตั้งค่าแล้ว มาโหลดเอกสาร Word ที่เซ็นชื่อแบบดิจิทัลกันดีกว่า

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ ข้อมูลโค้ดนี้เริ่มต้นใหม่`Document` วัตถุและโหลดเอกสาร Word ที่ลงนามของคุณ

## ขั้นตอนที่ 3: เข้าถึงลายเซ็นดิจิทัล

เมื่อโหลดเอกสารของคุณแล้ว ก็ถึงเวลาเข้าถึงลายเซ็นดิจิทัล

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
    Console.WriteLine("* Signature Found *");
    Console.WriteLine("Is valid: " + signature.IsValid);
    Console.WriteLine("Reason for signing: " + signature.Comments); 
    Console.WriteLine("Time of signing: " + signature.SignTime);
    Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
    Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
    Console.WriteLine();
}
```

รหัสนี้จะวนซ้ำลายเซ็นดิจิทัลแต่ละรายการในเอกสารและพิมพ์รายละเอียดต่างๆ เกี่ยวกับลายเซ็น มาดูกันว่าแต่ละส่วนทำหน้าที่อะไร:

1. พบลายเซ็น: บ่งชี้ว่าพบลายเซ็นแล้ว
2. ถูกต้อง: ตรวจสอบว่าลายเซ็นถูกต้องหรือไม่
3. เหตุผลในการลงนาม: แสดงเหตุผลในการลงนาม หากมี
4. เวลาที่ลงนาม: แสดงเวลาประทับเวลาที่ลงนามในเอกสาร
5. ชื่อเรื่อง: ดึงชื่อเรื่องจากใบรับรอง
6. ชื่อผู้ออก: ดึงข้อมูลชื่อผู้ออกจากใบรับรอง

## ขั้นตอนที่ 4: เรียกใช้รหัสของคุณ

เมื่อตั้งค่าทุกอย่างเรียบร้อยแล้ว ก็ถึงเวลาเรียกใช้โค้ดของคุณและดูผลลัพธ์


1. กด F5 หรือคลิกปุ่มเริ่มใน Visual Studio เพื่อเรียกใช้โปรแกรมของคุณ
2. หากเอกสารของคุณเซ็นชื่อแบบดิจิทัล คุณจะเห็นรายละเอียดลายเซ็นพิมพ์อยู่ในคอนโซล

## ขั้นตอนที่ 5: จัดการกับข้อผิดพลาดที่อาจเกิดขึ้น

เป็นความคิดที่ดีเสมอที่จะจัดการกับข้อผิดพลาดที่อาจเกิดขึ้น มาเพิ่มการจัดการข้อผิดพลาดพื้นฐานให้กับโค้ดของเรากัน

```csharp
try
{
    // เส้นทางไปยังไดเร็กทอรีเอกสาร
    string dataDir = "YOUR DOCUMENT DIRECTORY";
    Document doc = new Document(dataDir + "Digitally signed.docx");

    foreach (DigitalSignature signature in doc.DigitalSignatures)
    {
        Console.WriteLine("* Signature Found *");
        Console.WriteLine("Is valid: " + signature.IsValid);
        Console.WriteLine("Reason for signing: " + signature.Comments); 
        Console.WriteLine("Time of signing: " + signature.SignTime);
        Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
        Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
        Console.WriteLine();
    }
}
catch (Exception ex)
{
    Console.WriteLine("An error occurred: " + ex.Message);
}
```

วิธีนี้จะตรวจจับข้อยกเว้นใด ๆ ที่อาจเกิดขึ้นและพิมพ์ข้อความแสดงข้อผิดพลาด

## บทสรุป

และคุณก็ได้แล้ว! คุณเข้าถึงและตรวจสอบลายเซ็นดิจิทัลในเอกสาร Word ได้สำเร็จโดยใช้ Aspose.Words สำหรับ .NET มันไม่น่ากลัวอย่างที่คิดใช่ไหม? ด้วยขั้นตอนเหล่านี้ คุณสามารถจัดการลายเซ็นดิจิทัลในเอกสาร Word ของคุณได้อย่างมั่นใจ โดยรับประกันความถูกต้องและความสมบูรณ์ของลายเซ็นเหล่านั้น ขอให้มีความสุขในการเขียนโค้ด!

## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Words สำหรับ .NET เพื่อเพิ่มลายเซ็นดิจิทัลลงในเอกสาร Word ได้หรือไม่

ได้ คุณสามารถใช้ Aspose.Words สำหรับ .NET เพื่อเพิ่มลายเซ็นดิจิทัลลงในเอกสาร Word ได้ ไลบรารีมีคุณสมบัติที่ครอบคลุมสำหรับทั้งการเพิ่มและการตรวจสอบลายเซ็นดิจิทัล

### ลายเซ็นดิจิทัลประเภทใดบ้างที่ Aspose.Words สำหรับ .NET ตรวจสอบได้

Aspose.Words สำหรับ .NET สามารถตรวจสอบลายเซ็นดิจิทัลในไฟล์ DOCX ที่ใช้ใบรับรอง X.509

### Aspose.Words สำหรับ .NET เข้ากันได้กับ Microsoft Word ทุกรุ่นหรือไม่

Aspose.Words สำหรับ .NET รองรับเอกสาร Microsoft Word ทุกเวอร์ชัน รวมถึง DOC, DOCX, RTF และอื่นๆ

### ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Words สำหรับ .NET ได้อย่างไร

 คุณสามารถรับใบอนุญาตชั่วคราวสำหรับ Aspose.Words สำหรับ .NET ได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/)- สิ่งนี้ทำให้คุณสามารถลองใช้ฟีเจอร์ทั้งหมดของไลบรารีได้โดยไม่มีข้อจำกัดใดๆ

### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Words สำหรับ .NET ได้ที่ไหน

 คุณสามารถค้นหาเอกสารประกอบโดยละเอียดสำหรับ Aspose.Words สำหรับ .NET[ที่นี่](https://reference.aspose.com/words/net/).