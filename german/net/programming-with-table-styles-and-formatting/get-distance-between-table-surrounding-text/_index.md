---
title: الحصول على مسافة بين النص المحيط بالجدول
linktitle: الحصول على مسافة بين النص المحيط بالجدول
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لمعرفة المسافة بين النص والجدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة للحصول على المسافة بين النص المحيط في جدول باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية الوصول إلى المسافات المختلفة بين الجدول والنص المحيط في مستندات Word باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يوجد فيه مستند Word الخاص بك. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تحميل المستند الحالي
 بعد ذلك ، تحتاج إلى تحميل مستند Word الموجود في مثيل`Document` فصل.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## الخطوة 3: احصل على المسافة بين الجدول والنص المحيط
 للحصول على المسافة بين الجدول والنص المحيط ، نحتاج إلى الوصول إلى الجدول في المستند باستخدام تنسيق`GetChild()` الطريقة و`NodeType.Table` ملكية. يمكننا بعد ذلك عرض المسافات المختلفة باستخدام خصائص المصفوفة`DistanceTop`, `DistanceBottom`, `DistanceRight` و`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### عينة من التعليمات البرمجية المصدر للحصول على المسافة بين النص المحيط بالجدول باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على المسافة بين النص المحيط في جدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك الوصول بسهولة إلى المسافات المختلفة بين الجدول والنص المحيط في مستندات Word الخاصة بك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة ، يمكنك تحليل تخطيط الجداول الخاصة بك فيما يتعلق بالنص وتلبية الاحتياجات المحددة.