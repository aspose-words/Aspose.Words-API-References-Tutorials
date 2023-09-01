---
title: بناء الجدول في مستند Word
linktitle: بناء الجدول في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء جدول في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/build-table/
---
في هذا البرنامج التعليمي خطوة بخطوة، ستتعلم كيفية إنشاء جدول في مستند Word باستخدام Aspose.Words for .NET. سنرشدك خلال العملية ونزودك بمقتطفات التعليمات البرمجية اللازمة لـ C#. بحلول نهاية هذا الدليل، ستتمكن من إنشاء جدول بتنسيق ومحتوى مخصصين باستخدام فئة DocumentBuilder.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Words لمكتبة .NET المثبتة على نظامك.

## الخطوة 1: إنشاء مستند جديد
للبدء، قم بإنشاء مستند جديد باستخدام فئة المستند:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: ابدأ الجدول
بعد ذلك، استخدم أسلوب StartTable لفئة DocumentBuilder لبدء إنشاء الجدول:

```csharp
Table table = builder.StartTable();
```

## الخطوة 3: إدراج الخلايا وإضافة المحتوى
يمكنك الآن إدراج خلايا في الجدول وإضافة محتوى إليها باستخدام طريقتي InsertCell وWrite لفئة DocumentBuilder. تخصيص تنسيق الخلية حسب الحاجة:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## الخطوة 4: إنهاء الصف
بعد إضافة محتوى إلى خلايا الصف الأول، استخدم طريقة EndRow لفئة DocumentBuilder لإنهاء الصف:

```csharp
builder.EndRow();
```

## الخطوة 5: تخصيص تنسيق الصف
يمكنك تخصيص تنسيق الصف عن طريق تعيين خصائص كائني RowFormat وCellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## الخطوة 6: إنهاء الجدول
لإكمال الجدول، استخدم طريقة EndTable لفئة DocumentBuilder:

```csharp
builder.EndTable();
```

### مثال على التعليمات البرمجية المصدرية لإنشاء جدول باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لإنشاء جدول باستخدام Aspose.Words لـ .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إنشاء جدول في مستند Word باستخدام Aspose.Words لـ .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام كود المصدر المقدم، يمكنك الآن إنشاء جداول بتنسيق مخصص.

### الأسئلة الشائعة حول إنشاء جدول في مستند Word

#### س: ما هو Aspose.Words لـ .NET؟

ج: Aspose.Words for .NET هي مكتبة قوية لمعالجة المستندات تتيح للمطورين إنشاء مستندات Microsoft Word وقراءتها وتحريرها وتحويلها برمجيًا في تطبيقات .NET. فهو يوفر مجموعة واسعة من الميزات للعمل مع مستندات Word، مثل معالجة النص وإنشاء الجدول وحماية المستندات والتنسيق والمزيد.

#### س: كيف يمكنني إنشاء جدول في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: لإنشاء جدول في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:
1.  إنشاء مثيل جديد لـ`Document` فئة و أ`DocumentBuilder` هدف.
2.  استخدم ال`StartTable` طريقة`DocumentBuilder`الصف للبدء في بناء الجدول.
3.  قم بإدراج الخلايا في الجدول وإضافة محتوى باستخدام`InsertCell` و`Write` أساليب`DocumentBuilder` فصل.
4.  قم بإنهاء الصف باستخدام`EndRow` طريقة`DocumentBuilder` فصل.
5.  تخصيص تنسيق الصف عن طريق تعيين خصائص`RowFormat` و`CellFormat` أشياء.
6.  قم بإنهاء الجدول باستخدام`EndTable` طريقة`DocumentBuilder` فصل.
7. احفظ المستند.

#### س: كيف يمكنني تخصيص تنسيق الجدول وخلاياه؟

 ج: يمكنك تخصيص تنسيق الجدول وخلاياه عن طريق تعيين خصائص مختلفة للجدول`RowFormat` و`CellFormat` أشياء. على سبيل المثال، يمكنك ضبط محاذاة الخلية واتجاه النص الرأسي والأفقي وارتفاع الخلية وارتفاع الصف والمزيد. باستخدام هذه الخصائص، يمكنك تحقيق المظهر المطلوب للجدول ومحتوياته.

#### س: هل يمكنني إنشاء جداول معقدة تحتوي على خلايا مدمجة وميزات متقدمة أخرى؟

 ج: نعم، يوفر Aspose.Words for .NET ميزات متقدمة لإنشاء جداول معقدة، بما في ذلك دعم الخلايا المدمجة والجداول المتداخلة وتخطيطات الجداول المعقدة. يمكنك استخدام ال`MergeCells` طريقة دمج الخلايا,`StartTable`طريقة لإنشاء جداول متداخلة، وطرق أخرى لتحقيق بنية الجدول المطلوبة.

#### س: هل يتوافق Aspose.Words for .NET مع تنسيقات مستندات Word المختلفة؟

ج: نعم، يتوافق Aspose.Words for .NET مع العديد من تنسيقات مستندات Word، بما في ذلك DOC وDOCX وRTF والمزيد. وهو يدعم كلاً من التنسيقات القديمة (DOC) والتنسيقات الحديثة المستندة إلى XML (DOCX) ويسمح لك بالعمل مع المستندات بتنسيقات مختلفة دون أي مشاكل.

#### س: أين يمكنني العثور على مزيد من المعلومات والوثائق الخاصة بـ Aspose.Words for .NET؟

 ج: يمكنك العثور على وثائق شاملة وأمثلة على التعليمات البرمجية على[مراجع واجهة برمجة التطبيقات](https://reference.aspose.com/words/net/). ستوفر الوثائق معلومات تفصيلية حول ميزات المكتبة وكيفية استخدامها في تطبيقات .NET الخاصة بك.