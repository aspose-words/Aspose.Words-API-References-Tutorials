---
title: จัดรูปแบบจำนวนป้ายกำกับข้อมูลในแผนภูมิ
linktitle: จัดรูปแบบจำนวนป้ายกำกับข้อมูลในแผนภูมิ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีจัดรูปแบบป้ายกำกับข้อมูลในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนนี้ ปรับปรุงเอกสาร Word ของคุณได้อย่างง่ายดาย
type: docs
weight: 10
url: /th/net/programming-with-charts/format-number-of-data-label/
---
## การแนะนำ

การสร้างเอกสารที่น่าสนใจและให้ข้อมูลมักจะเกี่ยวข้องกับการรวมแผนภูมิที่มีป้ายกำกับข้อมูลที่มีการจัดรูปแบบอย่างดี หากคุณเป็นนักพัฒนา .NET ที่ต้องการปรับปรุงเอกสาร Word ของคุณด้วยแผนภูมิที่ซับซ้อน Aspose.Words สำหรับ .NET เป็นไลบรารีที่ยอดเยี่ยมที่จะช่วยให้คุณบรรลุเป้าหมายดังกล่าว บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการจัดรูปแบบป้ายตัวเลขในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET ทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกโค้ด มีข้อกำหนดเบื้องต้นบางประการที่คุณต้องมี:

-  Aspose.Words for .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Words for .NET แล้ว หากคุณยังไม่ได้ติดตั้ง คุณสามารถทำได้[ดาวน์โหลดได้ที่นี่](https://releases.aspose.com/words/net/).
- สภาพแวดล้อมการพัฒนา: คุณควรตั้งค่าสภาพแวดล้อมการพัฒนา .NET ขอแนะนำให้ใช้ Visual Studio
- ความรู้พื้นฐานของ C#: ความคุ้นเคยกับการเขียนโปรแกรม C# เป็นสิ่งจำเป็นเนื่องจากบทช่วยสอนนี้เกี่ยวข้องกับการเขียนและทำความเข้าใจโค้ด C#
-  ใบอนุญาตชั่วคราว: หากต้องการใช้ Aspose.Words โดยไม่มีข้อจำกัดใด ๆ คุณสามารถรับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).

ตอนนี้ เรามาเจาะลึกกระบวนการจัดรูปแบบป้ายตัวเลขในแผนภูมิทีละขั้นตอนกัน

## นำเข้าเนมสเปซ

ก่อนอื่น เราต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Words สำหรับ .NET เพิ่มบรรทัดต่อไปนี้ที่ด้านบนของไฟล์ C# ของคุณ:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

ก่อนจะเริ่มจัดการเอกสาร Word ได้ คุณต้องระบุไดเร็กทอรีที่จะบันทึกเอกสารของคุณเสียก่อน นี่เป็นสิ่งจำเป็นสำหรับการดำเนินการบันทึกในภายหลัง

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: เริ่มต้นเอกสารและ DocumentBuilder

 ขั้นตอนต่อไปคือการเริ่มต้นใหม่`Document` และก`DocumentBuilder` - ที่`DocumentBuilder` เป็นคลาสตัวช่วยที่ช่วยให้เราสามารถสร้างเนื้อหาเอกสารได้

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: แทรกแผนภูมิลงในเอกสาร

 ตอนนี้ เรามาแทรกแผนภูมิลงในเอกสารโดยใช้`DocumentBuilder`- ในบทช่วยสอนนี้ เราจะใช้แผนภูมิเส้นเป็นตัวอย่าง

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

ที่นี่ เราแทรกแผนภูมิเส้นที่มีความกว้างและความสูงเฉพาะ และตั้งชื่อแผนภูมิ

## ขั้นตอนที่ 4: ล้างซีรี่ส์เริ่มต้นและเพิ่มซีรี่ส์ใหม่

ตามค่าเริ่มต้น แผนภูมิจะมีซีรี่ส์ที่สร้างไว้ล่วงหน้าบางส่วน เราจำเป็นต้องล้างสิ่งเหล่านี้และเพิ่มซีรี่ส์ของเราเองด้วยจุดข้อมูลเฉพาะ

