---
title: استخدام أجزاء المهام الخاصة بملحق الويب
linktitle: استخدام أجزاء المهام الخاصة بملحق الويب
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لاستخدام أجزاء مهام ملحق الويب مع Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-webextension/using-web-extension-task-panes/
---

توفر هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام أجزاء مهام ملحق الويب مع Aspose.Words for .NET. وسنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي، ستتمكن من فهم كيفية إضافة أجزاء المهام وتكوينها لملحقات الويب.

قبل البدء، تأكد من تثبيت وتكوين مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وتعليمات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء، تحتاج إلى تحديد المسار إلى الدليل الذي تريد حفظ المستند الذي تم إنشاؤه فيه. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء وتكوين جزء المهام

 نقوم بإنشاء أ`TaskPane` الكائن وإضافته إلى المستند`s `مجموعة WebExtensionTaskPanes. بعد ذلك، نقوم بتكوين خصائص جزء المهام، مثل حالة الإرساء وإمكانية الرؤية والعرض.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

نقوم أيضًا بتعيين بيانات اعتماد ملحق الويب بما في ذلك معرف الكتالوج والإصدار ونوع المتجر.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

وأخيرًا، نضيف الخصائص والارتباطات إلى ملحق الويب.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## الخطوة 3: احفظ المستند وقم بتحميله

نقوم بحفظ المستند باستخدام أجزاء المهام التي تم تكوينها في الدليل المحدد.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## الخطوة 4: عرض معلومات أجزاء المهام

بعد ذلك، نقوم بتحميل المستند وعرض معلومات مصدر جزء المهام.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

هذا كل شئ ! لقد نجحت في استخدام أجزاء المهام الخاصة بامتداد الويب مع Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر لاستخدام أجزاء مهام ملحق الويب مع Aspose.Words لـ .NET


```csharp

	// المسار إلى دليل المستندات.
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
