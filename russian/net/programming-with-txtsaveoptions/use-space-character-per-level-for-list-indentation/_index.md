---
title: استخدم حرف المسافة لكل مستوى للمسافة البادئة للقائمة
linktitle: استخدم حرف المسافة لكل مستوى للمسافة البادئة للقائمة
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لاستخدام حرف مسافة لكل مستوى في قائمة المسافة البادئة في Aspose.Words for .NET. قم بإنشاء مستندات Word جيدة التنظيم بسهولة.
type: docs
weight: 10
url: /ru/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C #. من بين الميزات التي تقدمها Aspose.Words إمكانية استخدام حرف مسافة واحد لكل مستوى لعمل مسافة بادئة للقوائم. في هذا الدليل ، سنوضح لك كيفية استخدام كود المصدر C # الخاص بـ Aspose.Words for .NET لتنفيذ هذه الوظيفة.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة شائعة تجعل العمل مع مستندات Word أمرًا سهلاً وفعالاً. يوفر مجموعة واسعة من الوظائف لإنشاء وتعديل ومعالجة مستندات Word ، بما في ذلك إدارة القوائم والمسافة البادئة.

## إنشاء الوثيقة وإضافة المحتوى

تتمثل الخطوة الأولى في إنشاء مستند جديد وإضافة محتوى إليه. استخدم فئة المستند لإنشاء مثيل مستند جديد. ثم استخدم فئة DocumentBuilder لإضافة نص وإنشاء قائمة بمستويات متعددة من المسافة البادئة. هنا مثال :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء قائمة بثلاثة مستويات من المسافة البادئة
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

في هذا المثال ، نقوم بإنشاء مستند جديد واستخدام DocumentBuilder لإضافة نص وإنشاء قائمة بثلاثة مستويات من المسافة البادئة. لقد أضفنا ثلاثة عناصر إلى القائمة ، مع وضع مسافة بادئة لكل عنصر في مستوى إضافي.

## استخدام مسافة واحدة لكل مستوى للمسافة البادئة للقائمة

بمجرد إضافة المحتوى ، يمكننا الآن تكوين المسافة البادئة للقوائم باستخدام حرف مسافة واحد لكل مستوى. لهذا نستخدم فئة TxtSaveOptions وقمنا بتعيين خاصية ListIndentation.Count على عدد مستويات المسافة البادئة وخاصية ListIndentation.Character إلى حرف المسافة المراد استخدامه. إليك الطريقة:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

في هذا المثال ، أنشأنا مثيلًا لـ TxtSaveOptions وقمنا بتعيين خاصية ListIndentation.Count على 3 للإشارة إلى وجود ثلاثة مستويات من المسافة البادئة في القائمة. قمنا أيضًا بتعيين خاصية ListIndentation.Character إلى حرف المسافة ('') الذي نريد استخدامه للمسافة البادئة.

### مثال على شفرة المصدر لميزة "استخدام حرف مسافة واحد لكل مستوى للمسافة البادئة للقائمة" مع Aspose.Words for .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لميزة "استخدام حرف مسافة واحد لكل مستوى للمسافة البادئة للقائمة" مع Aspose.Words for .NET:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // المسار إلى دليل المستند الخاص بك
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // قم بإنشاء المستند وإضافة محتوى
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // قم بإنشاء قائمة بثلاثة مستويات من المسافة البادئة
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // استخدم مسافة واحدة لكل مستوى للمسافة البادئة للقائمة
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // احفظ المستند بالخيارات المحددة
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## خاتمة

في هذا الدليل ، أوضحنا كيفية استخدام Aspose.Words for .NET لتطبيق وظيفة "استخدام حرف مسافة واحد لكل مستوى من أجل المسافة البادئة للقائمة". باتباع الخطوات المقدمة واستخدام الكود المصدري C # المقدم ، يمكنك بسهولة تكوين المسافة البادئة للقوائم في مستندات Word الخاصة بك باستخدام حرف مسافة واحد لكل مستوى. يوفر Aspose.Words مرونة وقوة هائلة للعمل مع تنسيق النص وإدارة القوائم ، مما يسمح لك بإنشاء مستندات جيدة التنظيم في تطبيق C # الخاص بك.