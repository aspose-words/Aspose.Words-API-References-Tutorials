---
title: รับตำแหน่งตารางลอยตัว
linktitle: รับตำแหน่งตารางลอยตัว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรับตำแหน่งของตารางลอยในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/get-floating-table-position/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีรับตำแหน่งของตารางลอยในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถรับคุณสมบัติการวางตำแหน่งของตารางลอยในเอกสาร Word ของคุณโดยทางโปรแกรม

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: กำลังโหลดเอกสารและเข้าถึงตาราง
ในการเริ่มการประมวลผลคำด้วยตาราง เราจำเป็นต้องโหลดเอกสารที่มีตารางเหล่านั้นและเข้าถึงได้ ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ นอกจากนี้ ตรวจสอบให้แน่ใจว่าเอกสารมีตารางลอยตัว

## ขั้นตอนที่ 3: รับคุณสมบัติการวางตำแหน่งตารางลอย
ต่อไป เราจะวนซ้ำตารางทั้งหมดในเอกสารและรับคุณสมบัติการวางตำแหน่งตารางแบบลอย ใช้รหัสต่อไปนี้:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// หากอาร์เรย์เป็นแบบลอย ให้พิมพ์คุณสมบัติการวางตำแหน่ง
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 ในที่นี้เราใช้ a`foreach` วนซ้ำเพื่อวนซ้ำอาร์เรย์ทั้งหมดในเอกสาร เราตรวจสอบว่าอาร์เรย์เป็นแบบโฟลตหรือไม่โดยการตรวจสอบ`TextWrapping` คุณสมบัติ. หากเป็นเช่นนั้น เราจะพิมพ์คุณสมบัติการวางตำแหน่งของตาราง เช่น จุดยึดแนวนอน จุดยึดแนวตั้ง ระยะทางแนวนอนและแนวตั้งสัมบูรณ์ การอนุญาตให้ทับซ้อนกัน ระยะทางแนวนอนสัมบูรณ์ และความสัมพันธ์ในการจัดตำแหน่งในแนวตั้ง
 
### ตัวอย่างซอร์สโค้ดสำหรับรับตำแหน่งตารางแบบลอยตัวโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// หากตารางเป็นแบบลอย ให้พิมพ์คุณสมบัติการวางตำแหน่ง
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีรับตำแหน่งของตารางลอยในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณจะได้รับคุณสมบัติการวางตำแหน่งของตารางลอยในเอกสาร Word ของคุณโดยทางโปรแกรม คุณลักษณะนี้ช่วยให้คุณสามารถวิเคราะห์และจัดการตารางลอยได้ตามความต้องการเฉพาะของคุณ