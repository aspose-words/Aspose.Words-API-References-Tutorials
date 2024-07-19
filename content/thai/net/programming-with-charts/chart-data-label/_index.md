---
title: ปรับแต่งป้ายกำกับข้อมูลแผนภูมิ
linktitle: ปรับแต่งป้ายกำกับข้อมูลแผนภูมิ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีปรับแต่งป้ายกำกับข้อมูลแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET ในคำแนะนำทีละขั้นตอน เหมาะสำหรับนักพัฒนา .NET
type: docs
weight: 10
url: /th/net/programming-with-charts/chart-data-label/
---
## การแนะนำ

คุณกำลังมองหาการปรับปรุงแอปพลิเคชัน .NET ของคุณด้วยความสามารถในการประมวลผลเอกสารแบบไดนามิกและแบบกำหนดเองหรือไม่? Aspose.Words สำหรับ .NET อาจเป็นคำตอบของคุณ! ในคู่มือนี้ เราจะเจาะลึกในการปรับแต่งป้ายชื่อข้อมูลแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET ซึ่งเป็นไลบรารีที่มีประสิทธิภาพสำหรับการสร้าง ปรับเปลี่ยน และแปลงเอกสาร Word ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น บทช่วยสอนนี้จะแนะนำคุณในแต่ละขั้นตอน เพื่อให้แน่ใจว่าคุณจะเข้าใจวิธีใช้เครื่องมือนี้อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. Visual Studio: ติดตั้ง Visual Studio 2019 หรือใหม่กว่า
2. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณมี .NET Framework 4.0 หรือใหม่กว่า
3.  Aspose.Words สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Words สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/words/net/).
4. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับการเขียนโปรแกรม C# เป็นสิ่งจำเป็น
5.  ใบอนุญาตที่ถูกต้อง: รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) หรือซื้อได้ที่[ซื้อลิงค์](https://purchase.aspose.com/buy).

## นำเข้าเนมสเปซ

ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ ขั้นตอนนี้มีความสำคัญเนื่องจากทำให้แน่ใจว่าคุณสามารถเข้าถึงคลาสและวิธีการทั้งหมดที่มีให้โดย Aspose.Words

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Charts;
```

## ขั้นตอนที่ 1: เริ่มต้นเอกสารและ DocumentBuilder

ในการสร้างและจัดการเอกสาร Word ก่อนอื่นเราต้องเริ่มต้นอินสแตนซ์ของ`Document` คลาสและก`DocumentBuilder` วัตถุ.

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### คำอธิบาย

- เอกสารเอกสาร: สร้างอินสแตนซ์ใหม่ของคลาสเอกสาร
- ตัวสร้าง DocumentBuilder: DocumentBuilder ช่วยในการแทรกเนื้อหาลงในวัตถุเอกสาร

## ขั้นตอนที่ 2: แทรกแผนภูมิ

 ต่อไป เราจะแทรกแผนภูมิแท่งลงในเอกสารโดยใช้เครื่องหมาย`DocumentBuilder` วัตถุ.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

### คำอธิบาย

- รูปร่างรูปร่าง: แสดงแผนภูมิเป็นรูปร่างในเอกสาร
- builder.InsertChart(ChartType.Bar, 432, 252): แทรกแผนภูมิแท่งที่มีขนาดที่ระบุ

## ขั้นตอนที่ 3: เข้าถึงซีรี่ส์แผนภูมิ

ในการปรับแต่งป้ายกำกับข้อมูล เราต้องเข้าถึงชุดข้อมูลในแผนภูมิก่อน

```csharp
ChartSeries series0 = shape.Chart.Series[0];
```

### คำอธิบาย

- ChartSeries series0: ดึงข้อมูลชุดแรกของแผนภูมิ ซึ่งเราจะปรับแต่ง

## ขั้นตอนที่ 4: ปรับแต่งป้ายกำกับข้อมูล

ป้ายกำกับข้อมูลสามารถปรับแต่งเพื่อแสดงข้อมูลต่างๆ ได้ เราจะกำหนดค่าป้ายกำกับให้แสดงคีย์คำอธิบาย ชื่อซีรีส์ และค่า ในขณะที่ซ่อนชื่อหมวดหมู่และเปอร์เซ็นต์

```csharp
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

### คำอธิบาย

- ป้าย ChartDataLabelCollection: เข้าถึงป้ายข้อมูลของชุดข้อมูล
- label.ShowLegendKey: แสดงคีย์คำอธิบาย
- label.ShowLeaderLines: แสดงเส้นตัวนำสำหรับป้ายกำกับข้อมูลที่อยู่นอกจุดข้อมูล
- label.ShowCategoryName: ซ่อนชื่อหมวดหมู่
- label.ShowPercentage: ซ่อนค่าเปอร์เซ็นต์
- label.ShowSeriesName: แสดงชื่อซีรีส์
- label.ShowValue: แสดงค่าของจุดข้อมูล
- label.Separator: ตั้งค่าตัวคั่นสำหรับป้ายกำกับข้อมูล

## ขั้นตอนที่ 5: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารลงในไดเร็กทอรีที่ระบุ

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### คำอธิบาย

- doc.Save: บันทึกเอกสารด้วยชื่อที่ระบุในไดเร็กทอรีที่ให้ไว้

## บทสรุป

 ยินดีด้วย! คุณปรับแต่งป้ายกำกับข้อมูลแผนภูมิได้สำเร็จโดยใช้ Aspose.Words สำหรับ .NET ไลบรารีนี้นำเสนอโซลูชันที่มีประสิทธิภาพสำหรับการจัดการเอกสาร Word โดยทางโปรแกรม ทำให้นักพัฒนาสามารถสร้างแอปพลิเคชันการประมวลผลเอกสารที่ซับซ้อนและไดนามิกได้ง่ายขึ้น ดำดิ่งสู่[เอกสารประกอบ](https://reference.aspose.com/words/net/) เพื่อสำรวจคุณสมบัติและความสามารถเพิ่มเติม

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words สำหรับ .NET เป็นไลบรารีการประมวลผลเอกสารที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และแปลงเอกสาร Word โดยทางโปรแกรมได้

### ฉันจะติดตั้ง Aspose.Words สำหรับ .NET ได้อย่างไร
 คุณสามารถดาวน์โหลดและติดตั้งได้จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/words/net/)- ทำตามคำแนะนำการติดตั้งที่ให้ไว้

### ฉันสามารถทดลองใช้ Aspose.Words สำหรับ .NET ได้ฟรีหรือไม่
 ใช่ คุณจะได้รับ[ทดลองฟรี](https://releases.aspose.com/) หรือก[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/)เพื่อประเมินผลิตภัณฑ์

### Aspose.Words สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.Words สำหรับ .NET เข้ากันได้กับ .NET Core, .NET Standard และ .NET Framework

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Words สำหรับ .NET ได้ที่ไหน
 ท่านสามารถเยี่ยมชมได้ที่[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/words/8) เพื่อขอความช่วยเหลือจากชุมชน Aspose และผู้เชี่ยวชาญ
