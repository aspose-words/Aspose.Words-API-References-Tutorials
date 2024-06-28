---
title: รับระยะห่างระหว่างข้อความล้อมรอบตาราง
linktitle: รับระยะห่างระหว่างข้อความล้อมรอบตาราง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนเพื่อรับระยะห่างระหว่างข้อความและตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อรับระยะห่างระหว่างข้อความที่อยู่รอบๆ ในตารางโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีเข้าถึงระยะห่างต่างๆ ระหว่างตารางและข้อความโดยรอบในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือที่ตั้งเอกสาร Word ของคุณ แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารที่มีอยู่
 ถัดไป คุณต้องโหลดเอกสาร Word ที่มีอยู่ลงในอินสแตนซ์ของ`Document` ชั้นเรียน

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## ขั้นตอนที่ 3: หาระยะห่างระหว่างตารางกับข้อความโดยรอบ
 เพื่อให้ได้ระยะห่างระหว่างตารางและข้อความโดยรอบ เราจำเป็นต้องเข้าถึงตารางในเอกสารโดยใช้`GetChild()` วิธีการและ`NodeType.Table` คุณสมบัติ. จากนั้นเราสามารถแสดงระยะทางที่แตกต่างกันโดยใช้คุณสมบัติอาร์เรย์`DistanceTop`, `DistanceBottom`, `DistanceRight` และ`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### ซอร์สโค้ดตัวอย่างสำหรับรับระยะห่างระหว่างตารางรอบข้อความโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีหาระยะห่างระหว่างข้อความโดยรอบในตารางโดยใช้ Aspose.Words สำหรับ .NET เมื่อทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถเข้าถึงระยะห่างต่างๆ ระหว่างตารางและข้อความโดยรอบในเอกสาร Word ของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถวิเคราะห์เค้าโครงตารางของคุณโดยสัมพันธ์กับข้อความและตอบสนองความต้องการเฉพาะได้