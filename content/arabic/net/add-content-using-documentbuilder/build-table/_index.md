---
title: إنشاء جدول في مستند Word
linktitle: إنشاء جدول في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إنشاء جدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/build-table/
---
في هذا البرنامج التعليمي خطوة بخطوة ، ستتعلم كيفية إنشاء جدول في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من إنشاء جدول بتنسيق ومحتوى مخصصين باستخدام فئة DocumentBuilder.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: قم بإنشاء مستند جديد
للبدء ، أنشئ مستندًا جديدًا باستخدام فئة المستند:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: ابدأ الجدول
بعد ذلك ، استخدم طريقة StartTable لفئة DocumentBuilder لبدء إنشاء الجدول:

```csharp
Table table = builder.StartTable();
```

## الخطوة 3: أدخل الخلايا وأضف المحتوى
الآن ، يمكنك إدراج خلايا في الجدول وإضافة محتوى إليها باستخدام أساليب InsertCell و Write لفئة DocumentBuilder. قم بتخصيص تنسيق الخلية حسب الحاجة:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## الخطوة 4: قم بإنهاء الصف
بعد إضافة محتوى إلى خلايا الصف الأول ، استخدم طريقة EndRow لفئة DocumentBuilder لإنهاء الصف:

```csharp
builder.EndRow();
```

## الخطوة 5: تخصيص تنسيق الصفوف
يمكنك تخصيص تنسيق الصف عن طريق تعيين خصائص كائنات RowFormat و CellFormat:

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

## الخطوة 6: قم بإنهاء الجدول
لإكمال الجدول ، استخدم طريقة EndTable لفئة DocumentBuilder:

```csharp
builder.EndTable();
```

### مثال كود المصدر لبناء جدول باستخدام Aspose.Words for .NET
إليك الكود المصدري الكامل لبناء جدول باستخدام Aspose.Words for .NET:

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
تهانينا! لقد تعلمت بنجاح كيفية إنشاء جدول في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن إنشاء جداول بتنسيق مخصص.

### الأسئلة الشائعة لبناء الجدول في مستند Word

#### س: ما المقصود بـ Aspose.Words لـ .NET؟

ج: Aspose.Words for .NET هي مكتبة قوية لمعالجة المستندات تتيح للمطورين إنشاء مستندات Microsoft Word وقراءتها وتحريرها وتحويلها برمجيًا في تطبيقات .NET. يوفر مجموعة واسعة من الميزات للعمل مع مستندات Word ، مثل معالجة النص وإنشاء الجدول وحماية المستندات والتنسيق والمزيد.

#### س: كيف يمكنني إنشاء جدول في مستند Word باستخدام Aspose.Words for .NET؟

ج: لإنشاء جدول في مستند Word باستخدام Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:
1.  قم بإنشاء مثيل جديد لملف`Document` فئة وأ`DocumentBuilder` هدف.
2.  استخدم ال`StartTable` طريقة`DocumentBuilder` الصف لبدء بناء الجدول.
3. أدخل خلايا في الجدول وأضف المحتوى باستخدام ملف`InsertCell` و`Write` طرق`DocumentBuilder` فصل.
4.  قم بإنهاء الصف باستخدام ملف`EndRow` طريقة`DocumentBuilder` فصل.
5.  تخصيص تنسيق الصف عن طريق تعيين خصائص`RowFormat` و`CellFormat` أشياء.
6.  قم بإنهاء الجدول باستخدام ملف`EndTable` طريقة`DocumentBuilder` فصل.
7. احفظ المستند.

#### س: كيف يمكنني تخصيص تنسيق الجدول وخلاياه؟

 ج: يمكنك تخصيص تنسيق الجدول وخلاياه من خلال تعيين خصائص مختلفة لملف`RowFormat` و`CellFormat` أشياء. على سبيل المثال ، يمكنك ضبط محاذاة الخلية واتجاه النص الرأسي والأفقي وارتفاع الخلية وارتفاع الصف والمزيد. باستخدام هذه الخصائص ، يمكنك تحقيق المظهر المطلوب للجدول ومحتوياته.

#### س: هل يمكنني إنشاء جداول معقدة بخلايا مدمجة وميزات متقدمة أخرى؟

 ج: نعم ، يوفر Aspose.Words for .NET ميزات متقدمة لبناء جداول معقدة ، بما في ذلك دعم الخلايا المدمجة والجداول المتداخلة وتخطيطات الجدول المعقدة. يمكنك استخدام ال`MergeCells` طريقة لدمج الخلايا ،`StartTable`طريقة لإنشاء جداول متداخلة وطرق أخرى لتحقيق بنية الجدول المطلوبة.

#### س: هل يتوافق Aspose.Words for .NET مع تنسيقات مستندات Word المختلفة؟

ج: نعم ، Aspose.Words for .NET متوافق مع تنسيقات مستندات Word المختلفة ، بما في ذلك DOC و DOCX و RTF والمزيد. وهو يدعم كل من التنسيقات القديمة (DOC) والتنسيقات الحديثة المستندة إلى XML (DOCX) ويسمح لك بالعمل مع المستندات بتنسيقات مختلفة دون أي مشاكل.

#### س: أين يمكنني العثور على مزيد من المعلومات والوثائق الخاصة بـ Aspose.Words for .NET؟

 ج: يمكنك العثور على وثائق شاملة وأمثلة على التعليمات البرمجية[مراجع API](https://reference.aspose.com/words/net/). ستوفر الوثائق معلومات مفصلة حول ميزات المكتبة وكيفية استخدامها في تطبيقات .NET الخاصة بك.