---
title: أعد تشغيل رقم القائمة
linktitle: أعد تشغيل رقم القائمة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إعادة تعيين رقم قائمة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-list/restart-list-number/
---
في هذا البرنامج التعليمي خطوة بخطوة ، سنوضح لك كيفية إعادة تعيين رقم قائمة في مستند Word باستخدام Aspose.Words for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت Aspose.Words for .NET وتهيئته في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: إنشاء مُنشئ المستند والمستند

أولاً ، قم بإنشاء مستند جديد ومولد المستندات المرتبط به:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة الثانية: إنشاء وتخصيص القائمة الأولى

بعد ذلك ، قم بإنشاء قائمة بناءً على قالب موجود ، ثم قم بتخصيص مستوياته:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## الخطوة 3: إضافة عناصر إلى القائمة الأولى

استخدم منشئ المستندات لإضافة عناصر إلى القائمة الأولى وإزالة أرقام القائمة:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## الخطوة 4: إنشاء وتخصيص القائمة الثانية

لإعادة استخدام القائمة الأولى عن طريق إعادة تعيين الرقم ، قم بإنشاء نسخة من تخطيط القائمة الأصلي:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

يمكنك أيضًا إجراء تغييرات إضافية على القائمة الثانية إذا لزم الأمر.

## الخطوة 5: إضافة عناصر إلى القائمة الثانية

استخدم منشئ المستندات مرة أخرى لإضافة عناصر إلى القائمة الثانية وإزالة أرقام القائمة:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## الخطوة 6: احفظ المستند المعدل

أخيرًا ، احفظ المستند المعدل:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

لذا ! لقد نجحت في إعادة تعيين رقم قائمة في مستند Word باستخدام Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لإعادة تعيين رقم القائمة

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء قائمة تستند إلى قالب.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// لإعادة استخدام القائمة الأولى ، نحتاج إلى إعادة تشغيل الترقيم عن طريق إنشاء نسخة من تنسيق القائمة الأصلي.
List list2 = doc.Lists.AddCopy(list1);

// يمكننا تعديل القائمة الجديدة بأي طريقة ، بما في ذلك تعيين رقم بدء جديد.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```




