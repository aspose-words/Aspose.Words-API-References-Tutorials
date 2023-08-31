---
title: إدراج فقرة في مستند Word
linktitle: إدراج فقرة في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج فقرات منسقة في مستندات Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/insert-paragraph/
---
في هذا البرنامج التعليمي الشامل، ستتعلم كيفية إدراج فقرات في مستند Word باستخدام Aspose.Words for .NET. سنرشدك خلال العملية ونزودك بمقتطفات التعليمات البرمجية اللازمة لـ C#. بحلول نهاية هذا الدليل، ستتمكن من إضافة فقرات منسقة إلى مستنداتك.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Words لمكتبة .NET المثبتة على نظامك.

## الخطوة 1: إنشاء مستند جديد وDocumentBuilder
للبدء، قم بإنشاء مستند جديد باستخدام فئة Document وقم بتهيئة كائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تعيين الخط والتنسيق
بعد ذلك، قم بإعداد خصائص الخط وتنسيق الفقرة باستخدام كائنات Font وParagraphFormat على التوالي:

```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## الخطوة 3: أدخل فقرة
بعد إعداد الخط والتنسيق، استخدم طريقة Writeln لفئة DocumentBuilder لإدراج فقرة كاملة:

```csharp
builder.Writeln("A whole paragraph.");
```

## الخطوة 4: احفظ المستند
بعد إدراج الفقرة، احفظ المستند في ملف باستخدام طريقة الحفظ لفئة المستند:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## مثال على كود المصدر لإدراج فقرة باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لإدراج فقرة باستخدام Aspose.Words لـ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;

builder.Writeln("A whole paragraph.");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إدراج فقرات منسقة في مستند Word باستخدام Aspose.Words لـ .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام كود المصدر المقدم، يمكنك الآن إضافة فقرات مخصصة بخطوط وتنسيقات ومواءمة محددة إلى مستنداتك.

### الأسئلة الشائعة حول إدراج فقرة في مستند Word

#### س: هل يمكنني إدراج فقرات متعددة بتنسيق مختلف في نفس المستند؟

 ج: نعم، يمكنك إدراج فقرات متعددة بتنسيق مختلف في نفس المستند باستخدام Aspose.Words for .NET. ما عليك سوى ضبط خصائص تنسيق الخط والفقرة قبل الاتصال بـ`Writeln` طريقة لكل فقرة.

#### س: كيف يمكنني ضبط تباعد الأسطر والمسافات البادئة للفقرات؟

 ج: يوفر Aspose.Words for .NET خيارات لتعيين تباعد الأسطر والمسافات البادئة للفقرات. يمكنك ضبط`LineSpacing` و`LeftIndent` خصائص`ParagraphFormat` كائن للسيطرة على هذه الجوانب.

#### س: هل من الممكن إدراج قوائم ذات تعداد نقطي أو رقمي باستخدام DocumentBuilder؟

 ج: نعم، يمكنك إنشاء قوائم ذات تعداد نقطي أو رقمي عن طريق ضبط الإعداد`ListFormat` خصائص`DocumentBuilder` هدف. يمكنك إضافة عناصر القائمة باستخدام`Writeln` الطريقة، وسيتم تطبيق نمط الترقيم أو التعداد النقطي تلقائيًا.

#### س: هل يمكنني إدراج ارتباطات تشعبية أو عناصر أخرى داخل الفقرات؟

 ج: بالتأكيد! يمكنك إدراج الارتباطات التشعبية والصور والعناصر الأخرى داخل الفقرات باستخدام`DocumentBuilder` فصل. يتيح لك ذلك إنشاء محتوى غني وتفاعلي ضمن فقراتك.

#### س: كيف يمكنني إدراج أحرف أو رموز خاصة في فقرة؟

 ج: لإدراج أحرف أو رموز خاصة، يمكنك استخدام`Writeln` طريقة مع تمثيل Unicode المطلوب أو استخدم`InsertSpecialChar` طريقة`DocumentBuilder` فصل.