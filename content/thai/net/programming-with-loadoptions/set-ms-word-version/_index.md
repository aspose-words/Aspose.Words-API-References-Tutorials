---
title: ตั้งค่าเวอร์ชัน Ms Word
linktitle: ตั้งค่าเวอร์ชัน Ms Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตั้งค่าเวอร์ชัน MS Word โดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำโดยละเอียดของเรา เหมาะสำหรับนักพัฒนาที่ต้องการปรับปรุงการจัดการเอกสาร

type: docs
weight: 10
url: /th/net/programming-with-loadoptions/set-ms-word-version/
---
## การแนะนำ

เคยพบว่าตัวเองจำเป็นต้องทำงานกับเอกสาร MS Word เวอร์ชันเฉพาะแต่ไม่รู้วิธีตั้งค่าโดยทางโปรแกรมหรือไม่? คุณไม่ได้อยู่คนเดียว! ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการตั้งค่าเวอร์ชัน MS Word โดยใช้ Aspose.Words สำหรับ .NET นี่เป็นเครื่องมือที่ยอดเยี่ยมที่ทำให้การจัดการเอกสาร Word เป็นเรื่องง่าย เราจะเจาะลึกเนื้อหาสำคัญ โดยแจกแจงรายละเอียดแต่ละขั้นตอนเพื่อให้แน่ใจว่าคุณพร้อมใช้งานและดำเนินไปอย่างราบรื่น พร้อมที่จะเริ่มต้นหรือยัง? มาดำน้ำกันเถอะ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะพูดถึงโค้ด เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการแล้ว:

-  Aspose.Words สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณมีเวอร์ชันล่าสุด[ดาวน์โหลดได้ที่นี่](https://releases.aspose.com/words/net/).
- สภาพแวดล้อมการพัฒนา: คุณสามารถใช้ Visual Studio หรือ IDE ที่รองรับ .NET อื่นๆ ได้
- ความรู้พื้นฐานของ C#: แม้ว่าเราจะทำให้มันง่าย แต่ความเข้าใจพื้นฐานเกี่ยวกับ C# ก็เป็นสิ่งจำเป็น
- เอกสารตัวอย่าง: เตรียมเอกสาร Word ให้พร้อมในไดเร็กทอรีเอกสารของคุณเพื่อการทดสอบ

## นำเข้าเนมสเปซ

ก่อนที่คุณจะเริ่มเขียนโค้ด คุณจะต้องนำเข้าเนมสเปซที่จำเป็นก่อน ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
using Aspose.Words;
```

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสารของคุณ

ก่อนอื่น คุณต้องกำหนดว่าเอกสารของคุณอยู่ที่ใด นี่เป็นสิ่งสำคัญเนื่องจากคุณจะโหลดและบันทึกเอกสารจากไดเร็กทอรีนี้ ให้คิดว่าเป็นการตั้งค่า GPS ก่อนการเดินทาง

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการโหลด

ถัดไป คุณต้องกำหนดค่าตัวเลือกการโหลด นี่คือจุดที่ความมหัศจรรย์เกิดขึ้น! ด้วยการตั้งค่าเวอร์ชัน MS Word ในตัวเลือกการโหลด คุณกำลังบอก Aspose.Words ว่า Word เวอร์ชันใดที่จะจำลองเมื่อโหลดเอกสาร

```csharp
// กำหนดค่าตัวเลือกการโหลดด้วยคุณสมบัติ "ตั้งค่าเวอร์ชัน MS Word"
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

ลองนึกภาพคุณอยู่ที่ร้านกาแฟที่กำลังตัดสินใจว่าจะดื่มเครื่องดื่มชนิดใด ในทำนองเดียวกัน คุณจะเลือกเวอร์ชันของ Word ที่คุณต้องการใช้งาน

## ขั้นตอนที่ 3: โหลดเอกสาร

ตอนนี้คุณได้ตั้งค่าตัวเลือกการโหลดแล้ว ก็ถึงเวลาโหลดเอกสารของคุณ ขั้นตอนนี้คล้ายกับการเปิดเอกสารใน Word เวอร์ชันใดเวอร์ชันหนึ่ง

```csharp
// โหลดเอกสารด้วย MS Word เวอร์ชันที่ระบุ
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

สุดท้ายนี้ เมื่อเอกสารของคุณถูกโหลดและการปรับแต่งตามที่ต้องการเสร็จสิ้นแล้ว คุณก็จะบันทึกมันไว้ เหมือนกับการกดปุ่มบันทึกหลังจากทำการเปลี่ยนแปลงใน Word

```csharp
// บันทึกเอกสาร
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## บทสรุป

การตั้งค่าเวอร์ชัน MS Word ใน Aspose.Words สำหรับ .NET นั้นตรงไปตรงมาเมื่อคุณแยกย่อยออกเป็นขั้นตอนที่สามารถจัดการได้ ด้วยการกำหนดค่าตัวเลือกการโหลด การโหลดเอกสารของคุณ และการบันทึก คุณมั่นใจได้ว่าเอกสารของคุณจะได้รับการจัดการตรงตามที่คุณต้องการ คู่มือนี้เป็นแนวทางที่ชัดเจนในการบรรลุเป้าหมายดังกล่าว ขอให้มีความสุขในการเขียนโค้ด!

## คำถามที่พบบ่อย

### ฉันสามารถตั้งค่าเวอร์ชันอื่นที่ไม่ใช่ Word 2010 ได้หรือไม่
 ได้ คุณสามารถตั้งค่าเวอร์ชันต่างๆ เช่น Word 2007, Word 2013 ฯลฯ ได้โดยการเปลี่ยน`MsWordVersion` คุณสมบัติ.

### Aspose.Words เข้ากันได้กับ .NET Core หรือไม่
อย่างแน่นอน! Aspose.Words รองรับ .NET Framework, .NET Core และ .NET 5+

### ฉันต้องมีใบอนุญาตเพื่อใช้ Aspose.Words หรือไม่
 คุณสามารถใช้รุ่นทดลองใช้ฟรีได้ แต่คุณจะต้องมีใบอนุญาตจึงจะมีคุณสมบัติครบถ้วนได้[รับใบอนุญาตชั่วคราวที่นี่](https://purchase.aspose.com/temporary-license/).

### ฉันสามารถจัดการคุณสมบัติอื่นๆ ของเอกสาร Word โดยใช้ Aspose.Words ได้หรือไม่
ใช่ Aspose.Words เป็นไลบรารีที่ครอบคลุมซึ่งช่วยให้คุณสามารถจัดการเอกสาร Word ได้เกือบทุกด้าน

### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน
 ตรวจสอบ[เอกสารประกอบ](https://reference.aspose.com/words/net/) สำหรับตัวอย่างเพิ่มเติมและข้อมูลโดยละเอียด
