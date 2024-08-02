---
title: تنسيق الجدول والخلية بحدود مختلفة
linktitle: تنسيق الجدول والخلية بحدود مختلفة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تنسيق الجداول والخلايا ذات الحدود المختلفة باستخدام Aspose.Words لـ .NET. قم بتحسين مستندات Word الخاصة بك باستخدام أنماط الجدول المخصصة وتظليل الخلايا.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---
## مقدمة

هل سبق لك أن حاولت جعل مستندات Word الخاصة بك تبدو أكثر احترافية من خلال تخصيص حدود الجداول والخلايا؟ إذا لم يكن الأمر كذلك، فأنت في علاج! سيرشدك هذا البرنامج التعليمي خلال عملية تنسيق الجداول والخلايا ذات الحدود المختلفة باستخدام Aspose.Words for .NET. تخيل أن لديك القدرة على تغيير مظهر جداولك باستخدام بضعة أسطر فقط من التعليمات البرمجية. مفتون؟ دعنا نتعمق ونستكشف كيف يمكنك تحقيق ذلك بسهولة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- فهم أساسي للبرمجة C#.
- تم تثبيت Visual Studio على جهاز الكمبيوتر الخاص بك.
-  Aspose.Words لمكتبة .NET. إذا لم تقم بتثبيته بعد، يمكنك تنزيله[هنا](https://releases.aspose.com/words/net/).
-  ترخيص Aspose صالح. يمكنك الحصول على نسخة تجريبية مجانية أو ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).

## استيراد مساحات الأسماء

للعمل مع Aspose.Words لـ .NET، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروعك. أضف ما يلي باستخدام التوجيهات في الجزء العلوي من ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System.Drawing;
```

## الخطوة 1: تهيئة المستند و DocumentBuilder

أولاً، تحتاج إلى إنشاء مستند جديد وتهيئة DocumentBuilder، مما يساعد في بناء محتوى المستند. 

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: البدء في إنشاء جدول

بعد ذلك، استخدم DocumentBuilder لبدء إنشاء جدول وإدراج الخلية الأولى.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

## الخطوة 3: تعيين حدود الجدول

تعيين الحدود للجدول بأكمله. تضمن هذه الخطوة أن جميع الخلايا الموجودة في الجدول لها نمط حدود ثابت ما لم يتم تحديد خلاف ذلك.

```csharp
// تعيين الحدود للجدول بأكمله.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
```

## الخطوة 4: تطبيق تظليل الخلية

تطبيق التظليل على الخلايا لجعلها متميزة بصريا. في هذا المثال، سنقوم بتعيين لون خلفية الخلية الأولى إلى اللون الأحمر.


```csharp
// قم بتعيين تظليل الخلية لهذه الخلية.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
```

## الخطوة 5: أدخل خلية أخرى ذات تظليل مختلف

أدخل الخلية الثانية وقم بتطبيق لون تظليل مختلف. وهذا يجعل الجدول أكثر ألوانًا وأسهل في القراءة.

```csharp
builder.InsertCell();
// حدد تظليلًا مختلفًا للخلية الثانية.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
```

## الخطوة 6: مسح تنسيق الخلية

امسح تنسيق الخلية من العمليات السابقة للتأكد من أن الخلايا التالية لا ترث نفس الأنماط.


```csharp
// امسح تنسيق الخلية من العمليات السابقة.
builder.CellFormat.ClearFormatting();
```

## الخطوة 7: تخصيص الحدود لخلايا معينة

قم بتخصيص الحدود لخلايا معينة لجعلها مميزة. هنا، سنقوم بتعيين حدود أكبر للخلية الأولى من الصف الجديد.

```csharp
builder.InsertCell();
// قم بإنشاء حدود أكبر للخلية الأولى من هذا الصف. هذا سيكون مختلفا
// مقارنة بالحدود المحددة للجدول.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
```

## الخطوة 8: أدخل الخلية النهائية

قم بإدراج الخلية النهائية وتأكد من مسح تنسيقها، بحيث تستخدم الأنماط الافتراضية للجدول.

```csharp
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## الخطوة 9: احفظ المستند

وأخيرا، احفظ المستند في الدليل المحدد.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## خاتمة

وهناك لديك! لقد تعلمت للتو كيفية تنسيق الجداول والخلايا ذات الحدود المختلفة باستخدام Aspose.Words لـ .NET. من خلال تخصيص حدود الجدول وتظليل الخلايا، يمكنك تحسين المظهر المرئي لمستنداتك بشكل كبير. لذا، تفضل، وقم بتجربة أنماط مختلفة، واجعل مستنداتك مميزة!

## الأسئلة الشائعة

### هل يمكنني استخدام أنماط حدود مختلفة لكل خلية؟
 نعم، يمكنك تعيين أنماط حدود مختلفة لكل خلية باستخدام`CellFormat.Borders` ملكية.

### كيف يمكنني إزالة كافة الحدود من الجدول؟
 يمكنك إزالة جميع الحدود عن طريق ضبط نمط الحدود على`LineStyle.None`.

### هل من الممكن تعيين ألوان حدود مختلفة لكل خلية؟
 قطعاً! يمكنك تخصيص لون الحدود لكل خلية باستخدام`CellFormat.Borders.Color` ملكية.

### هل يمكنني استخدام الصور كخلفيات للخلايا؟
على الرغم من أن Aspose.Words لا يدعم الصور كخلفيات خلايا بشكل مباشر، إلا أنه يمكنك إدراج صورة في خلية وضبط حجمها لتغطية مساحة الخلية.

### كيف يمكنني دمج الخلايا في الجدول؟
 يمكنك دمج الخلايا باستخدام`CellFormat.HorizontalMerge`و`CellFormat.VerticalMerge` ملكيات.