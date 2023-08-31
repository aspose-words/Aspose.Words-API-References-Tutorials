---
title: تحديد مستوى القائمة
linktitle: تحديد مستوى القائمة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحديد مستوى القائمة في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-list/specify-list-level/
---

في هذا البرنامج التعليمي خطوة بخطوة، سنوضح لك كيفية تحديد مستوى القائمة في مستند Word باستخدام Aspose.Words for .NET. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

 للبدء، تأكد من تثبيت Aspose.Words for .NET وتكوينه في بيئة التطوير لديك. إذا لم تكن قد قمت بذلك بالفعل، قم بتنزيل المكتبة وتثبيتها من[Aspose.Releases]https://releases.aspose.com/words/net/.

## الخطوة 1: إنشاء المستند ومولد المستندات

أولاً، قم بإنشاء مستند جديد ومولد المستندات المرتبط به:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إنشاء قائمة مرقمة وتطبيقها

بعد ذلك، قم بإنشاء قائمة مرقمة بناءً على أحد قوالب قوائم Microsoft Word وقم بتطبيقها على الفقرة الحالية في أداة إنشاء المستندات:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## الخطوة 3: قائمة مواصفات المستوى

 استخدم أداة إنشاء المستندات`ListLevelNumber` الخاصية لتحديد مستوى القائمة وإضافة نص إلى الفقرة:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

كرر هذه الخطوات لتحديد مستويات القائمة وإضافة نص في كل مستوى.

## الخطوة 4: إنشاء وتطبيق قائمة ذات تعداد نقطي

يمكنك أيضًا إنشاء قائمة ذات تعداد نقطي وتطبيقها باستخدام أحد قوالب قوائم Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## الخطوة 5: إضافة نص إلى مستويات القائمة ذات التعداد النقطي

 استخدم ال`ListLevelNumber` الخاصية مرة أخرى لتحديد مستوى القائمة ذات التعداد النقطي وإضافة نص:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## الخطوة 6: إيقاف قائمة التنسيق

 لإيقاف تنسيق القائمة، قم بتعيين`null` إلى`List` خاصية مولد الوثيقة:

```csharp
builder. ListFormat. List = null;
```

## الخطوة 7: حفظ المستند المعدل

احفظ المستند المعدل:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

لذا ! لقد نجحت في تحديد مستوى القائمة في مستند Word باستخدام Aspose.Words لـ .NET.

### نموذج التعليمات البرمجية المصدر لتحديد مستوى القائمة

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//قم بإنشاء قائمة مرقمة بناءً على أحد قوالب قوائم Microsoft Word
// وتطبيقه على الفقرة الحالية لمنشئ المستندات.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// هناك تسعة مستويات في هذه القائمة، دعونا نجربهم جميعا.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// قم بإنشاء قائمة ذات تعداد نقطي استناداً إلى أحد قوالب قوائم Microsoft Word
// وتطبيقه على الفقرة الحالية لمنشئ المستندات.
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

### الأسئلة الشائعة

#### س: كيف يمكنني تحديد مستوى القائمة في Aspose.Words؟

 ج: لتحديد مستوى القائمة في Aspose.Words، تحتاج إلى إنشاء مثيل لـ`List` الصف وإعطائه قائمة مرقمة. ثم يمكنك استخدام`Paragraph.ListFormat.ListLevelNumber` الخاصية لتحديد مستوى كل عنصر في القائمة. يمكنك ربط هذه القائمة بقسم من مستندك حتى تصل عناصر القائمة إلى المستوى المطلوب.

#### س: هل من الممكن تغيير تنسيق ترقيم عناصر القائمة في Aspose.Words؟

 ج: نعم، يمكنك تغيير تنسيق الترقيم لعناصر القائمة في Aspose.Words. ال`ListLevel` تقدم الطبقة العديد من الخصائص لهذا، مثل`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`يمكنك استخدام هذه الخصائص لتعيين تنسيق الترقيم لعناصر القائمة، مثل الأرقام العربية والأرقام الرومانية والحروف وما إلى ذلك.

#### س: هل يمكنني إضافة مستويات إضافية إلى قائمة مرقمة في Aspose.Words؟

 ج: نعم، من الممكن إضافة مستويات إضافية إلى القائمة المرقمة في Aspose.Words. ال`ListLevel` يسمح لك class بتعيين خصائص التنسيق لكل مستوى من القائمة. يمكنك تعيين خيارات مثل البادئة، واللاحقة، والمحاذاة، والمسافة البادئة، وما إلى ذلك. ويتيح لك ذلك إنشاء قوائم ذات مستويات متعددة من التسلسل الهرمي.


