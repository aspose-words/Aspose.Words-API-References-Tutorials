---
title: ลบการป้องกันเอกสารในเอกสาร Word
linktitle: ลบการป้องกันเอกสารในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีลบการป้องกันออกจากเอกสาร Word โดยใช้ Aspose.Words for .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อยกเลิกการปกป้องเอกสารของคุณอย่างง่ายดาย
type: docs
weight: 10
url: /th/net/document-protection/remove-document-protection/
---

## การแนะนำ

เฮ้! เคยพบว่าตัวเองถูกล็อคไม่ให้ใช้งานเอกสาร Word ของคุณเองเนื่องจากการตั้งค่าการป้องกันหรือไม่? เหมือนพยายามเปิดประตูด้วยกุญแจผิด หงุดหงิดใช่ไหม? แต่อย่ากลัว! ด้วย Aspose.Words สำหรับ .NET คุณสามารถลบการป้องกันออกจากเอกสาร Word ของคุณได้อย่างง่ายดาย บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน เพื่อให้มั่นใจว่าคุณสามารถควบคุมเอกสารของคุณได้อย่างเต็มที่ในเวลาไม่นาน มาดำน้ำกันเถอะ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะพูดถึงโค้ด เราต้องแน่ใจว่าเรามีทุกสิ่งที่เราต้องการ:

1.  Aspose.Words สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Words สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/net/).
2. สภาพแวดล้อมการพัฒนา: สภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio
3. ความรู้พื้นฐานของ C#: การทำความเข้าใจพื้นฐานของ C# จะช่วยให้คุณปฏิบัติตามได้

## นำเข้าเนมสเปซ

ก่อนที่จะเขียนโค้ดใดๆ ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Words.Protection;
```

เนมสเปซเหล่านี้จะมอบเครื่องมือทั้งหมดที่เราต้องการในการจัดการเอกสาร Word

## ขั้นตอนที่ 1: โหลดเอกสาร

เอาล่ะ มาเริ่มกันเลย ขั้นตอนแรกคือโหลดเอกสารที่คุณต้องการยกเลิกการป้องกัน นี่คือที่ที่เราบอกโปรแกรมของเราว่าเรากำลังจัดการกับเอกสารใด

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ProtectedDocument.docx");
```

 ที่นี่ เราระบุเส้นทางไปยังไดเร็กทอรีที่มีเอกสารของเรา แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: ลบการป้องกันโดยไม่ต้องใช้รหัสผ่าน

บางครั้ง เอกสารจะได้รับการป้องกันโดยไม่ต้องใช้รหัสผ่าน ในกรณีเช่นนี้ เราสามารถลบการป้องกันออกได้ด้วยโค้ดเพียงบรรทัดเดียว

```csharp
// ลบการป้องกันโดยไม่ต้องใช้รหัสผ่าน
doc.Unprotect();
```

แค่นั้นแหละ! ขณะนี้เอกสารของคุณไม่มีการป้องกัน แต่ถ้ามีรหัสผ่านล่ะ?

## ขั้นตอนที่ 3: ลบการป้องกันด้วยรหัสผ่าน

หากเอกสารของคุณได้รับการป้องกันด้วยรหัสผ่าน คุณจะต้องระบุรหัสผ่านนั้นเพื่อเอาการป้องกันออก นี่คือวิธีการ:

```csharp
// ลบการป้องกันด้วยรหัสผ่านที่ถูกต้อง
doc.Unprotect("currentPassword");
```

 แทนที่`"currentPassword"` ด้วยรหัสผ่านจริงที่ใช้ป้องกันเอกสาร เมื่อคุณระบุรหัสผ่านที่ถูกต้อง การป้องกันจะถูกยกเลิก

## ขั้นตอนที่ 4: เพิ่มและลบการป้องกัน

สมมติว่าคุณต้องการลบการป้องกันปัจจุบันออกแล้วเพิ่มการป้องกันใหม่ สิ่งนี้มีประโยชน์สำหรับการรีเซ็ตการป้องกันเอกสาร ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
// เพิ่มการป้องกันใหม่
doc.Protect(ProtectionType.ReadOnly, "newPassword");

// ลบการป้องกันใหม่
doc.Unprotect("newPassword");
```

 ในโค้ดข้างต้น เราจะเพิ่มการป้องกันใหม่ด้วยรหัสผ่านก่อน`"newPassword"`แล้วลบออกทันทีโดยใช้รหัสผ่านเดียวกัน

## ขั้นตอนที่ 5: บันทึกเอกสาร

สุดท้ายนี้ หลังจากทำการเปลี่ยนแปลงที่จำเป็นทั้งหมดแล้ว อย่าลืมบันทึกเอกสารของคุณ นี่คือรหัสสำหรับบันทึกเอกสาร:

```csharp
// บันทึกเอกสาร
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

วิธีนี้จะบันทึกเอกสารที่ไม่มีการป้องกันของคุณในไดเร็กทอรีที่ระบุ

## บทสรุป

และคุณก็ได้แล้ว! การลบการป้องกันออกจากเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เป็นเรื่องง่าย ไม่ว่าจะเป็นเอกสารที่มีการป้องกันด้วยรหัสผ่านหรือไม่ก็ตาม Aspose.Words มอบความยืดหยุ่นในการจัดการการป้องกันเอกสารได้อย่างง่ายดาย ตอนนี้คุณสามารถปลดล็อคเอกสารของคุณและควบคุมได้อย่างเต็มที่ด้วยโค้ดเพียงไม่กี่บรรทัด

## คำถามที่พบบ่อย

### จะเกิดอะไรขึ้นหากฉันระบุรหัสผ่านผิด?

หากคุณระบุรหัสผ่านไม่ถูกต้อง Aspose.Words จะส่งข้อยกเว้น ตรวจสอบให้แน่ใจว่าคุณใช้รหัสผ่านที่ถูกต้องเพื่อลบการป้องกัน

### ฉันสามารถลบการป้องกันออกจากเอกสารหลายฉบับพร้อมกันได้หรือไม่

ได้ คุณสามารถวนซ้ำรายการเอกสารและใช้ตรรกะการป้องกันแบบเดียวกันกับแต่ละรายการได้

### Aspose.Words สำหรับ .NET ฟรีหรือไม่

 Aspose.Words สำหรับ .NET เป็นไลบรารีแบบชำระเงิน แต่คุณสามารถทดลองใช้ได้ฟรี ตรวจสอบ[ทดลองใช้ฟรี](https://releases.aspose.com/)-

### การป้องกันประเภทอื่นใดที่ฉันสามารถนำไปใช้กับเอกสาร Word ได้

Aspose.Words ช่วยให้คุณสามารถใช้การป้องกันประเภทต่างๆ ได้ เช่น ReadOnly, AllowOnlyRevisions, AllowOnlyComments และ AllowOnlyFormFields

### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Words สำหรับ .NET ได้ที่ไหน

 คุณสามารถดูเอกสารรายละเอียดได้ที่[หน้าเอกสาร Aspose.Words สำหรับ .NET](https://reference.aspose.com/words/net/).
