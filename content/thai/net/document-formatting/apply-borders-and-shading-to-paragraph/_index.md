---
title: ใช้เส้นขอบและการแรเงากับย่อหน้าในเอกสาร Word
linktitle: ใช้เส้นขอบและการแรเงากับย่อหน้าในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ใช้เส้นขอบและการแรเงากับย่อหน้าในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อปรับปรุงการจัดรูปแบบเอกสารของคุณ
type: docs
weight: 10
url: /th/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
## การแนะนำ

สวัสดี เคยสงสัยบ้างไหมว่าจะทำให้เอกสาร Word ของคุณมีเส้นขอบและการแรเงาสุดเก๋ได้อย่างไร คุณอยู่ในสถานที่ที่เหมาะสม! วันนี้ เรากำลังดำดิ่งสู่โลกของ Aspose.Words สำหรับ .NET เพื่อทำให้ย่อหน้าของเรามีชีวิตชีวา ลองนึกภาพเอกสารของคุณดูทันสมัยพอๆ กับงานของนักออกแบบมืออาชีพด้วยโค้ดเพียงไม่กี่บรรทัด พร้อมที่จะเริ่มต้นหรือยัง? ไปกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้นการเขียนโค้ด เราต้องแน่ใจว่าเรามีทุกสิ่งที่เราต้องการก่อน นี่คือรายการตรวจสอบด่วนของคุณ:

