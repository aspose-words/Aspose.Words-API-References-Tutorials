---
title: รับตำแหน่งตาราง
linktitle: รับตำแหน่งตาราง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรับตำแหน่งของตารางในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/get-table-position/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีรับตำแหน่งของตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถรับคุณสมบัติการวางตำแหน่งตารางในเอกสาร Word ของคุณโดยทางโปรแกรม

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: กำลังโหลดเอกสารและเข้าถึงตาราง
ในการเริ่มการประมวลผลคำด้วยตาราง เราจำเป็นต้องโหลดเอกสารที่มีอยู่และเข้าถึงได้ ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Tables.docx");

// การเข้าถึงอาร์เรย์
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ นอกจากนี้ ตรวจสอบให้แน่ใจว่าเอกสารมีตารางที่คุณต้องการรับตำแหน่ง

## ขั้นตอนที่ 3: รับคุณสมบัติการวางตำแหน่งอาร์เรย์
ต่อไป เราจะตรวจสอบประเภทการวางตำแหน่งของอาเรย์และรับคุณสมบัติการวางตำแหน่งที่เหมาะสม ใช้รหัสต่อไปนี้:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 ที่นี่เราใช้เงื่อนไขเพื่อตรวจสอบว่าอาร์เรย์เป็นแบบโฟลตหรือไม่ ถ้าเป็นเช่นนั้นเราจะพิมพ์`RelativeHorizontalAlignment`และ`RelativeVerticalAlignment` คุณสมบัติเพื่อให้ได้การจัดแนวสัมพัทธ์ในแนวนอนและแนวตั้งของตาราง มิฉะนั้นเราจะพิมพ์`Alignment` คุณสมบัติเพื่อรับการจัดตำแหน่งอาร์เรย์

### ตัวอย่างซอร์สโค้ดสำหรับรับตำแหน่งตารางโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีรับตำแหน่งของตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณจะได้รับคุณสมบัติการวางตำแหน่งตารางในเอกสาร Word ของคุณโดยทางโปรแกรม คุณลักษณะนี้ช่วยให้คุณสามารถวิเคราะห์และจัดการอาร์เรย์ตามตำแหน่งเฉพาะได้