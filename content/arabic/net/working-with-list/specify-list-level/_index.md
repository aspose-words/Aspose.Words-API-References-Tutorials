---
title: حدد مستوى القائمة
linktitle: حدد مستوى القائمة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تحديد مستوى القائمة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-list/specify-list-level/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوضح لك كيفية تحديد مستوى القائمة في مستند Word باستخدام Aspose.Words for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

 للبدء ، تأكد من تثبيت Aspose.Words for .NET وتهيئته في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل ، فقم بتنزيل المكتبة وتثبيتها من[Aspose.Releases] https://releases.aspose.com/words/net/.

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

 استخدم وثيقة منشئ`ListLevelNumber` لتحديد مستوى القائمة وإضافة نص إلى الفقرة:

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

//قم بإنشاء قائمة ذات تعداد رقمي استنادًا إلى أحد قوالب قائمة Microsoft Word
// وتطبيقه على الفقرة الحالية لمنشئ المستند.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// هناك تسعة مستويات في هذه القائمة ، دعونا نجربها جميعًا.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// قم بإنشاء قائمة ذات تعداد نقطي استنادًا إلى أحد قوالب قوائم Microsoft Word
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

### التعليمات

#### س: كيف يمكنني تحديد مستوى القائمة في Aspose.Words؟

 ج: لتحديد مستوى القائمة في Aspose.Words ، تحتاج إلى إنشاء مثيل لـ`List` فئة وإعطائها قائمة مرقمة. ثم يمكنك استخدام ملف`Paragraph.ListFormat.ListLevelNumber` الخاصية لتحديد مستوى كل عنصر قائمة. يمكنك إقران هذه القائمة بجزء من المستند الخاص بك بحيث تحتوي عناصر القائمة على المستوى المطلوب.

#### س: هل من الممكن تغيير تنسيق الترقيم لعناصر القائمة في Aspose.Words؟

 ج: نعم ، يمكنك تغيير تنسيق الترقيم لعناصر القائمة في Aspose.Words. ال`ListLevel` تقدم فئة عدة خصائص لهذا ، مثل`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`، إلخ. يمكنك استخدام هذه الخصائص لتعيين تنسيق الترقيم لعناصر القائمة ، مثل الأرقام العربية ، والأرقام الرومانية ، والأحرف ، وما إلى ذلك.

#### س: هل يمكنني إضافة مستويات إضافية إلى قائمة ذات تعداد رقمي في Aspose.Words؟

 ج: نعم ، من الممكن إضافة مستويات إضافية إلى قائمة ذات تعداد رقمي في Aspose.Words. ال`ListLevel` تسمح لك class بتعيين خصائص التنسيق لكل مستوى من القائمة. يمكنك تعيين خيارات مثل البادئة ، واللاحقة ، والمحاذاة ، والمسافة البادئة ، وما إلى ذلك. وهذا يسمح لك بإنشاء قوائم بمستويات متعددة من التسلسل الهرمي.

