---
title: إعادة تشغيل رقم القائمة
linktitle: إعادة تشغيل رقم القائمة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إعادة تعيين رقم القائمة في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-list/restart-list-number/
---
في هذا البرنامج التعليمي خطوة بخطوة، سنوضح لك كيفية إعادة تعيين رقم القائمة في مستند Word باستخدام Aspose.Words for .NET. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

 للبدء، تأكد من تثبيت Aspose.Words for .NET وتكوينه في بيئة التطوير لديك. إذا لم تكن قد قمت بذلك بالفعل، قم بتنزيل المكتبة وتثبيتها من[Aspose.Releases]https://releases.aspose.com/words/net/.

## الخطوة 1: إنشاء المستند ومولد المستندات

أولاً، قم بإنشاء مستند جديد ومولد المستندات المرتبط به:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إنشاء القائمة الأولى وتخصيصها

بعد ذلك، قم بإنشاء قائمة بناءً على قالب موجود، ثم قم بتخصيص مستوياتها:

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

لإعادة استخدام القائمة الأولى عن طريق إعادة تعيين الرقم، قم بإنشاء نسخة من تخطيط القائمة الأصلي:

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

وأخيرا، احفظ الوثيقة المعدلة:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

لذا ! لقد نجحت في إعادة تعيين رقم القائمة في مستند Word باستخدام Aspose.Words لـ .NET.

### نموذج التعليمات البرمجية المصدر لإعادة تعيين رقم القائمة

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء قائمة بناءً على القالب.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// لإعادة استخدام القائمة الأولى، نحتاج إلى إعادة تشغيل الترقيم عن طريق إنشاء نسخة من تنسيق القائمة الأصلي.
List list2 = doc.Lists.AddCopy(list1);

//يمكننا تعديل القائمة الجديدة بأي شكل من الأشكال، بما في ذلك تحديد رقم بداية جديد.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### الأسئلة الشائعة

#### س: كيف يمكنني إعادة تشغيل ترقيم القائمة في Aspose.Words؟

 ج: لإعادة تشغيل ترقيم القائمة في Aspose.Words، يمكنك استخدام الأمر`ListRestartAtNumber` طريقة`List` فصل. تسمح لك هذه الطريقة بتعيين قيمة طلب جديدة يجب إعادة تشغيل القائمة منها. على سبيل المثال، يمكنك استخدام`list.ListRestartAtNumber(1)` لإعادة تشغيل الترقيم من 1.

#### س: هل من الممكن تخصيص البادئة واللاحقة لترقيم القائمة المعاد تشغيلها في Aspose.Words؟

 ج: نعم، يمكنك تخصيص البادئة واللاحقة لترقيم القائمة المعاد تشغيلها في Aspose.Words. ال`ListLevel` يقدم الفصل خصائص مثل`ListLevel.NumberPrefix` و`ListLevel.NumberSuffix` والتي تسمح لك بتحديد البادئة واللاحقة لكل مستوى في القائمة. يمكنك استخدام هذه الخصائص لتخصيص البادئة واللاحقة حسب الحاجة.

#### س: كيف يمكنني تحديد قيمة ترقيم معينة يجب إعادة تشغيل القائمة منها؟

 ج: لتحديد قيمة رقمية محددة يجب إعادة تشغيل القائمة منها، يمكنك استخدام الأمر`ListRestartAtNumber`طريقة تمرير القيمة المطلوبة كوسيطة. على سبيل المثال، لإعادة بدء الترقيم من 5، يمكنك استخدام`list.ListRestartAtNumber(5)`.

#### س: هل من الممكن إعادة تشغيل ترقيم القائمة متعدد المستويات في Aspose.Words؟

 ج: نعم، يدعم Aspose.Words إعادة ترقيم مستويات القائمة المتعددة. يمكنك تطبيق`ListRestartAtNumber` طريقة على كل مستوى قائمة لإعادة تشغيل الترقيم بشكل فردي. على سبيل المثال، يمكنك استخدام`list.Levels[0].ListRestartAtNumber(1)` لإعادة تشغيل مستوى القائمة الأول من 1، و`list.Levels[1].ListRestartAtNumber(1)` لإعادة تشغيل قائمة المستوى الثاني بدءًا من الرقم 1، وهكذا.



