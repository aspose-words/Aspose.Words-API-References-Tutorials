---
title: รับรู้และการทดแทนภายในรูปแบบการแทนที่
linktitle: รับรู้และการทดแทนภายในรูปแบบการแทนที่
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้รูปแบบการแทนที่ด้วยการรับรู้และการทดแทนใน Aspose.Words สำหรับ .NET เพื่อจัดการเอกสาร Word
type: docs
weight: 10
url: /th/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้ฟังก์ชัน Recognize And Substitutions Within Replacement Patterns ใน Aspose.Words สำหรับไลบรารี .NET คุณสมบัตินี้ช่วยจดจำรูปแบบการค้นหาที่ซับซ้อนและดำเนินการทดแทนตามกลุ่มที่บันทึกไว้ระหว่างการจัดการเอกสาร

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: การสร้างเอกสารใหม่

ก่อนที่เราจะเริ่มใช้การจับคู่และการทดแทนในรูปแบบการแทนที่ เราจำเป็นต้องสร้างเอกสารใหม่โดยใช้ Aspose.Words สำหรับ .NET ซึ่งสามารถทำได้โดยการยกตัวอย่าง a`Document` วัตถุ:

```csharp
Document doc = new Document();
```

## ขั้นตอนที่ 2: แทรกข้อความลงในเอกสาร

 เมื่อได้เอกสารแล้ว เราก็สามารถแทรกข้อความโดยใช้ a`DocumentBuilder` วัตถุ. ในตัวอย่างของเรา เราใช้`Write` วิธีแทรกวลี "เจสันให้เงินแก่พอล" : :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## ขั้นตอนที่ 3: การรับรู้และการทดแทนในรูปแบบการแทนที่

 ตอนนี้เราจะใช้`Range.Replace` ฟังก์ชั่นเพื่อค้นหาข้อความและแทนที่โดยใช้นิพจน์ทั่วไปเพื่อจดจำรูปแบบเฉพาะ ในตัวอย่างของเรา เราใช้นิพจน์ทั่วไป`([A-z]+) gives money to ([A-z]+)` จดจำประโยคที่มีคนให้เงินกับคนอื่น เราใช้รูปแบบการทดแทน`$2 takes money from $1` เพื่อดำเนินการทดแทนโดยการกลับบทบาท การใช้งานของ`$1` และ`$2` หมายถึงกลุ่มที่ถูกจับโดยนิพจน์ทั่วไป:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### ตัวอย่างซอร์สโค้ดสำหรับการรับรู้และการทดแทนภายในรูปแบบการแทนที่โดยใช้ Aspose.Words สำหรับ .NET

ต่อไปนี้คือตัวอย่างซอร์สโค้ดแบบเต็มเพื่อแสดงการใช้การจับคู่และการทดแทนในรูปแบบการแทนที่ด้วย Aspose.Words สำหรับ .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้ฟีเจอร์ Recognize And Substitutions Within Replacement Patterns ของ Aspose.Words for .NET เราทำตามคำแนะนำทีละขั้นตอนเพื่อสร้างเอกสาร แทรกข้อความ ทำการค้นหาและแทนที่โดยใช้นิพจน์ทั่วไปและรูปแบบการแทนที่ตามกลุ่มที่บันทึกไว้ และจัดการเอกสาร

### คำถามที่พบบ่อย

#### ถาม: คุณลักษณะ "การรับรู้และการทดแทนภายในรูปแบบการแทนที่" ใน Aspose.Words สำหรับ .NET คืออะไร

ตอบ: คุณลักษณะ "การรับรู้และการแทนที่ภายในรูปแบบการแทนที่" ใน Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถจดจำรูปแบบการค้นหาที่ซับซ้อนโดยใช้นิพจน์ทั่วไป และดำเนินการทดแทนตามกลุ่มที่บันทึกไว้ระหว่างการจัดการเอกสาร ช่วยให้คุณสามารถแปลงข้อความที่ตรงกันแบบไดนามิกโดยการอ้างอิงกลุ่มที่บันทึกไว้ในรูปแบบการแทนที่

#### ถาม: ฉันจะสร้างเอกสารใหม่โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการสร้างเอกสารใหม่โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถยกตัวอย่าง a`Document` วัตถุ. นี่คือตัวอย่างโค้ด C# เพื่อสร้างเอกสารใหม่:

```csharp
Document doc = new Document();
```

