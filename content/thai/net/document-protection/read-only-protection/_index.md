---
title: การป้องกันแบบอ่านอย่างเดียวในเอกสาร Word
linktitle: การป้องกันแบบอ่านอย่างเดียวในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีปกป้องเอกสาร Word ของคุณโดยใช้การป้องกันแบบอ่านอย่างเดียวโดยใช้ Aspose.Words สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเรา
type: docs
weight: 10
url: /th/net/document-protection/read-only-protection/
---
## การแนะนำ

เมื่อพูดถึงการจัดการเอกสาร Word มีหลายครั้งที่คุณต้องทำให้เป็นแบบอ่านอย่างเดียวเพื่อปกป้องเนื้อหา ไม่ว่าจะเป็นการแบ่งปันข้อมูลสำคัญโดยไม่ต้องเสี่ยงต่อการแก้ไขโดยไม่ตั้งใจ หรือเพื่อรับรองความสมบูรณ์ของเอกสารทางกฎหมาย การป้องกันแบบอ่านอย่างเดียวถือเป็นคุณสมบัติที่มีคุณค่า ในบทช่วยสอนนี้ เราจะสำรวจวิธีการใช้การป้องกันแบบอ่านอย่างเดียวในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายแต่ละขั้นตอนโดยละเอียดและน่าสนใจ เพื่อให้มั่นใจว่าคุณสามารถปฏิบัติตามได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด มีข้อกำหนดเบื้องต้นบางประการที่คุณต้องมี:

