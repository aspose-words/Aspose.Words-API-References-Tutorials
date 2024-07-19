---
title: แทรกฟิลด์ที่ซ้อนกัน
linktitle: แทรกฟิลด์ที่ซ้อนกัน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกฟิลด์ที่ซ้อนกันลงในเอกสาร Word ของคุณด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-fields/insert-nested-fields/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่าง ซึ่งใช้ฟีเจอร์ "แทรกฟิลด์ที่ซ้อนกัน" ของ Aspose.Words สำหรับ .NET อย่าลืมปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในโค้ดที่ให้มา คุณต้องระบุไดเร็กทอรีของเอกสารของคุณ แทนที่ค่า "YOUR DOCUMENT DIRECTORY" ด้วยเส้นทางที่เหมาะสมไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสารและ DocumentBuilder

เราเริ่มต้นด้วยการสร้างเอกสารใหม่และเตรียมใช้งาน DocumentBuilder

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: การแทรกตัวแบ่งหน้า

เราใช้การวนซ้ำเพื่อแทรกตัวแบ่งหน้าหลายหน้าลงในเอกสาร

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## ขั้นตอนที่ 4: ย้ายไปที่ส่วนท้าย

 เราใช้`MoveToHeaderFooter()` วิธีการของ DocumentBuilder เพื่อย้ายเคอร์เซอร์ไปที่ส่วนท้ายหลัก

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## ขั้นตอนที่ 5: การแทรกฟิลด์ที่ซ้อนกัน

 เราใช้ DocumentBuilder's`InsertField()` วิธีการแทรกฟิลด์ที่ซ้อนกันไว้ในส่วนท้าย

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 ในที่สุดเราก็เรียกว่า`Update()` วิธีการอัพเดตสนาม

```csharp
field. Update();
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกฟิลด์ที่ซ้อนกันด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสารและ DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกตัวแบ่งหน้า
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// ย้ายไปที่ส่วนท้าย
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// แทรกฟิลด์ที่ซ้อนกัน
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// อัพเดทสนามครับ.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

ในตัวอย่างนี้ เราสร้างเอกสารใหม่ แทรกตัวแบ่งหน้า ย้ายเคอร์เซอร์ไปที่ส่วนท้าย จากนั้นแทรกฟิลด์ที่ซ้อนกันในส่วนท้าย

### คำถามที่พบบ่อย

#### ถาม: ฉันจะแทรกฟิลด์ที่ซ้อนกันในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการแทรกฟิลด์ที่ซ้อนกันในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:

1. รับย่อหน้าที่คุณต้องการแทรกเขตข้อมูลที่ซ้อนกัน
2.  สร้างก`FieldStart` วัตถุสำหรับฟิลด์พาเรนต์
3.  เพิ่มฟิลด์ย่อยโดยใช้`FieldStart.NextSibling` วิธีการผ่านที่สอดคล้องกัน`FieldStart` วัตถุเป็นพารามิเตอร์

#### ถาม: การใช้ฟิลด์ที่ซ้อนกันในเอกสาร Word กับ Aspose.Words สำหรับ .NET มีประโยชน์อย่างไร

ตอบ: การใช้ฟิลด์ที่ซ้อนกันมีข้อดีหลายประการในเอกสาร Word ที่มี Aspose.Words สำหรับ .NET ซึ่งช่วยให้มีความยืดหยุ่นมากขึ้นในการสร้างเทมเพลตเอกสารแบบไดนามิก โดยอนุญาตให้แทรกค่าตัวแปรและการคำนวณลงในฟิลด์ที่ซ้อนกัน ฟิลด์ที่ซ้อนกันยังอำนวยความสะดวกในการสร้างเนื้อหาอัตโนมัติ เช่น การสร้างสารบัญ หมายเลขหน้า ฯลฯ

#### ถาม: ฉันสามารถมีฟิลด์ที่ซ้อนกันหลายระดับในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET ได้หรือไม่

ตอบ: ได้ เป็นไปได้ที่จะมีฟิลด์ที่ซ้อนกันหลายระดับในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET คุณสามารถสร้างลำดับชั้นที่ซับซ้อนของฟิลด์ที่ซ้อนกันได้โดยใช้`FieldStart.NextSibling` วิธีการเพิ่มฟิลด์ลูกลงในฟิลด์พาเรนต์ที่มีอยู่

#### ถาม: ฉันจะปรับแต่งคุณสมบัติของฟิลด์ที่ซ้อนกันในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการปรับแต่งคุณสมบัติของฟิลด์ที่ซ้อนกันในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET คุณสามารถเข้าถึงฟิลด์ที่เกี่ยวข้องได้`FieldStart` วัตถุและแก้ไขคุณสมบัติตามความจำเป็น คุณสามารถตั้งค่าตัวเลือกการจัดรูปแบบ ค่า การคำนวณ ฯลฯ ของฟิลด์ที่ซ้อนกันเพื่อให้ได้ผลลัพธ์ที่ต้องการ

#### ถาม: การแทรกฟิลด์ที่ซ้อนกันจะส่งผลต่อประสิทธิภาพของเอกสาร Word ด้วย Aspose.Words สำหรับ .NET หรือไม่

ตอบ: การแทรกฟิลด์ที่ซ้อนกันอาจส่งผลต่อประสิทธิภาพการทำงานของเอกสาร Word ด้วย Aspose.Words สำหรับ .NET โดยเฉพาะอย่างยิ่งหากเอกสารประกอบด้วยฟิลด์ที่ซ้อนกันจำนวนมากหรือลำดับชั้นที่ซับซ้อน ขอแนะนำให้ปรับโค้ดให้เหมาะสมโดยหลีกเลี่ยงการดำเนินการที่ไม่จำเป็นหรือซ้ำซ้อนในฟิลด์ที่ซ้อนกันเพื่อปรับปรุงประสิทธิภาพ