#### ถาม: ฉันจะแทรกข้อความลงในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เมื่อคุณมีเอกสารแล้ว คุณสามารถแทรกข้อความโดยใช้ a`DocumentBuilder` วัตถุ. ตัวอย่างเช่น หากต้องการแทรกวลี "Jason ให้เงินแก่ Paul" คุณสามารถใช้`Write` วิธี:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### ถาม: ฉันจะค้นหาข้อความและแทนที่โดยใช้นิพจน์ทั่วไปใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการดำเนินการค้นหาข้อความและแทนที่โดยใช้นิพจน์ทั่วไปใน Aspose.Words สำหรับ .NET คุณสามารถใช้`Range.Replace` ทำงานพร้อมกับรูปแบบนิพจน์ทั่วไป คุณสามารถสร้าง`Regex` วัตถุที่มีรูปแบบที่ต้องการแล้วส่งต่อไปยัง`Replace` วิธี:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### ถาม: ฉันจะใช้กลุ่มที่บันทึกไว้ในรูปแบบการแทนที่ระหว่างการค้นหาข้อความและแทนที่ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการใช้กลุ่มที่บันทึกไว้ในรูปแบบการแทนที่ระหว่างการค้นหาข้อความและแทนที่ใน Aspose.Words สำหรับ .NET คุณสามารถเปิดใช้งาน`UseSubstitutions` ทรัพย์สินของ`FindReplaceOptions` วัตถุ. ซึ่งจะทำให้คุณสามารถอ้างอิงถึงกลุ่มที่บันทึกไว้ได้โดยใช้`$1`, `$2`ฯลฯ ในรูปแบบการแทนที่:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### ถาม: ซอร์สโค้ดตัวอย่างแสดงให้เห็นอะไรสำหรับฟีเจอร์ "รับรู้และการแทนที่ภายในรูปแบบการแทนที่" ใน Aspose.Words สำหรับ .NET

ตอบ: ซอร์สโค้ดตัวอย่างสาธิตการใช้คุณลักษณะ "รับรู้และการทดแทนภายในรูปแบบการแทนที่" ใน Aspose.Words สำหรับ .NET โดยจะแสดงวิธีการสร้างเอกสาร แทรกข้อความ ค้นหาข้อความและแทนที่โดยใช้นิพจน์ทั่วไป และใช้กลุ่มที่บันทึกไว้ในรูปแบบการแทนที่เพื่อแปลงข้อความที่ตรงกันแบบไดนามิก

#### ถาม: ฉันจะค้นหาข้อมูลเพิ่มเติมและตัวอย่างเกี่ยวกับการใช้นิพจน์ทั่วไปใน Aspose.Words สำหรับ .NET ได้ที่ไหน

ตอบ: สำหรับข้อมูลเพิ่มเติมและตัวอย่างเกี่ยวกับการใช้นิพจน์ทั่วไปใน Aspose.Words สำหรับ .NET คุณสามารถดูได้ที่[Aspose.Words สำหรับการอ้างอิง .NET API](https://reference.aspose.com/words/net/). เอกสารนี้จะให้คำอธิบายโดยละเอียดและตัวอย่างโค้ดสำหรับสถานการณ์ต่างๆ ที่เกี่ยวข้องกับนิพจน์ทั่วไปและการจัดการข้อความใน Aspose.Words สำหรับ .NET

#### ถาม: ฉันสามารถจัดการด้านอื่นๆ ของเอกสารตามกลุ่มที่บันทึกไว้ระหว่างการค้นหาและแทนที่ข้อความได้หรือไม่

ตอบ: ได้ คุณสามารถจัดการลักษณะอื่นๆ ของเอกสารตามกลุ่มที่บันทึกไว้ระหว่างการค้นหาและแทนที่ข้อความได้ นอกเหนือจากการแทนที่ข้อความแล้ว คุณยังสามารถแก้ไขการจัดรูปแบบ สไตล์ โครงสร้างเอกสาร และองค์ประกอบอื่นๆ ตามกลุ่มที่บันทึกไว้โดยใช้ API ต่างๆ ที่ Aspose.Words สำหรับ .NET มอบให้

#### ถาม: มีข้อจำกัดหรือข้อควรพิจารณาเมื่อใช้นิพจน์ทั่วไปและกลุ่มที่บันทึกไว้ใน Aspose.Words สำหรับ .NET หรือไม่

ตอบ: แม้ว่านิพจน์ทั่วไปและกลุ่มที่บันทึกจะมีความสามารถอันทรงพลังสำหรับการค้นหาข้อความและแทนที่ใน Aspose.Words สำหรับ .NET แต่สิ่งสำคัญคือต้องพิจารณาถึงความซับซ้อนและผลกระทบด้านประสิทธิภาพ นิพจน์ทั่วไปที่ซับซ้อนสูงและกลุ่มที่บันทึกไว้จำนวนมากอาจส่งผลต่อประสิทธิภาพการทำงาน ขอแนะนำให้ทดสอบและเพิ่มประสิทธิภาพนิพจน์ทั่วไปสำหรับกรณีการใช้งานเฉพาะของคุณเพื่อให้แน่ใจว่าการจัดการเอกสารมีประสิทธิภาพ

#### ถาม: ฉันสามารถใช้ฟีเจอร์ "รับรู้และการแทนที่ภายในรูปแบบการแทนที่" กับภาษาอื่นที่ไม่ใช่ภาษาอังกฤษได้หรือไม่

ตอบ: ได้ คุณลักษณะ "การรับรู้และการแทนที่ภายในรูปแบบการแทนที่" ใน Aspose.Words สำหรับ .NET สามารถใช้กับภาษาอื่นที่ไม่ใช่ภาษาอังกฤษได้ นิพจน์ทั่วไปไม่เชื่อเรื่องภาษาและสามารถสร้างให้ตรงกับรูปแบบเฉพาะในภาษาใดก็ได้ คุณสามารถปรับรูปแบบนิพจน์ทั่วไปให้เหมาะกับภาษาที่คุณต้องการและรูปแบบข้อความเฉพาะที่คุณต้องการจดจำและแทนที่ได้