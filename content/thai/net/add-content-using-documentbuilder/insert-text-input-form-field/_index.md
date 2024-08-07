---
title: แทรกฟิลด์แบบฟอร์มป้อนข้อความในเอกสาร Word
linktitle: แทรกฟิลด์แบบฟอร์มป้อนข้อความในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกฟิลด์แบบฟอร์มป้อนข้อความในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET พร้อมบทช่วยสอนทีละขั้นตอนนี้ เหมาะสำหรับการสร้างแบบฟอร์มเชิงโต้ตอบ
type: docs
weight: 10
url: /th/net/add-content-using-documentbuilder/insert-text-input-form-field/
---
## การแนะนำ

ในบทช่วยสอนนี้ เรากำลังเจาะลึกเข้าไปในโลกของ Aspose.Words สำหรับ .NET เพื่อเรียนรู้วิธีแทรกฟิลด์แบบฟอร์มป้อนข้อความในเอกสาร Word รัดเข็มขัดไว้ เพราะเรากำลังจะเริ่มการเดินทางที่จะทำให้งานเอกสารอัตโนมัติของคุณเป็นเรื่องง่าย ไม่ว่าคุณกำลังสร้างแบบฟอร์ม เทมเพลต หรือเอกสารเชิงโต้ตอบ การเรียนรู้ทักษะนี้จะยกระดับแอปพลิเคชัน .NET ของคุณไปสู่อีกระดับ

### ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม มีบางสิ่งที่คุณต้องการ:

1.  Aspose.Words สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Words สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก[กำหนดหน้าการเผยแพร่](https://releases.aspose.com/words/net/).
2. สภาพแวดล้อมการพัฒนา: สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Visual Studio
3. ความเข้าใจพื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# และกรอบงาน .NET
4.  ใบอนุญาตชั่วคราว (ไม่บังคับ): หากคุณกำลังประเมิน Aspose.Words คุณอาจต้องการได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อหลีกเลี่ยงข้อจำกัดใดๆ

## นำเข้าเนมสเปซ

ขั้นแรก เรามาเริ่มขั้นตอนโดยการนำเข้าเนมสเปซที่จำเป็น สิ่งนี้จะทำให้เราใช้คลาสและวิธีการของ Aspose.Words ได้อย่างง่ายดาย

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
```

ตอนนี้ เรามาแบ่งกระบวนการออกเป็นขั้นตอนง่ายๆ ที่เข้าใจง่าย แต่ละขั้นตอนมีความสำคัญ ดังนั้นโปรดปฏิบัติตามอย่างใกล้ชิด

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

ก่อนที่เราจะเจาะลึกโค้ด คุณต้องระบุเส้นทางไปยังไดเร็กทอรีเอกสารของคุณก่อน นี่คือที่ที่เอกสาร Word ที่คุณสร้างขึ้นจะถูกบันทึก

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารใหม่

 ต่อไปเราต้องสร้างอินสแตนซ์ใหม่ของ`Document` ระดับ. นี่แสดงถึงเอกสาร Word ที่เราจะใช้งาน

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 3: เริ่มต้น DocumentBuilder

 ที่`DocumentBuilder` class เป็นเครื่องมือหลักของเราในการเพิ่มเนื้อหาลงในเอกสาร ให้คิดว่ามันเป็นปากกาที่เขียนบนผืนผ้าใบเอกสาร Word

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 4: แทรกฟิลด์แบบฟอร์มป้อนข้อความ

 นี่คือจุดที่ความมหัศจรรย์เกิดขึ้น เราจะใช้`InsertTextInput` วิธีการของ`DocumentBuilder` คลาสเพื่อเพิ่มฟิลด์แบบฟอร์มป้อนข้อความ ช่องแบบฟอร์มนี้จะอนุญาตให้ผู้ใช้ป้อนข้อความลงในเอกสาร

```csharp
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);
```

- ชื่อ: "TextInput" - นี่คือชื่อของฟิลด์แบบฟอร์ม
-  พิมพ์:`TextFormFieldType.Regular` เป็นการระบุว่าฟิลด์แบบฟอร์มเป็นการป้อนข้อความปกติ
- ข้อความเริ่มต้น: "" - นี่คือข้อความเริ่มต้นที่แสดงในฟิลด์แบบฟอร์ม (ว่างเปล่าในกรณีนี้)
- ค่า: "Hello" - ค่าเริ่มต้นของฟิลด์แบบฟอร์ม
- ความยาวสูงสุด: 0 - เป็นการไม่จำกัดความยาวของอินพุต

## ขั้นตอนที่ 5: บันทึกเอกสาร

สุดท้ายเราจำเป็นต้องบันทึกเอกสารลงในไดเร็กทอรีที่ระบุ สิ่งนี้จะสร้างไฟล์ .docx พร้อมด้วยฟิลด์แบบฟอร์มป้อนข้อความที่แทรกไว้

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

## บทสรุป

และคุณก็ได้แล้ว! คุณได้แทรกฟิลด์แบบฟอร์มป้อนข้อความลงในเอกสาร Word สำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET นี่เป็นเพียงส่วนเล็กของภูเขาน้ำแข็ง ด้วย Aspose.Words คุณสามารถทำให้งานการประมวลผลเอกสารของคุณเป็นอัตโนมัติและปรับปรุงได้หลายวิธี ตั้งแต่การสร้างเทมเพลตที่ซับซ้อนไปจนถึงการสร้างแบบฟอร์มเชิงโต้ตอบ ความเป็นไปได้ไม่มีที่สิ้นสุด

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words สำหรับ .NET เป็นไลบรารีการประมวลผลเอกสารที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และแปลงเอกสาร Word โดยทางโปรแกรมได้

### ฉันสามารถใช้ Aspose.Words ได้ฟรีหรือไม่
Aspose.Words เสนอเวอร์ชันทดลองใช้ฟรีพร้อมข้อจำกัดบางประการ เพื่อการใช้งานเต็มรูปแบบ คุณสามารถซื้อใบอนุญาตหรือรับใบอนุญาตชั่วคราวเพื่อการประเมินได้

### ช่องแบบฟอร์มป้อนข้อความมีไว้เพื่ออะไร?
ช่องแบบฟอร์มป้อนข้อความใช้ในเอกสาร Word เพื่อให้ผู้ใช้สามารถป้อนข้อความลงในพื้นที่ที่กำหนดไว้ล่วงหน้า ทำให้เหมาะสำหรับแบบฟอร์มและเทมเพลต

### ฉันจะปรับแต่งลักษณะที่ปรากฏของฟิลด์แบบฟอร์มได้อย่างไร
 คุณสามารถปรับแต่งลักษณะที่ปรากฏของฟิลด์แบบฟอร์มได้โดยใช้คุณสมบัติต่างๆ ของ`DocumentBuilder` คลาส เช่น แบบอักษร ขนาด และการจัดตำแหน่ง

### ฉันจะหาบทช่วยสอนเพิ่มเติมเกี่ยวกับ Aspose.Words สำหรับ .NET ได้ที่ไหน
 คุณสามารถค้นหาบทช่วยสอนและเอกสารเพิ่มเติมได้ที่[หน้าเอกสาร Aspose.Words สำหรับ .NET](https://reference.aspose.com/words/net/).
