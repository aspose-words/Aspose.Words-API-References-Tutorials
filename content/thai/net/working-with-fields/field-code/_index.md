---
title: รหัสฟิลด์
linktitle: รหัสฟิลด์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการรับโค้ดฟิลด์และฟิลด์ส่งผลให้เอกสาร Word ของคุณด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fields/field-code/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่าง ซึ่งใช้ฟีเจอร์ "รับโค้ดฟิลด์" ของ Aspose.Words สำหรับ .NET อย่าลืมปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในโค้ดที่ให้มา คุณต้องระบุไดเร็กทอรีของเอกสารของคุณ แทนที่ค่า "YOUR DOCUMENT DIRECTORY" ด้วยเส้นทางที่เหมาะสมไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ขั้นตอนแรกคือการอัปโหลดเอกสารที่คุณต้องการรับรหัสฟิลด์

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

อย่าลืมแทนที่ "Hyperlinks.docx" ด้วยชื่อไฟล์ของคุณเอง

## ขั้นตอนที่ 3: เรียกดูฟิลด์เอกสาร

 เราใช้ก`foreach`วนซ้ำเพื่อวนซ้ำทุกฟิลด์ที่มีอยู่ในเอกสาร

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 ในการวนซ้ำแต่ละครั้ง เราได้รับโค้ดฟิลด์โดยใช้`GetFieldCode()` วิธี. เรายังเก็บผลลัพธ์ของฟิลด์ไว้ในตัวแปรด้วย

### ตัวอย่างซอร์สโค้ดสำหรับรับโค้ดฟิลด์ด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Hyperlinks.docx");

// วนซ้ำช่องเอกสาร
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // ดำเนินการบางอย่างกับโค้ดของฟิลด์และผลลัพธ์
}
```

ในตัวอย่างนี้ เราโหลดเอกสารแล้ววนไปตามฟิลด์ทั้งหมดที่มีอยู่ในเอกสาร ในการวนซ้ำแต่ละครั้ง เราได้รับโค้ดและผลลัพธ์ของฟิลด์ คุณสามารถเพิ่มตรรกะของคุณเองเพื่อประมวลผลโค้ดและฟิลด์ผลลัพธ์ได้ตามต้องการ

นี่เป็นการสรุปคำแนะนำของเราเกี่ยวกับการใช้ฟีเจอร์ "รับโค้ดฟิลด์" กับ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: ฉันจะแทรกฟิลด์ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการแทรกฟิลด์ลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`DocumentBuilder.InsertField` วิธีการระบุรหัสฟิลด์ที่เหมาะสม ตัวอย่างเช่นคุณสามารถใช้`builder.InsertField("MERGEFIELD CustomerName")`เพื่อแทรกเขตข้อมูลผสานลงในเอกสาร

#### ถาม: ฉันจะอัปเดตฟิลด์ในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการอัปเดตฟิลด์เอกสารโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้`Document.UpdateFields` วิธี. การดำเนินการนี้จะอัปเดตฟิลด์ทั้งหมดที่มีอยู่ในเอกสาร เช่น ฟิลด์ผสาน ฟิลด์วันที่ ฯลฯ

#### ถาม: ฉันจะดึงค่าของฟิลด์เฉพาะใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการดึงค่าของฟิลด์เฉพาะใน Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`Field.GetResult` วิธีการโดยระบุดัชนีของฟิลด์ใน`Document.Range.Fields` ของสะสม. ตัวอย่างเช่นคุณสามารถใช้`string value = document.Range.Fields[0].GetResult()` เพื่อดึงค่าของฟิลด์แรกในเอกสาร

#### ถาม: ฉันจะลบฟิลด์ออกจากเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการลบฟิลด์ออกจากเอกสารโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`Field.Remove` วิธีการระบุ`Field` วัตถุที่คุณต้องการลบ นี่จะเป็นการลบฟิลด์ออกจากเอกสาร