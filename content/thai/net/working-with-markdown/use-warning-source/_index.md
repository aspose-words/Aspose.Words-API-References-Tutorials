---
title: ใช้แหล่งคำเตือน
linktitle: ใช้แหล่งคำเตือน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้แหล่งคำเตือนด้วย Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/working-with-markdown/use-warning-source/
---

ในตัวอย่างนี้ เราจะแสดงวิธีใช้แหล่งคำเตือนกับ Aspose.Words สำหรับ .NET แหล่งคำเตือนระบุที่มาของคำเตือนเมื่อใช้ฟังก์ชันโทรกลับ

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

 เราจะโหลดเอกสารที่มีอยู่ซึ่งมีคำเตือนโดยใช้`Load` วิธีการของ`Document` ชั้นเรียน

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## ขั้นตอนที่ 3: การใช้แหล่งคำเตือน

 เราจะใช้แหล่งคำเตือนโดยการตั้งค่าของเอกสาร`WarningCallback` ทรัพย์สินเพื่อรวบรวมของ`WarningInfo` วัตถุ

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

สุดท้ายเราสามารถบันทึกเอกสารในรูปแบบที่ต้องการได้

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### ตัวอย่างซอร์สโค้ดสำหรับการใช้แหล่งคำเตือนกับ Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีใช้แหล่งคำเตือนกับ Aspose.Words สำหรับ .NET แล้ว

### คำถามที่พบบ่อย

#### ถาม: เราสามารถปรับแต่งลักษณะที่ปรากฏของแท็ก "คำเตือน" ได้หรือไม่

 ตอบ: การจัดรูปแบบของแท็ก "คำเตือน" ขึ้นอยู่กับตัวเรนเดอร์ Markdown ที่ใช้ ในกรณีส่วนใหญ่ คุณสามารถปรับแต่งรูปลักษณ์ได้โดยใช้ CSS เพื่อกำหนดเป้าหมาย`blockquote` แท็กในเอกสารของคุณ

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มไอคอนลงในแท็ก "คำเตือน"

ตอบ: ได้ คุณสามารถเพิ่มไอคอนลงในแท็ก "คำเตือน" ได้โดยใช้โค้ด HTML ในเอกสาร Markdown ของคุณ คุณสามารถใส่ก`span` แท็กด้วยคลาสที่เหมาะสมเพื่อแสดงไอคอนถัดจากข้อความเตือน

#### ถาม: แท็ก "คำเตือน" เข้ากันได้กับโปรแกรมอ่าน Markdown ทั้งหมดหรือไม่

 ตอบ: ความเข้ากันได้ของแท็ก "คำเตือน" ขึ้นอยู่กับการเรนเดอร์ Markdown ที่ใช้ ผู้อ่าน Markdown ส่วนใหญ่จะสนับสนุน`blockquote` แท็กเพื่อแสดงข้อความที่ไฮไลต์ แต่ลักษณะที่ปรากฏอาจแตกต่างกันไป