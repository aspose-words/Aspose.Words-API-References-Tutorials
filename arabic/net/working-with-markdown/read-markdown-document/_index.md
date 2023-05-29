---
title: اقرأ مستند Markdown
linktitle: اقرأ مستند Markdown
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية قراءة مستند تخفيض السعر باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/read-markdown-document/
---

في هذا المثال ، سنرشدك إلى كيفية قراءة مستند Markdown باستخدام Aspose.Words for .NET Markdown هي لغة ترميز خفيفة الوزن تُستخدم لتنسيق نص عادي.

## الخطوة 1: قراءة مستند Markdown

 أولاً ، سنستخدم ملف`Document` فئة لقراءة مستند Markdown. نحتاج إلى تحديد مسار ملف Markdown لقراءته.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Quotes.md");
```

## الخطوة 2: إزالة تنسيق الرأس

يمكننا إزالة التنسيق من العنوان في الفقرة الأخيرة من المستند. في هذا المثال ، نقوم بتعيين نمط "اقتباس" للفقرة.

```csharp
Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
paragraph.ParagraphFormat.Style = doc.Styles["Quote"];
```

## الخطوة 3: حفظ المستند

أخيرًا ، يمكننا حفظ المستند بالتنسيق المطلوب.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
```

### مثال على شفرة المصدر لقراءة مستند Markdown مع Aspose.Words for .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Quotes.md");

// دعنا نزيل تنسيق العنوان من عرض الأسعار في الفقرة الأخيرة.
Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
paragraph.ParagraphFormat.Style = doc.Styles["Quote"];

doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
```

تهنئة ! لقد تعلمت الآن كيفية قراءة مستند Markdown باستخدام Aspose.Words for .NET.

