---
title: استخدم مصدر التحذير
linktitle: استخدم مصدر التحذير
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام مصدر التحذير مع Aspose.Words دليل تفصيلي خطوة بخطوة لـ .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/use-warning-source/
---

في هذا المثال ، سوف نوضح لك كيفية استخدام مصدر التحذير مع Aspose.Words for .NET. يشير مصدر التحذير إلى أصل التحذير عند استخدام وظيفة رد الاتصال.

## الخطوة 1: تحميل المستند

 سنقوم بتحميل مستند موجود يحتوي على تحذيرات باستخدام امتداد`Load` طريقة`Document` فصل.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## الخطوة 3: استخدام مصدر التحذير

 سنستخدم مصدر التحذير من خلال تعيين المستند`WarningCallback` ملكية لمجموعة من`WarningInfo` أشياء.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## الخطوة 4: حفظ المستند

أخيرًا ، يمكننا حفظ المستند بالتنسيق المطلوب.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### مثال التعليمات البرمجية المصدر لاستخدام مصدر التحذير مع Aspose.Words for .NET

```csharp
	// المسار إلى دليل المستندات.
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

تهنئة ! لقد تعلمت الآن كيفية استخدام مصدر التحذير مع Aspose.Words for .NET.