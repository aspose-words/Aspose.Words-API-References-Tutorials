---
title: تغيير Toc Tab Stops
linktitle: تغيير Toc Tab Stops
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تغيير علامات تبويب جدول المحتويات في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C #. من بين الوظائف التي تقدمها Aspose.Words ، هناك إمكانية تعديل علامات التبويب المستخدمة في جدول محتويات مستند Word. في هذا الدليل ، سنوضح لك كيفية استخدام شفرة المصدر C # الخاصة بـ Aspose.Words for .NET لتغيير علامات التبويب في جدول محتويات المستند.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة شائعة تجعل العمل مع مستندات Word أمرًا سهلاً وفعالاً. يوفر مجموعة واسعة من الميزات لإنشاء مستندات Word وتحريرها ومعالجتها ، بما في ذلك علامات تبويب جدول المحتويات المتغيرة.

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