---
title: استخدم حرف المسافة لكل مستوى للمسافة البادئة للقائمة
linktitle: استخدم حرف المسافة لكل مستوى للمسافة البادئة للقائمة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لاستخدام حرف المسافة لكل مستوى للمسافة البادئة للقائمة في Aspose.Words لـ .NET. قم بإنشاء مستندات Word جيدة التنظيم بسهولة.
type: docs
weight: 10
url: /ar/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
تعد Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C#. من بين الميزات التي يقدمها Aspose.Words هي إمكانية استخدام حرف مسافة واحد لكل مستوى لوضع مسافة بادئة للقوائم. سنوضح لك في هذا الدليل كيفية استخدام الكود المصدري لـ C# الخاص بـ Aspose.Words لـ .NET لتنفيذ هذه الوظيفة.

## فهم مكتبة Aspose.Words

قبل الغوص في التعليمات البرمجية، من المهم فهم مكتبة Aspose.Words الخاصة بـ .NET. Aspose.Words هي مكتبة شائعة تجعل معالجة الكلمات باستخدام مستندات Word سهلة وفعالة. فهو يوفر نطاقًا واسعًا من الوظائف لإنشاء مستندات Word وتعديلها ومعالجتها، بما في ذلك إدارة القوائم والمسافات البادئة.

## إنشاء المستند وإضافة المحتوى

الخطوة الأولى هي إنشاء مستند جديد وإضافة محتوى إليه. استخدم فئة المستند لإنشاء مثيل مستند جديد. ثم استخدم فئة DocumentBuilder لإضافة نص وإنشاء قائمة بمستويات متعددة من المسافة البادئة. هنا مثال :

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

في هذا المثال، نقوم بإنشاء مستند جديد واستخدام DocumentBuilder لإضافة نص وإنشاء قائمة بثلاثة مستويات من المسافة البادئة. لقد أضفنا ثلاثة عناصر إلى القائمة، مع وضع مسافة بادئة لكل عنصر في مستوى إضافي.

## استخدام حرف مسافة واحد لكل مستوى للمسافة البادئة للقائمة

بمجرد إضافة المحتوى، يمكننا الآن تكوين المسافة البادئة للقوائم باستخدام حرف مسافة واحد لكل مستوى. لهذا نستخدم فئة TxtSaveOptions وقمنا بتعيين الخاصية ListIndentation.Count على عدد مستويات المسافة البادئة والخاصية ListIndentation.Character على حرف المسافة المطلوب استخدامه. إليك الطريقة:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

في هذا المثال، قمنا بإنشاء مثيل لـ TxtSaveOptions وقمنا بتعيين الخاصية ListIndentation.Count إلى 3 للإشارة إلى وجود ثلاثة مستويات من المسافة البادئة في القائمة. قمنا أيضًا بتعيين خاصية ListIndentation.Character على حرف المسافة (' ') الذي نريد استخدامه للمسافة البادئة.

### مثال على التعليمات البرمجية المصدر لميزة "استخدام حرف مسافة واحد لكل مستوى للمسافة البادئة للقائمة" مع Aspose.Words for .NET

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
             // المسار إلى دليل المستندات الخاص بك
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // قم بإنشاء المستند وإضافة المحتوى
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // قم بإنشاء قائمة بثلاثة مستويات من المسافة البادئة
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // استخدم حرف مسافة واحد لكل مستوى للمسافة البادئة للقائمة
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

في هذا الدليل، شرحنا كيفية استخدام Aspose.Words لـ .NET لتطبيق وظيفة "استخدام حرف مسافة واحد لكل مستوى للمسافة البادئة للقائمة". باتباع الخطوات المقدمة واستخدام كود مصدر C# المقدم، يمكنك بسهولة تكوين المسافة البادئة للقوائم في مستندات Word الخاصة بك باستخدام حرف مسافة واحد لكل مستوى. يوفر Aspose.Words مرونة وقوة هائلة لمعالجة الكلمات من خلال تنسيق النص وإدارة القائمة، مما يسمح لك بإنشاء مستندات جيدة التنظيم في تطبيق C# الخاص بك.

### أسئلة مكررة

#### س: ما هو Aspose.Words لـ .NET؟
تعد Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C#. وهو يقدم العديد من الميزات لمعالجة الكلمات مع مستندات Word، بما في ذلك القدرة على استخدام مسافة واحدة لكل مستوى لوضع مسافة بادئة في القوائم.

#### س: كيف يمكنني استخدام مسافة واحدة لكل مستوى لوضع مسافة بادئة للقائمة باستخدام Aspose.Words for .NET؟
يمكنك استخدام مسافة واحدة لكل مستوى للمسافة البادئة للقائمة باتباع الخطوات التالية:

 قم بإنشاء مستند جديد باستخدام`Document` فصل.

 استخدم ال`DocumentBuilder`class لإضافة محتوى إلى المستند وإنشاء قائمة بمستويات متعددة من المسافة البادئة.

 بمجرد إضافة المحتوى وتكوين المسافة البادئة للقائمة، استخدم`TxtSaveOptions` فئة وتعيين`ListIndentation.Count` الخاصية إلى عدد مستويات المسافة البادئة و`ListIndentation.Character` الملكية على الفضاء (`' '`) ليستخدم.

 احفظ المستند بالخيارات المحددة باستخدام الملف`Save` طريقة`Document` فصل.

#### س: هل يدعم Aspose.Words الأحرف الأخرى لوضع مسافة بادئة للقائمة؟
نعم، يدعم Aspose.Words الأحرف الأخرى لوضع مسافة بادئة في القوائم. يمكنك استخدام أحرف غير المسافات البيضاء، مثل علامات التبويب (`'\t'` ) أو أحرف خاصة أخرى، عن طريق تعيين`ListIndentation.Character` الملكية إلى الحرف المطلوب.

#### س: هل من الممكن تخصيص عدد المسافات لكل مستوى للمسافة البادئة للقائمة؟
 نعم، يمكنك تخصيص عدد المسافات لكل مستوى للمسافة البادئة للقائمة عن طريق تغيير قيمة`ListIndentation.Count` الممتلكات في`TxtSaveOptions` فصل. يمكنك تحديد عدد المسافات التي تريدها لكل مستوى من المسافة البادئة.

#### س: ما هي الميزات الأخرى التي يقدمها Aspose.Words لإدارة القائمة؟
يقدم Aspose.Words العديد من الميزات لإدارة القوائم في مستندات Word. يمكنك إنشاء قوائم مرقمة أو نقطية، وتعيين مستويات المسافة البادئة، وتخصيص نمط القوائم، وإضافة عناصر القائمة، والمزيد.