---
title: تطبيق حدود المخطط التفصيلي
linktitle: تطبيق حدود المخطط التفصيلي
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتطبيق حدود المخطط التفصيلي على جدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لتطبيق حد مخطط تفصيلي على جدول باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي، سيكون لديك فهم واضح لكيفية التعامل مع حدود الجدول في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يتم فيه تخزين مستند Word الخاص بك. استبدل "دليل المستندات الخاصة بك" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تحميل الوثيقة
 بعد ذلك، تحتاج إلى تحميل مستند Word إلى مثيل`Document` فصل.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## الخطوة 3: الوصول إلى الجدول
 لتطبيق حدود مخطط تفصيلي، نحتاج إلى الوصول إلى الجدول الموجود في المستند. ال`Table` يمثل الفصل جدولًا في Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## الخطوة 4: قم بمحاذاة الجدول إلى منتصف الصفحة
 يمكننا الآن محاذاة الجدول في منتصف الصفحة باستخدام الأمر`Alignment` خاصية الجدول.

```csharp
table. Alignment = Table Alignment. Center;
```

## الخطوة 5: مسح حدود الجدول الموجودة
للبدء بحد مخطط تفصيلي جديد، نحتاج أولاً إلى مسح كافة الحدود الموجودة من الجدول. ويمكن القيام بذلك باستخدام`ClearBorders()` طريقة.

```csharp
table. ClearBorders();
```

## الخطوة 6: تحديد حد أخضر حول الطاولة
 يمكننا الآن تعيين حد أخضر حول الطاولة باستخدام`SetBorder()` طريقة لكل جانب من الجدول. في هذا المثال، نستخدم حدًا من النوع "مفرد" بسمك 1.5 نقطة ولون أخضر.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## الخطوة 7: املأ الخلايا بلون الخلفية
لتحسين العرض المرئي للجدول، يمكننا ملء الخلايا بلون الخلفية الأرضية

فكرة. في هذا المثال، نستخدم اللون الأخضر الفاتح.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## الخطوة 8: احفظ المستند المعدل
وأخيرًا، نقوم بحفظ المستند المعدل في ملف. يمكنك اختيار الاسم والموقع المناسبين للمستند الناتج.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

تهنئة ! لقد قمت الآن بتطبيق حد مخطط تفصيلي على جدول باستخدام Aspose.Words لـ .NET.

### نموذج التعليمات البرمجية المصدر لتطبيق حدود المخطط التفصيلي باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// قم بمحاذاة الجدول إلى وسط الصفحة.
	table.Alignment = TableAlignment.Center;
	//قم بمسح أي حدود موجودة من الجدول.
	table.ClearBorders();
	// ضع حدودًا خضراء حول الطاولة ولكن ليس بداخلها.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// املأ الخلايا بلون أخضر فاتح خالص.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تطبيق حدود مخطط تفصيلي على جدول باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي، يمكنك بسهولة دمج هذه الوظيفة في مشاريع C# الخاصة بك. يعد التعامل مع تنسيق الجدول جانبًا أساسيًا من معالجة المستندات، ويقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لتحقيق ذلك. باستخدام هذه المعرفة، يمكنك تحسين العرض المرئي لمستندات Word الخاصة بك وتلبية متطلبات محددة.