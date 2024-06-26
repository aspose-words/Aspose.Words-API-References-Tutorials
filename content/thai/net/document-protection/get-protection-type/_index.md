---
title: รับประเภทการป้องกันในเอกสาร Word
linktitle: รับประเภทการป้องกันในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้ฟังก์ชันรับประเภทการป้องกันในเอกสาร word ของ Aspose.Words สำหรับ .NET เพื่อกำหนดประเภทการป้องกันของเอกสาร
type: docs
weight: 10
url: /th/net/document-protection/get-protection-type/
---
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนที่อธิบายซอร์สโค้ด C# สำหรับฟีเจอร์รับประเภทการป้องกันของ Aspose.Words สำหรับ .NET ในบทความนี้ เราจะแสดงวิธีใช้ฟีเจอร์ที่มีประสิทธิภาพนี้เพื่อกำหนดประเภทการป้องกันของเอกสาร การป้องกันเอกสารถือเป็นสิ่งสำคัญเพื่อให้มั่นใจถึงการรักษาความลับและความสมบูรณ์ของไฟล์ของคุณ เราจะแนะนำคุณตลอดขั้นตอนที่จำเป็นในการรวม Aspose.Words สำหรับ .NET และใช้ฟีเจอร์รับประเภทการป้องกัน

## ขั้นตอนที่ 1: การโหลดเอกสาร

ขั้นตอนแรกในการใช้ฟีเจอร์รับประเภทการป้องกันคือการอัปโหลดเอกสารที่คุณต้องการใช้งาน คุณสามารถทำได้โดยใช้คลาสเอกสารที่ Aspose.Words สำหรับ .NET จัดให้ นี่คือโค้ดตัวอย่างในการโหลดเอกสารจากไฟล์:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไฟล์เอกสารของคุณ

## ขั้นตอนที่ 2: การดึงข้อมูลประเภทการป้องกัน

หลังจากอัปโหลดเอกสารแล้ว คุณสามารถใช้คุณสมบัติ ProtectionType ของออบเจ็กต์ Document เพื่อดึงข้อมูลประเภทการป้องกันที่ใช้กับเอกสารได้ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### ตัวอย่างซอร์สโค้ดสำหรับรับประเภทการป้องกันโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับฟังก์ชัน Get Protection Type โดยใช้ Aspose.Words สำหรับ .NET:

```csharp
Document doc = new Document(MyDir + "Document.docx");
ProtectionType protectionType = doc.ProtectionType;
```

## บทสรุป

ในบทความนี้ เราได้อธิบายวิธีการใช้ฟังก์ชันรับประเภทการป้องกันของ Aspose.Words สำหรับ .NET เพื่อกำหนดประเภทการป้องกันของเอกสาร เมื่อทำตามขั้นตอนที่อธิบายไว้ คุณจะสามารถรวมฟังก์ชันการทำงานนี้เข้ากับโปรเจ็กต์ C# ของคุณได้อย่างง่ายดาย และจัดการเอกสารที่ได้รับการป้องกันได้อย่างมีประสิทธิภาพ Aspose.Words สำหรับ .NET ให้ความยืดหยุ่นอย่างมาก

### คำถามที่พบบ่อย

#### ถาม: คุณสมบัติ ProtectionType ใน Aspose.Words สำหรับ .NET คืออะไร

 ตอบ:`ProtectionType` คุณสมบัติใน Aspose.Words สำหรับ .NET เป็นคุณสมบัติที่ช่วยให้คุณกำหนดประเภทของการป้องกันที่ใช้กับเอกสาร Word โดยให้ข้อมูลเกี่ยวกับระดับการป้องกันเอกสาร เช่น เอกสารได้รับการคุ้มครองสำหรับความคิดเห็น การแก้ไข แบบฟอร์ม หรือข้อจำกัดประเภทอื่นๆ หรือไม่

#### ถาม: ฉันจะดึงข้อมูลประเภทการป้องกันของเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการดึงข้อมูลประเภทการป้องกันของเอกสารโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:
1.  โหลดเอกสารโดยใช้`Document` ชั้นเรียน
2.  เข้าถึง`ProtectionType` ทรัพย์สินของ`Document` วัตถุเพื่อดึงข้อมูลประเภทการป้องกัน

#### ถาม: ฉันสามารถระบุได้ว่าเอกสารได้รับการป้องกันสำหรับแบบฟอร์มหรือเขตข้อมูลแบบฟอร์มโดยใช้คุณสมบัติ ProtectionType หรือไม่

 ตอบ: ได้ คุณสามารถระบุได้ว่าเอกสารได้รับการป้องกันสำหรับแบบฟอร์มหรือฟิลด์แบบฟอร์มหรือไม่โดยใช้`ProtectionType` คุณสมบัติใน Aspose.Words สำหรับ .NET หากตั้งค่าประเภทการป้องกันไว้เป็น`AllowOnlyFormFields`แสดงว่าเอกสารได้รับการป้องกัน และแก้ไขได้เฉพาะช่องแบบฟอร์มเท่านั้น

#### ถาม: คุณสมบัติ ProtectionType สามารถส่งคืนการป้องกันประเภทอื่นใดได้บ้าง

 ตอบ:`ProtectionType` คุณสมบัติใน Aspose.Words สำหรับ .NET สามารถส่งคืนการป้องกันได้หลายประเภท ได้แก่:
- `NoProtection`:เอกสารไม่ได้รับการป้องกัน
- `AllowOnlyRevisions`: เอกสารได้รับการป้องกัน และสามารถแก้ไขได้เท่านั้น
- `AllowOnlyComments`: เอกสารได้รับการป้องกัน และสามารถเพิ่มได้เฉพาะความคิดเห็นเท่านั้น
- `AllowOnlyFormFields`: เอกสารได้รับการป้องกัน และแก้ไขได้เฉพาะช่องแบบฟอร์มเท่านั้น
- `ReadOnly`: เอกสารได้รับการป้องกันและตั้งค่าเป็นแบบอ่านอย่างเดียว

#### ถาม: ฉันสามารถแก้ไขประเภทการป้องกันของเอกสารโดยใช้คุณสมบัติ ProtectionType ได้หรือไม่

 ตอบ: ไม่ใช่`ProtectionType`คุณสมบัติใน Aspose.Words สำหรับ .NET เป็นคุณสมบัติแบบอ่านอย่างเดียว ช่วยให้คุณสามารถดึงข้อมูลประเภทการป้องกันปัจจุบันของเอกสารได้ แต่ไม่มีวิธีการโดยตรงในการแก้ไขประเภทการป้องกัน หากต้องการแก้ไขประเภทการป้องกัน คุณต้องใช้วิธีการและคุณสมบัติอื่นที่มีอยู่ใน`Document` ชั้นเรียน เช่น`Protect` หรือ`Unprotect`.

#### ถาม: เป็นไปได้หรือไม่ที่จะปกป้องเอกสารที่มีการป้องกันหลายประเภทพร้อมกัน

ตอบ: ไม่ Aspose.Words สำหรับ .NET อนุญาตให้ใช้การป้องกันประเภทเดียวกับเอกสารในแต่ละครั้งเท่านั้น อย่างไรก็ตาม คุณสามารถรวมการป้องกันประเภทต่างๆ เข้าด้วยกันได้โดยเปิดใช้งานการป้องกัน ตั้งค่าประเภทหนึ่ง ปิดใช้งานการป้องกัน แล้วเปิดใช้งานอีกครั้งด้วยประเภทอื่น

