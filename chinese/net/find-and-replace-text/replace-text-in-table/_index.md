---
title: استبدال النص في الجدول
linktitle: استبدال النص في الجدول
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استبدال نص في جدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/find-and-replace-text/replace-text-in-table/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة "استبدال النص في الجدول" في Aspose.Words لمكتبة .NET. تتيح لك هذه الميزة البحث عن نص معين واستبداله داخل جدول في مستند Word.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: قم بتحميل المستند

 قبل أن نبدأ في استخدام استبدال النص في جدول ، نحتاج إلى تحميل المستند إلى Aspose.Words for .NET. يمكن القيام بذلك باستخدام ملف`Document` فئة وتحديد مسار ملف المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

## الخطوة 2: الوصول إلى اللوحة

 بمجرد تحميل المستند ، نحتاج إلى الانتقال إلى الجدول حيث نريد إجراء استبدال النص. في مثالنا ، نستخدم الامتداد`GetChild` الطريقة مع`NodeType.Table` المعلمة للحصول على الجدول الأول في المستند:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## الخطوة 3: إجراء استبدال النص

 الآن نستخدم ملف`Range.Replace` طريقة لإجراء استبدال النص في المصفوفة. في مثالنا ، نستبدل كل تكرارات كلمة "Carrots" بكلمة "Eggs" باستخدام امتداد`FindReplaceOptions` الخيار مع`FindReplaceDirection.Forward` اتجاه البحث. بالإضافة إلى ذلك ، نستبدل القيمة "50" بـ "20" في الخلية الأخيرة من الصف الأخير من الجدول:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## الخطوة 4: احفظ المستند المحرر

 أخيرًا ، نحفظ المستند المعدل في دليل محدد باستخدام امتداد`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
```

Aspose.Words for .NET اتبعنا دليلًا تفصيليًا لتحميل مستند والوصول إلى الجدول وإجراء استبدال النص وحفظ المستند المعدل.

### مثال على شفرة المصدر لـ Replace Text In Table باستخدام Aspose.Words لـ .NET

في ما يلي نموذج التعليمات البرمجية المصدر الكامل لإثبات استخدام استبدال النص في جدول مع Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Tables.docx");

	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
	table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
    
```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام وظيفة Aspose's Replace Text In Table.
