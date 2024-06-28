---
title: การใช้บานหน้าต่างงานส่วนขยายของเว็บ
linktitle: การใช้บานหน้าต่างงานส่วนขยายของเว็บ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการใช้บานหน้าต่างงานส่วนขยายเว็บกับ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-webextension/using-web-extension-task-panes/
---

บทความนี้ให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการใช้บานหน้าต่างงานส่วนขยายเว็บด้วย Aspose.Words สำหรับ .NET เราจะอธิบายโค้ดแต่ละส่วนอย่างละเอียด ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถเข้าใจวิธีเพิ่มและกำหนดค่าบานหน้าต่างงานสำหรับส่วนขยายเว็บได้

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Words สำหรับ .NET ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดูไลบรารีและคำแนะนำในการติดตั้งได้จากเว็บไซต์ Aspose

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ในการเริ่มต้น คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกเอกสารที่สร้างขึ้น แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างและกำหนดค่าบานหน้าต่างงาน

 เราสร้างก`TaskPane` วัตถุและเพิ่มลงในเอกสาร`s `คอลเลกชันของ WebExtensionTaskPanes ต่อไป เราจะกำหนดค่าคุณสมบัติของบานหน้าต่างงาน เช่น สถานะที่เทียบชิดขอบ การมองเห็น และความกว้าง

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

นอกจากนี้เรายังตั้งค่าข้อมูลรับรองส่วนขยายเว็บ รวมถึงรหัสแค็ตตาล็อก เวอร์ชัน และประเภทร้านค้า

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

สุดท้ายนี้ เราเพิ่มคุณสมบัติและการผูกเข้ากับส่วนขยายของเว็บ

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## ขั้นตอนที่ 3: บันทึกและโหลดเอกสาร

เราบันทึกเอกสารด้วยบานหน้าต่างงานที่กำหนดค่าไว้ในไดเร็กทอรีที่ระบุ

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## ขั้นตอนที่ 4: แสดงข้อมูลบานหน้าต่างงาน

ต่อไป เราจะโหลดเอกสารและแสดงข้อมูลแหล่งที่มาของบานหน้าต่างงาน

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

นั่นคือทั้งหมด! คุณใช้บานหน้าต่างงานส่วนขยายเว็บกับ Aspose.Words สำหรับ .NET สำเร็จแล้ว

### ตัวอย่างซอร์สโค้ดสำหรับการใช้บานหน้าต่างงานส่วนขยายเว็บด้วย Aspose.Words สำหรับ .NET


```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	TaskPane taskPane = new TaskPane();
	doc.WebExtensionTaskPanes.Add(taskPane);

	taskPane.DockState = TaskPaneDockState.Right;
	taskPane.IsVisible = true;
	taskPane.Width = 300;

	taskPane.WebExtension.Reference.Id = "wa102923726";
	taskPane.WebExtension.Reference.Version = "1.0.0.0";
	taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
	taskPane.WebExtension.Reference.Store = "th-TH";
	taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
	taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
		WebExtensionBindingType.Text, "194740422"));

	doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	
	
	doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	Console.WriteLine("Task panes sources:\n");

	foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
	{
		WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
		Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
	}
 
```