```csharp
// ลบซีรี่ส์ที่สร้างโดยค่าเริ่มต้น
chart.Series.Clear();

// เพิ่มซีรี่ส์ใหม่ด้วยจุดข้อมูลที่กำหนดเอง
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
	new string[] { "Category 1", "Category 2", "Category 3" }, 
	new double[] { 2.5, 1.5, 3.5 });
```

## ขั้นตอนที่ 5: เปิดใช้งานป้ายกำกับข้อมูล

หากต้องการแสดงป้ายกำกับข้อมูลบนแผนภูมิ เราจำเป็นต้องเปิดใช้งานป้ายกำกับเหล่านี้สำหรับซีรี่ส์ของเรา

```csharp
series1.HasDataLabels = true;
series1.DataLabels.ShowValue = true;
```

## ขั้นตอนที่ 6: จัดรูปแบบป้ายกำกับข้อมูล

หัวใจสำคัญของบทช่วยสอนนี้คือการจัดรูปแบบป้ายกำกับข้อมูล เราสามารถใช้รูปแบบตัวเลขที่แตกต่างกันกับแต่ละป้ายข้อมูลแยกกันได้

```csharp
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00"; // รูปแบบสกุลเงิน
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy"; // รูปแบบวันที่
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%"; // รูปแบบเปอร์เซ็นต์
```

 นอกจากนี้ คุณยังสามารถลิงก์รูปแบบของป้ายชื่อข้อมูลไปยังเซลล์ต้นทางได้ เมื่อเชื่อมโยงแล้ว`NumberFormat` จะถูกรีเซ็ตเป็นแบบทั่วไปและสืบทอดมาจากเซลล์ต้นทาง

```csharp
series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
```

## ขั้นตอนที่ 7: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารลงในไดเร็กทอรีที่ระบุ

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

วิธีนี้จะบันทึกเอกสารของคุณด้วยชื่อที่ระบุ และช่วยให้แน่ใจว่าแผนภูมิที่มีป้ายกำกับข้อมูลที่จัดรูปแบบแล้วจะยังคงอยู่

## บทสรุป

การจัดรูปแบบป้ายชื่อข้อมูลในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET สามารถปรับปรุงความสามารถในการอ่านและความเป็นมืออาชีพของเอกสาร Word ของคุณได้อย่างมาก เมื่อทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถสร้างแผนภูมิ เพิ่มชุดข้อมูล และจัดรูปแบบป้ายชื่อข้อมูลให้ตรงกับความต้องการของคุณได้ Aspose.Words สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ช่วยให้สามารถปรับแต่งเอกสาร Word ได้อัตโนมัติและเป็นระบบอัตโนมัติ ทำให้เป็นทรัพย์สินอันล้ำค่าสำหรับนักพัฒนา .NET

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการสร้าง จัดการ และแปลงเอกสาร Word โดยทางโปรแกรมโดยใช้ C#

### ฉันสามารถจัดรูปแบบแผนภูมิประเภทอื่นด้วย Aspose.Words สำหรับ .NET ได้หรือไม่
ใช่ Aspose.Words สำหรับ .NET รองรับแผนภูมิหลายประเภท รวมถึงแท่ง คอลัมน์ พาย และอื่นๆ

### ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Words สำหรับ .NET ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### เป็นไปได้หรือไม่ที่จะเชื่อมโยงป้ายกำกับข้อมูลกับเซลล์ต้นทางใน Excel
ได้ คุณสามารถเชื่อมโยงป้ายกำกับข้อมูลกับเซลล์ต้นทางได้ โดยอนุญาตให้ใช้รูปแบบตัวเลขสืบทอดจากเซลล์ต้นทางได้

### ฉันจะหาเอกสารรายละเอียดเพิ่มเติมเกี่ยวกับ Aspose.Words สำหรับ .NET ได้ที่ไหน
 คุณสามารถค้นหาเอกสารที่ครอบคลุม[ที่นี่](https://reference.aspose.com/words/net/).
