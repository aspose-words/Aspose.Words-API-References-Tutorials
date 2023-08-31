---
title: قم بإدراج جدول المحتويات في مستند Word
linktitle: قم بإدراج جدول المحتويات في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج جدول محتويات في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/insert-table-of-contents/
---
في هذا البرنامج التعليمي الشامل ، ستتعلم كيفية إدراج جدول محتويات في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من إنشاء جدول محتويات بالعناوين المناسبة وأرقام الصفحات.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل جدول المحتويات
بعد ذلك ، استخدم الأسلوب InsertTableOfContents لفئة DocumentBuilder لإدراج جدول محتويات. حدد خيارات التنسيق المطلوبة في الطريقة:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## الخطوة 3: إضافة محتوى المستند
بعد إدراج جدول المحتويات ، أضف محتوى المستند الفعلي. قم بتعيين أنماط العناوين المناسبة باستخدام StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## الخطوة 4: تحديث جدول المحتويات
سيكون جدول المحتويات المُدرج حديثًا فارغًا في البداية. لتعبئتها ، قم بتحديث الحقول في المستند:

```csharp
doc.UpdateFields();
```

## الخطوة 5: احفظ المستند
بعد إدراج جدول المحتويات وتحديث الحقول ، احفظ المستند في ملف باستخدام طريقة Save من فئة Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### مثال كود المصدر لإدراج جدول المحتويات باستخدام Aspose.Words for .NET
فيما يلي الكود المصدري الكامل لإدخال جدول محتويات باستخدام Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// تهيئة DocumentBuilder بكائن المستند
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إدراج جدول المحتويات
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// ابدأ محتوى المستند الفعلي في الصفحة الثانية.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// سيكون جدول المحتويات المُدرج حديثًا فارغًا في البداية.
// يجب أن يتم ملؤها عن طريق تحديث الحقول في المستند.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية إدراج جدول محتويات في مستند Word باستخدام Aspose.Words for .NET. باتباع هذا الدليل المفصل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن إنشاء جدول محتويات بالعناوين المناسبة وأرقام الصفحات لمستنداتك.

### الأسئلة الشائعة حول إدراج جدول المحتويات في مستند Word

#### س: هل يمكنني تخصيص مظهر جدول المحتويات؟

 ج: نعم ، يمكنك تخصيص مظهر جدول المحتويات عن طريق تعديل خيارات التنسيق المحددة في ملف`InsertTableOfContents` طريقة. تسمح لك المعلمات بالتحكم في أرقام الصفحات والمسافة البادئة والأنماط الأخرى.

#### س: ماذا لو أردت تضمين مستويات عناوين معينة في جدول المحتويات؟

 ج: يمكنك تحديد مستويات العناوين المرغوبة لتضمينها في جدول المحتويات عن طريق ضبط القيمة داخل`InsertTableOfContents` طريقة. على سبيل المثال ، باستخدام`"\\o \"1-3\""` ستشمل مستويات العنوان من 1 إلى 3.

#### س: هل يمكنني تحديث جدول المحتويات تلقائيًا إذا قمت بإجراء تغييرات على محتوى المستند؟

 ج: نعم ، يمكنك تحديث جدول المحتويات تلقائيًا عن طريق الاتصال بـ`UpdateFields` الطريقة على المستند. سيضمن ذلك انعكاس أي تغييرات يتم إجراؤها على محتوى المستند ، مثل إضافة العناوين أو إزالتها ، في جدول المحتويات.

#### س: كيف يمكنني تنسيق مستويات العناوين في جدول المحتويات بشكل مختلف؟

 ج: يمكنك نمط مستويات العناوين بشكل مختلف باستخدام أنماط فقرة مختلفة لكل مستوى عنوان. عن طريق تعيين مختلف`StyleIdentifier` قيم`ParagraphFormat` التابع`DocumentBuilder`، يمكنك إنشاء أنماط مميزة لكل مستوى عنوان.

#### س: هل يمكن إضافة تنسيق إضافي إلى العناوين في جدول المحتويات؟

 ج: نعم ، يمكنك إضافة تنسيق إضافي إلى العناوين في جدول المحتويات ، مثل أنماط الخطوط أو الألوان أو الخصائص الأخرى. عن طريق ضبط`Font` خصائص`DocumentBuilder`، يمكنك تطبيق تنسيق مخصص على العناوين.