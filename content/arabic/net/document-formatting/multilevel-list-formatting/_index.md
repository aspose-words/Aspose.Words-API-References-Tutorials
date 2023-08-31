---
title: تنسيق قائمة متعددة المستويات في مستند Word
linktitle: تنسيق قائمة متعددة المستويات في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء قائمة متعددة المستويات وتطبيق التنسيق المخصص في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/multilevel-list-formatting/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية استخدام تنسيق القائمة متعددة المستويات في ميزة مستند Word مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم الكود المصدري وتطبيق التغييرات.

## الخطوة 1: إنشاء وتكوين المستند

للبدء، قم بإنشاء مستند جديد وكائن DocumentBuilder مرتبط. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تنسيق القائمة متعددة المستويات

سنقوم الآن بتطبيق تنسيق القائمة متعددة المستويات باستخدام الطرق المتوفرة في كائن DocumentBuilder. إليك الطريقة:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## الخطوة 3: حفظ الوثيقة

 بعد إدراج حقل نموذج إدخال النص، احفظ المستند في الموقع المطلوب باستخدام الزر`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### مثال على التعليمات البرمجية المصدر لتنسيق القائمة متعددة المستويات باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لميزة تنسيق القائمة متعددة المستويات باستخدام Aspose.Words for .NET:


```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

باستخدام هذا الرمز، ستتمكن من إنشاء قائمة متعددة المستويات وتطبيق التنسيق المناسب على كل مستوى باستخدام Aspose.Words for .NET.


## خاتمة

في هذا البرنامج التعليمي، اكتشفنا عملية استخدام ميزة تنسيق القائمة متعددة المستويات في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة، يمكنك إنشاء قوائم منظمة جيدًا بمستويات متعددة، مما يعزز بنية مستنداتك وسهولة قراءتها.

### الأسئلة الشائعة

#### س: ما هي القائمة متعددة المستويات في مستند Word؟

ج: القائمة متعددة المستويات في مستند Word هي قائمة هرمية تسمح لك بتنظيم العناصر في مستويات مختلفة من العناصر الفرعية. فهو يساعد على تقديم المعلومات بطريقة منظمة، مما يسهل على القراء فهم المحتوى.

#### س: هل يمكنني تخصيص مظهر القائمة متعددة المستويات؟

ج: نعم، يمكنك تخصيص مظهر القائمة متعددة المستويات في مستند Word الخاص بك. من خلال تطبيق أنماط مختلفة، مثل النقاط أو الأرقام أو الحروف، وضبط المسافة البادئة والتباعد، يمكنك إنشاء قائمة منظمة وجذابة بصريًا.

#### س: هل يدعم Aspose.Words for .NET خيارات تنسيق القائمة الأخرى؟

ج: نعم، يوفر Aspose.Words for .NET مجموعة شاملة من الميزات لتنسيق القائمة. وهو يدعم أنواع مختلفة من القوائم، بما في ذلك القوائم النقطية، والقوائم المرقمة، والقوائم متعددة المستويات. يمكنك التعامل مع تنسيق القوائم وإضافة العناصر أو إزالتها وتخصيص مظهرها.

#### س: هل يمكنني استخدام Aspose.Words لـ .NET للعمل مع عناصر المستند الأخرى؟

ج: نعم، يوفر Aspose.Words for .NET إمكانات واسعة النطاق للعمل مع عناصر المستند المختلفة، مثل الفقرات والجداول والصور والمزيد. فهو يمكّنك من إنشاء مستندات Word وتعديلها وتحويلها برمجياً، مما يؤدي إلى تبسيط مهام معالجة المستندات.