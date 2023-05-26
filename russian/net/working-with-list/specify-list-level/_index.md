---
title: حدد مستوى القائمة
linktitle: حدد مستوى القائمة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحديد مستوى القائمة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/working-with-list/specify-list-level/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوضح لك كيفية تحديد مستوى القائمة في مستند Word باستخدام Aspose.Words for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت Aspose.Words for .NET وتهيئته في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: إنشاء مُنشئ المستند والمستند

أولاً ، قم بإنشاء مستند جديد ومولد المستندات المرتبط به:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إنشاء وتطبيق قائمة رقمية

بعد ذلك ، أنشئ قائمة ذات تعداد رقمي استنادًا إلى أحد قوالب قوائم Microsoft Word وقم بتطبيقها على الفقرة الحالية في منشئ المستندات:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## الخطوة 3: مواصفات مستوى القائمة

 استخدم وثيقة منشئ`ListLevelNumber`لتحديد مستوى القائمة وإضافة نص إلى الفقرة:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

كرر هذه الخطوات لتحديد مستويات القائمة وإضافة نص في كل مستوى.

## الخطوة 4: إنشاء وتطبيق قائمة نقطية

يمكنك أيضًا إنشاء قائمة نقطية وتطبيقها باستخدام أحد قوالب قوائم Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## الخطوة 5: إضافة نص إلى مستويات قائمة نقطية

 استخدم ال`ListLevelNumber` الخاصية مرة أخرى لتحديد مستوى القائمة النقطية وإضافة نص:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## الخطوة 6: إيقاف قائمة التنسيق

 لإيقاف تنسيق القائمة ، اضبط`null` الى`List` خاصية منشئ المستندات:

```csharp
builder. ListFormat. List = null;
```

## الخطوة 7: حفظ المستند المعدل

احفظ المستند المعدل:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

لذا ! لقد نجحت في تحديد مستوى القائمة في مستند Word باستخدام Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لتحديد مستوى القائمة

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء قائمة ذات تعداد رقمي استنادًا إلى أحد قوالب قائمة Microsoft Word
// وتطبيقه على الفقرة الحالية لمنشئ المستند.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// هناك تسعة مستويات في هذه القائمة ، دعونا نجربها جميعًا.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

//قم بإنشاء قائمة ذات تعداد نقطي استنادًا إلى أحد قوالب قوائم Microsoft Word
// وتطبيقه على الفقرة الحالية لمنشئ المستند.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// هذه طريقة لإيقاف تنسيق القائمة.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```