1.  Aspose.Words for .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Words for .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[กำหนดหน้าการเผยแพร่](https://releases.aspose.com/words/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาโดยติดตั้ง .NET Visual Studio เป็นตัวเลือกที่ดี
3. ความเข้าใจพื้นฐานของ C#: บทช่วยสอนนี้ถือว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ

ขั้นแรก ตรวจสอบให้แน่ใจว่าเราได้นำเข้าเนมสเปซที่จำเป็นแล้ว นี่เป็นสิ่งสำคัญเนื่องจากช่วยให้เราสามารถเข้าถึงคลาสและวิธีการที่เราต้องการจาก Aspose.Words สำหรับ .NET

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## ขั้นตอนที่ 1: ตั้งค่าเอกสาร

ในขั้นตอนนี้ เราจะสร้างเอกสารใหม่และตัวสร้างเอกสาร นี่เป็นรากฐานสำหรับการดำเนินงานของเรา

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// เขียนข้อความลงในเอกสาร
builder.Write("Open document as read-only");
```

คำอธิบาย:

- เราเริ่มต้นด้วยการกำหนดเส้นทางไดเรกทอรีที่จะบันทึกเอกสาร
-  ใหม่`Document` วัตถุถูกสร้างขึ้นและ`DocumentBuilder` มีความเกี่ยวข้องกับมัน
- เมื่อใช้ตัวสร้าง เราจะเพิ่มบรรทัดข้อความง่ายๆ ลงในเอกสาร

## ขั้นตอนที่ 2: ตั้งรหัสผ่านป้องกันการเขียน

ต่อไปเราต้องตั้งรหัสผ่านเพื่อป้องกันการเขียน รหัสผ่านนี้มีความยาวได้สูงสุด 15 อักขระ

```csharp
//ป้อนรหัสผ่านที่มีความยาวสูงสุด 15 อักขระ
doc.WriteProtection.SetPassword("MyPassword");
```

คำอธิบาย:

-  ที่`SetPassword` วิธีการถูกเรียกใช้บน`WriteProtection` คุณสมบัติของเอกสาร
- เราให้รหัสผ่าน ("MyPassword" ในกรณีนี้) ซึ่งจะต้องใช้ในการลบการป้องกัน

## ขั้นตอนที่ 3: เปิดใช้งานคำแนะนำแบบอ่านอย่างเดียว

ในขั้นตอนนี้ เราแนะนำให้เอกสารเป็นแบบอ่านอย่างเดียว ซึ่งหมายความว่าเมื่อเปิดเอกสาร ระบบจะแจ้งให้ผู้ใช้เปิดเอกสารในโหมดอ่านอย่างเดียว

```csharp
// ทำให้เอกสารเป็นแบบอ่านอย่างเดียวแนะนำ
doc.WriteProtection.ReadOnlyRecommended = true;
```

คำอธิบาย:

-  ที่`ReadOnlyRecommended` คุณสมบัติถูกตั้งค่าเป็น`true`.
- การดำเนินการนี้จะแจ้งให้ผู้ใช้เปิดเอกสารในโหมดอ่านอย่างเดียว แม้ว่าผู้ใช้สามารถเลือกที่จะเพิกเฉยต่อคำแนะนำได้ก็ตาม

## ขั้นตอนที่ 4: ใช้การป้องกันแบบอ่านอย่างเดียว

สุดท้ายนี้ เราใช้การป้องกันแบบอ่านอย่างเดียวกับเอกสาร ขั้นตอนนี้บังคับใช้การป้องกัน

```csharp
// ใช้การป้องกันการเขียนเป็นแบบอ่านอย่างเดียว
doc.Protect(ProtectionType.ReadOnly);
```

คำอธิบาย:

-  ที่`Protect` วิธีการถูกเรียกในเอกสารด้วย`ProtectionType.ReadOnly` เป็นข้อโต้แย้ง
- วิธีการนี้บังคับใช้การป้องกันแบบอ่านอย่างเดียว ป้องกันการแก้ไขเอกสารโดยไม่ต้องใช้รหัสผ่าน

## ขั้นตอนที่ 5: บันทึกเอกสาร

ขั้นตอนสุดท้ายคือการบันทึกเอกสารโดยใช้การตั้งค่าการป้องกันที่ใช้

```csharp
// บันทึกเอกสารที่ได้รับการป้องกัน
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

คำอธิบาย:

-  ที่`Save` มีการเรียกใช้เมธอดบนเอกสาร โดยระบุพาธและชื่อของไฟล์
- เอกสารจะถูกบันทึกโดยมีการป้องกันแบบอ่านอย่างเดียว

## บทสรุป

และคุณก็ได้แล้ว! คุณสร้างเอกสาร Word แบบอ่านอย่างเดียวที่ได้รับการป้องกันโดยใช้ Aspose.Words สำหรับ .NET สำเร็จแล้ว คุณสมบัตินี้ช่วยให้แน่ใจว่าเนื้อหาของเอกสารของคุณยังคงสภาพเดิมและไม่มีการเปลี่ยนแปลง เพิ่มระดับการรักษาความปลอดภัยเพิ่มเติม ไม่ว่าคุณจะแชร์ข้อมูลที่ละเอียดอ่อนหรือเอกสารทางกฎหมาย การป้องกันแบบอ่านอย่างเดียวคือเครื่องมือที่ต้องมีในคลังแสงการจัดการเอกสารของคุณ

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข แปลง และปกป้องเอกสาร Word โดยทางโปรแกรมโดยใช้ C# หรือภาษา .NET อื่นๆ

### ฉันสามารถลบการป้องกันแบบอ่านอย่างเดียวออกจากเอกสารได้หรือไม่
 ใช่ คุณสามารถลบการป้องกันแบบอ่านอย่างเดียวได้โดยใช้`Unprotect` วิธีการและระบุรหัสผ่านที่ถูกต้อง

### รหัสผ่านที่ตั้งไว้ในเอกสารมีการเข้ารหัสหรือไม่
ใช่ Aspose.Words เข้ารหัสรหัสผ่านเพื่อความปลอดภัยของเอกสารที่ได้รับการป้องกัน

### ฉันสามารถใช้การป้องกันประเภทอื่นโดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่
ใช่ Aspose.Words สำหรับ .NET รองรับการป้องกันหลายประเภท รวมถึงการอนุญาตเฉพาะความคิดเห็น การกรอกแบบฟอร์ม หรือการติดตามการเปลี่ยนแปลง

### มีการทดลองใช้ฟรีสำหรับ Aspose.Words สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[กำหนดหน้าการเผยแพร่](https://releases.aspose.com/).