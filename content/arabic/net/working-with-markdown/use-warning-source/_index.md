---
title: استخدم مصدر التحذير
linktitle: استخدم مصدر التحذير
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام مصدر التحذير مع دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/use-warning-source/
---

في هذا المثال، سنوضح لك كيفية استخدام مصدر التحذير مع Aspose.Words لـ .NET. يشير مصدر التحذير إلى أصل التحذير عند استخدام وظيفة رد الاتصال.

## الخطوة 1: تحميل الوثيقة

 سنقوم بتحميل مستند موجود يحتوي على تحذيرات باستخدام ملف`Load` طريقة`Document` فصل.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## الخطوة 3: استخدام مصدر التحذير

 سنستخدم مصدر التحذير عن طريق تعيين المستند`WarningCallback` الملكية لمجموعة من`WarningInfo` أشياء.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## الخطوة 4: حفظ الوثيقة

وأخيرا، يمكننا حفظ المستند بالتنسيق المطلوب.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### مثال على كود المصدر لاستخدام مصدر التحذير مع Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

تهنئة ! لقد تعلمت الآن كيفية استخدام مصدر التحذير مع Aspose.Words لـ .NET.

### الأسئلة الشائعة

#### س: هل يمكننا تخصيص مظهر علامة "التحذير"؟

ج: يعتمد تنسيق علامة "التحذير" على عارض Markdown المستخدم. في معظم الحالات، يمكنك تخصيص المظهر باستخدام CSS لاستهداف`blockquote` علامة في المستند الخاص بك.

#### س: هل يمكن إضافة أيقونات إلى علامة "التحذير"؟

 ج: نعم، من الممكن إضافة أيقونات إلى علامة "تحذير" باستخدام كود HTML في مستند Markdown الخاص بك. يمكنك إدراج أ`span` ضع علامة بالفئة المناسبة لعرض أيقونة بجوار نص التحذير.

#### س: هل علامة "التحذير" متوافقة مع جميع أجهزة قراءة Markdown؟

 ج: يعتمد توافق علامة "التحذير" على عرض Markdown المستخدم. سيدعم معظم قراء Markdown`blockquote` لعرض النص المميز، ولكن قد يختلف المظهر الدقيق.