---
title: إدراج جدول المحتويات في مستند Word
linktitle: إدراج جدول المحتويات في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج جدول محتويات في مستندات Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/insert-table-of-contents/
---
في هذا البرنامج التعليمي الشامل، ستتعلم كيفية إدراج جدول محتويات في مستند Word باستخدام Aspose.Words for .NET. سنرشدك خلال العملية ونزودك بمقتطفات التعليمات البرمجية اللازمة لـ C#. بحلول نهاية هذا الدليل، ستكون قادرًا على إنشاء جدول محتويات بالعناوين وأرقام الصفحات المناسبة.

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

## الخطوة 2: أدخل جدول المحتويات
بعد ذلك، استخدم أسلوب InsertTableOfContents لفئة DocumentBuilder لإدراج جدول محتويات. حدد خيارات التنسيق المطلوبة ضمن الطريقة:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## الخطوة 3: إضافة محتوى المستند
بعد إدراج جدول المحتويات، أضف محتوى المستند الفعلي. قم بتعيين أنماط العناوين المناسبة باستخدام StyleIdentifier:

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
سيكون جدول المحتويات المدرج حديثًا فارغًا في البداية. لملئها، قم بتحديث الحقول الموجودة في المستند:

```csharp
doc.UpdateFields();
```

## الخطوة 5: احفظ المستند
بعد إدراج جدول المحتويات وتحديث الحقول، احفظ المستند في ملف باستخدام طريقة الحفظ لفئة المستند:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### مثال على كود المصدر لإدراج جدول المحتويات باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لإدراج جدول المحتويات باستخدام Aspose.Words لـ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// تهيئة DocumentBuilder باستخدام كائن المستند
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إدراج جدول المحتوياتأ
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


// سيكون جدول المحتويات المدرج حديثًا فارغًا في البداية.
// ويجب ملؤها عن طريق تحديث الحقول الموجودة في المستند.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية إدراج جدول محتويات في مستند Word باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل التفصيلي واستخدام كود المصدر المقدم، يمكنك الآن إنشاء جدول محتويات بالعناوين وأرقام الصفحات المناسبة لمستنداتك.

### الأسئلة الشائعة حول إدراج جدول المحتويات في مستند Word

#### س: هل يمكنني تخصيص مظهر جدول المحتويات؟

 ج: نعم، يمكنك تخصيص مظهر جدول المحتويات عن طريق تعديل خيارات التنسيق المحددة في ملف`InsertTableOfContents` طريقة. تسمح لك المعلمات بالتحكم في أرقام الصفحات والمسافات البادئة والأنماط الأخرى.

#### س: ماذا لو كنت أرغب في تضمين مستويات عناوين محددة في جدول المحتويات؟

 ج: يمكنك تحديد مستويات العناوين المطلوبة لإدراجها في جدول المحتويات عن طريق ضبط القيمة داخل`InsertTableOfContents` طريقة. على سبيل المثال، باستخدام`"\\o \"1-3\""` سوف تشمل مستويات العنوان من 1 إلى 3.

#### س: هل يمكنني تحديث جدول المحتويات تلقائيًا إذا قمت بإجراء تغييرات على محتوى المستند؟

 ج: نعم، يمكنك تحديث جدول المحتويات تلقائيًا عن طريق الاتصال بـ`UpdateFields` الطريقة على الوثيقة سيضمن هذا أن أي تغييرات يتم إجراؤها على محتوى المستند، مثل إضافة أو إزالة العناوين، تنعكس في جدول المحتويات.

#### س: كيف يمكنني تصميم مستويات العناوين في جدول المحتويات بشكل مختلف؟

 ج: يمكنك تصميم مستويات العناوين بشكل مختلف باستخدام أنماط فقرات مختلفة لكل مستوى عنوان. عن طريق تعيين مختلفة`StyleIdentifier` القيم إلى`ParagraphFormat` التابع`DocumentBuilder`، يمكنك إنشاء أنماط مميزة لكل مستوى عنوان.

#### س: هل من الممكن إضافة تنسيق إضافي للعناوين في جدول المحتويات؟

 ج: نعم، يمكنك إضافة تنسيق إضافي إلى العناوين الموجودة في جدول المحتويات، مثل أنماط الخطوط أو الألوان أو خصائص أخرى. عن طريق ضبط`Font` خصائص`DocumentBuilder`، يمكنك تطبيق تنسيق مخصص على العناوين.