---
title: تغيير توقف علامة Toc في مستند Word
linktitle: تغيير توقف علامة Toc في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تغيير علامات تبويب جدول المحتويات في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C #. من بين الوظائف التي تقدمها Aspose.Words ، هناك إمكانية تعديل علامات التبويب المستخدمة في جدول محتويات مستند Word. في هذا الدليل ، سنوضح لك كيفية استخدام شفرة المصدر C # الخاصة بـ Aspose.Words for .NET لتغيير علامات التبويب في جدول محتويات المستند.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة شائعة تجعل معالجة الكلمات بمستندات Word سهلة وفعالة. يوفر مجموعة واسعة من الميزات لإنشاء مستندات Word وتحريرها ومعالجتها ، بما في ذلك علامات تبويب جدول المحتويات المتغيرة.

## تحميل المستند الذي يحتوي على جدول المحتويات

الخطوة الأولى هي تحميل مستند Word الذي يحتوي على جدول المحتويات الذي تريد تعديله. استخدم فئة المستند لتحميل المستند من الملف المصدر. هنا مثال :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

في هذا المثال ، نقوم بتحميل المستند "Table of content.docx" الموجود في دليل documents.

## تغيير علامات التبويب في جدول المحتويات

بمجرد تحميل المستند ، ننتقل إلى كل فقرة في المستند ونتحقق مما إذا كان قد تم تنسيقها باستخدام أنماط نتائج جدول المحتويات (TOC). إذا كان الأمر كذلك ، نقوم بتعديل علامات التبويب المستخدمة لمحاذاة أرقام الصفحات. إليك الطريقة:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

في هذا المثال ، نستخدم حلقة للتكرار خلال كل فقرة في المستند. نتحقق بعد ذلك من تنسيق الفقرة باستخدام أنماط نتيجة جدول المحتويات (TOC). إذا كان الأمر كذلك ، فإننا نصل إلى علامة التبويب الأولى المستخدمة في هذه الفقرة ونقوم بتعديلها عن طريق إزالة علامة التبويب القديمة وإضافة علامة تبويب جديدة بموضع معدل.

## احفظ المستند المعدل

بمجرد إجراء التغييرات اللازمة على علامات التبويب في جدول المحتويات ، يمكنك حفظ المستند المعدل باستخدام طريقة Save لفئة Document. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

في هذا المثال ، نحفظ المستند المعدل باسم "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### نموذج شفرة مصدر لميزة "تحرير جدول المحتويات" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند الذي يحتوي على جدول المحتويات
Document doc = new Document(dataDir + "Table of contents.docx");

// قم بتعديل علامات تبويب جدول المحتويات
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## خاتمة

في هذا الدليل ، قمنا بتغطية كيفية استخدام Aspose.Words for .NET لتغيير علامات التبويب في جدول محتويات مستند Word باستخدام الكود المصدري C # المقدم. باتباع الخطوات المقدمة ، يمكنك بسهولة تخصيص علامات تبويب جدول المحتويات في مستندات Word الخاصة بك في تطبيق C # الخاص بك. يوفر Aspose.Words مرونة وقوة هائلة للعمل مع أنماط وتنسيقات مستنداتك ، مما يسمح لك بإنشاء مستندات Word جذابة واحترافية.

### الأسئلة الشائعة حول علامات تبويب تغيير toc في مستند Word

#### س: ما هو الغرض من وظيفة "تغيير توقف علامة التبويب Toc في مستند Word" في Aspose.Words for .NET؟

ج: تتيح لك وظيفة "توقف علامة التبويب تغيير Toc في مستند Word" في Aspose.Words for .NET تعديل علامات الجدولة المستخدمة في جدول محتويات مستند Word. يمكّنك من تخصيص محاذاة وموضع أرقام الصفحات والعناوين المقابلة داخل جدول المحتويات.

#### س: ما المقصود بـ Aspose.Words لـ .NET؟

ج: Aspose.Words for .NET مكتبة قوية مصممة لمعالجة الكلمات باستخدام مستندات Word في تطبيقات .NET. يوفر ميزات شاملة لإنشاء مستندات Word وتحريرها ومعالجتها وتحويلها برمجيًا باستخدام C # أو لغات .NET الأخرى.

#### س: كيف يمكنني تحميل مستند Word يحتوي على جدول محتويات باستخدام Aspose.Words for .NET؟

 ج: لتحميل مستند Word يحتوي على جدول محتويات باستخدام Aspose.Words for .NET ، يمكنك استخدام`Document` الطبقة ومنشئها. من خلال توفير مسار ملف المستند ، يمكنك تحميله في ملف`Document` هدف. هذا مثال:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