-  Aspose.Words สำหรับ .NET: คุณต้องติดตั้งไลบรารีนี้ คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์กำหนด](https://releases.aspose.com/words/net/).
- สภาพแวดล้อมการพัฒนา: Visual Studio หรือ IDE อื่น ๆ ที่รองรับ .NET
- ความรู้พื้นฐานเกี่ยวกับ C#: เพียงพอที่จะเข้าใจและปรับแต่งข้อมูลโค้ด
- ใบอนุญาตที่ถูกต้อง: อย่างใดอย่างหนึ่ง[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) หรือของที่ซื้อมาจาก[กำหนด](https://purchase.aspose.com/buy).

## นำเข้าเนมสเปซ

ก่อนที่จะกระโดดลงไปในโค้ด เราต้องแน่ใจว่าเราได้นำเข้าเนมสเปซที่จำเป็นเข้ามาในโปรเจ็กต์ของเราแล้ว สิ่งนี้ทำให้คุณสมบัติเจ๋ง ๆ ทั้งหมดของ Aspose.Words เข้าถึงได้สำหรับเรา

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using Aspose.Words.Drawing;
using System.Drawing;
```

ตอนนี้ เรามาแบ่งกระบวนการออกเป็นขั้นตอนขนาดพอดีคำกัน แต่ละขั้นตอนจะมีหัวข้อและคำอธิบายโดยละเอียด พร้อม? ไปกันเลย!

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

ก่อนอื่น เราต้องมีพื้นที่สำหรับบันทึกเอกสารที่มีรูปแบบสวยงาม มากำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 ไดเร็กทอรีนี้เป็นที่ที่เอกสารขั้นสุดท้ายของคุณจะถูกบันทึกไว้ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงบนเครื่องของคุณ

## ขั้นตอนที่ 2: สร้างเอกสารใหม่และ DocumentBuilder

 ต่อไปเราจะต้องสร้างเอกสารใหม่และก`DocumentBuilder` วัตถุ. ที่`DocumentBuilder` คือไม้กายสิทธิ์ของเราที่ช่วยให้เราสามารถจัดการเอกสารได้

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 ที่`Document` object แสดงถึงเอกสาร Word ทั้งหมดของเรา และ`DocumentBuilder` ช่วยเราเพิ่มและจัดรูปแบบเนื้อหา

## ขั้นตอนที่ 3: กำหนดเส้นขอบย่อหน้า

ตอนนี้ มาเพิ่มเส้นขอบที่มีสไตล์ให้กับย่อหน้าของเรากันดีกว่า เราจะกำหนดระยะห่างจากข้อความและกำหนดรูปแบบเส้นขอบที่แตกต่างกัน

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

ที่นี่ เรากำหนดระยะห่าง 20 จุดระหว่างข้อความและเส้นขอบ เส้นขอบทุกด้าน (ซ้าย, ขวา, บน, ล่าง) ถูกกำหนดให้เป็นเส้นคู่ แฟนซีใช่ไหม?

## ขั้นตอนที่ 4: ใช้การแรเงากับย่อหน้า

เส้นขอบนั้นเยี่ยมยอด แต่มาเพิ่มความพิเศษด้วยการแรเงากันดีกว่า เราจะใช้รูปแบบกากบาทในแนวทแยงผสมกับสีเพื่อทำให้ย่อหน้าของเราโดดเด่น

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

ในขั้นตอนนี้ เราใช้พื้นผิวกากบาทในแนวทแยงโดยมีปะการังสีอ่อนเป็นสีพื้นหลัง และใช้สีแซลมอนสีอ่อนเป็นสีโฟร์กราวด์ มันเหมือนกับการแต่งย่อหน้าของคุณด้วยเสื้อผ้าดีไซเนอร์!

## ขั้นตอนที่ 5: เพิ่มข้อความลงในย่อหน้า

ย่อหน้าที่ไม่มีข้อความคืออะไร? มาเพิ่มประโยคตัวอย่างเพื่อดูการจัดรูปแบบของเรา

```csharp
builder.Write("I'm a formatted paragraph with double border and nice shading.");
```

บรรทัดนี้แทรกข้อความของเราลงในเอกสาร เรียบง่าย แต่ตอนนี้ถูกห่อหุ้มด้วยกรอบมีสไตล์และพื้นหลังสีเทา

## ขั้นตอนที่ 6: บันทึกเอกสาร

ในที่สุดก็ถึงเวลาบันทึกงานของเรา มาบันทึกเอกสารลงในไดเร็กทอรีที่ระบุด้วยชื่อที่สื่อความหมาย

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

 สิ่งนี้จะบันทึกเอกสารของเราด้วยชื่อ`DocumentFormatting.ApplyBordersAndShadingToParagraph.doc` ในไดเร็กทอรีที่เราระบุไว้ก่อนหน้านี้

## บทสรุป

และคุณก็ได้แล้ว! ด้วยโค้ดเพียงไม่กี่บรรทัด เราได้เปลี่ยนย่อหน้าธรรมดาให้กลายเป็นเนื้อหาที่ดึงดูดสายตา Aspose.Words สำหรับ .NET ทำให้การเพิ่มการจัดรูปแบบที่ดูเป็นมืออาชีพให้กับเอกสารของคุณเป็นเรื่องง่ายอย่างไม่น่าเชื่อ ไม่ว่าคุณจะเตรียมรายงาน จดหมาย หรือเอกสารใดๆ เทคนิคเหล่านี้จะช่วยให้คุณสร้างความประทับใจได้เป็นอย่างดี ลองใช้เลย และดูเอกสารของคุณมีชีวิตขึ้นมา!

## คำถามที่พบบ่อย

### ฉันสามารถใช้สไตล์เส้นที่แตกต่างกันสำหรับแต่ละเส้นขอบได้หรือไม่  
 อย่างแน่นอน! Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถปรับแต่งแต่ละเส้นขอบแยกกันได้ เพียงแค่ตั้งค่า`LineStyle` สำหรับเส้นขอบแต่ละประเภทตามที่แสดงในคำแนะนำ

### มีพื้นผิวแรเงาอะไรอีกบ้าง?  
 มีพื้นผิวหลายแบบที่คุณสามารถใช้ได้ เช่น ทึบ แถบแนวนอน แถบแนวตั้ง และอื่นๆ ตรวจสอบ[จัดทำเอกสาร](https://reference.aspose.com/words/net/) สำหรับรายการทั้งหมด

### ฉันจะเปลี่ยนสีเส้นขอบได้อย่างไร?  
 คุณสามารถตั้งค่าสีเส้นขอบโดยใช้`Color` คุณสมบัติสำหรับแต่ละชายแดน ตัวอย่างเช่น,`borders[BorderType.Left].Color = Color.Red;`.

### เป็นไปได้ไหมที่จะใช้เส้นขอบและการแรเงากับส่วนใดส่วนหนึ่งของข้อความ?  
 ใช่ คุณสามารถใช้เส้นขอบและการแรเงากับข้อความเฉพาะได้โดยใช้`Run` วัตถุภายใน`DocumentBuilder`.

### ฉันสามารถทำให้กระบวนการนี้เป็นอัตโนมัติสำหรับหลายย่อหน้าได้หรือไม่  
อย่างแน่นอน! คุณสามารถวนซ้ำย่อหน้าของคุณและใช้การตั้งค่าเส้นขอบและแรเงาเดียวกันโดยทางโปรแกรม