يقوم مقتطف الشفرة هذا بتحميل المستند "Table of content.docx" الموجود في الدليل المحدد.

#### س: كيف يمكنني تغيير علامات التبويب المستخدمة في جدول المحتويات باستخدام Aspose.Words for .NET؟

 ج: بمجرد تحميل المستند ، يمكنك تكرار كل فقرة في المستند والتحقق من تنسيقها باستخدام أنماط نتائج جدول المحتويات (TOC). إذا تم تنسيق الفقرة كنمط جدول المحتويات ، يمكنك تعديل علامات التبويب المستخدمة لمحاذاة أرقام الصفحات. في Aspose.Words for .NET ، يمكنك الوصول إلى ملف`ParagraphFormat` خاصية كل فقرة لاسترداد وتعديل علامات الجدولة. هذا مثال:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

في هذا الرمز ، تتكرر الحلقة خلال كل فقرة في المستند. إذا كانت الفقرة تحتوي على نمط جدول المحتويات ، فإنها تصل إلى أول علامة توقف مستخدمة في تلك الفقرة ، وتزيلها ، وتضيف علامة جدولة جديدة بموضع معدل.

#### س: هل يمكنني تغيير علامات التبويب لمستويات متعددة في جدول المحتويات باستخدام Aspose.Words for .NET؟

ج: نعم ، يمكنك تغيير علامات التبويب لمستويات متعددة في جدول المحتويات باستخدام Aspose.Words for .NET. من خلال التكرار خلال كل فقرة والتحقق من نمط جدول المحتويات ، يمكنك تعديل علامات التبويب لكل مستوى على حدة. يمكنك الوصول إلى المستوى المطلوب من جدول المحتويات وضبط علامات الجدولة وفقًا لذلك.

#### س: كيف يمكنني حفظ المستند المعدل بعد تغيير علامات التبويب في جدول المحتويات باستخدام Aspose.Words for .NET؟

 ج: بعد إجراء التغييرات اللازمة على علامات التبويب في جدول المحتويات ، يمكنك حفظ المستند المعدل باستخدام امتداد`Save` طريقة`Document` فصل. قم بتوفير مسار الملف المطلوب واسم مستند الإخراج كمعامل لملف`Save` طريقة. هذا مثال:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

يحفظ هذا الرمز المستند المعدل كـ "WorkingWithTableOfContent.ChangeTocTabStops.docx".

#### س: هل يمكنني تخصيص جوانب أخرى من جدول المحتويات باستخدام Aspose.Words for .NET؟

ج: نعم ، باستخدام Aspose.Words for .NET ، يمكنك تخصيص جوانب مختلفة من جدول المحتويات. بصرف النظر عن تغيير علامات التبويب ، يمكنك تعديل أنماط الخط وحجمه ومحاذاة وخصائص التنسيق الأخرى لإدخالات جدول المحتويات وأرقام الصفحات. بالإضافة إلى ذلك ، يمكنك ضبط المسافة البادئة والتباعد والتنسيق للعناوين المقابلة.

#### س:. هل يمكنني تغيير محاذاة الجدولة والأحرف البادئة لجدول المحتويات باستخدام Aspose.Words for .NET؟

ج: نعم ، يمكنك تغيير محاذاة الجدولة والشخصيات البادئة لجدول المحتويات باستخدام Aspose.Words for .NET. من خلال الوصول إلى علامات الجدولة وضبط خصائص المحاذاة والقائد ، يمكنك التحكم في المحاذاة والمظهر المرئي لأرقام الصفحات والعناوين المقابلة في جدول المحتويات.

#### س: هل يدعم Aspose.Words for .NET تغيير الأنماط والتنسيق الأخرى في مستندات Word؟

ج: نعم ، يوفر Aspose.Words for .NET دعمًا شاملاً لتغيير أنماط وتنسيقات مختلفة في مستندات Word. يسمح لك بتعديل الأنماط لعناصر مختلفة مثل الفقرات والعناوين والجداول والقوائم والمزيد. يمكنك تغيير الخطوط والألوان والمحاذاة والمسافة البادئة والتباعد وجوانب التنسيق الأخرى وفقًا لمتطلباتك.

#### س: هل يمكنني تعديل علامات التبويب في جدول المحتويات في مستند Word موجود باستخدام Aspose.Words for .NET؟

ج: نعم ، يمكنك تعديل علامات التبويب في جدول المحتويات في مستند Word موجود باستخدام Aspose.Words for .NET. عن طريق تحميل المستند ، والتكرار خلال الفقرات ، وإجراء التغييرات اللازمة على علامات الجدولة ، يمكنك تحديث علامات التبويب في جدول المحتويات. أخيرًا ، احفظ المستند لتطبيق التعديلات.