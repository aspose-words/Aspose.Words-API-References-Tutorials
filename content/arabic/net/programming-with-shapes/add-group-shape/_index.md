---
title: إضافة شكل المجموعة
linktitle: إضافة شكل المجموعة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة أشكال جماعية إلى مستندات Word باستخدام Aspose.Words لـ .NET من خلال هذا البرنامج التعليمي الشامل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/add-group-shape/
---
## مقدمة

قد يكون إنشاء مستندات معقدة تحتوي على عناصر مرئية غنية في بعض الأحيان مهمة شاقة، خاصة عند التعامل مع أشكال المجموعات. لكن لا تخف! يعمل Aspose.Words for .NET على تبسيط هذه العملية، مما يجعلها سهلة مثل الفطيرة. في هذا البرنامج التعليمي، سنرشدك خلال خطوات إضافة أشكال جماعية إلى مستندات Word الخاصة بك. على استعداد للغوص في؟ دعونا نبدأ!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1.  Aspose.Words for .NET: يمكنك تنزيله من[صفحة الإصدارات Aspose](https://releases.aspose.com/words/net/).
2. بيئة التطوير: Visual Studio أو أي بيئة تطوير متكاملة أخرى متوافقة مع .NET.
3. الفهم الأساسي لـ C#: الإلمام ببرمجة C# يعد ميزة إضافية.

## استيراد مساحات الأسماء

للبدء، نحتاج إلى استيراد مساحات الأسماء الضرورية في مشروعنا. توفر مساحات الأسماء هذه إمكانية الوصول إلى الفئات والأساليب المطلوبة لمعالجة مستندات Word باستخدام Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## الخطوة 1: تهيئة المستند

أول الأشياء أولاً، دعونا نقوم بتهيئة مستند Word جديد. فكر في هذا على أنه إنشاء لوحة قماشية فارغة حيث سنضيف أشكال مجموعتنا.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.EnsureMinimum();
```

 هنا،`EnsureMinimum()` يضيف الحد الأدنى من العقد المطلوبة للمستند.

## الخطوة 2: إنشاء كائن GroupShape

 بعد ذلك، نحن بحاجة إلى إنشاء`GroupShape`هدف. سيكون هذا الكائن بمثابة حاوية للأشكال الأخرى، مما يسمح لنا بتجميعها معًا.

```csharp
GroupShape groupShape = new GroupShape(doc);
```

## الخطوة 3: إضافة الأشكال إلى GroupShape

 الآن، دعونا نضيف الأشكال الفردية لدينا`GroupShape` حاوية. سنبدأ بشكل حدود مميز ثم نضيف شكل زر الإجراء.

### إضافة شكل حدود مميز

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1)
{
    Width = 100,
    Height = 100
};
groupShape.AppendChild(accentBorderShape);
```

 يقوم مقتطف الكود هذا بإنشاء شكل حد مميز بعرض وارتفاع 100 وحدة ويضيفه إلى`GroupShape`.

### إضافة شكل زر العمل

```csharp
Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

 هنا، نقوم بإنشاء شكل زر إجراء، ووضعه، وإضافته إلى ملفنا`GroupShape`.

## الخطوة 4: تحديد أبعاد GroupShape

 للتأكد من أن أشكالنا تتلاءم بشكل جيد مع المجموعة، نحتاج إلى تعيين أبعاد المجموعة`GroupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

 وهذا يحدد العرض والارتفاع`GroupShape` 200 وحدة ويحدد حجم الإحداثيات وفقًا لذلك.

## الخطوة 5: أدخل شكل المجموعة في المستند

 الآن، دعونا ندخل لدينا`GroupShape` في المستند باستخدام`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

`DocumentBuilder` يوفر طريقة سهلة لإضافة العقد، بما في ذلك الأشكال، إلى المستند.

## الخطوة 6: احفظ المستند

وأخيرًا، احفظ المستند في الدليل المحدد.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

وهنا لديك! المستند الذي يحتوي على أشكال المجموعة جاهز.

## خاتمة

لا يجب أن تكون إضافة أشكال جماعية إلى مستندات Word الخاصة بك عملية معقدة. باستخدام Aspose.Words for .NET، يمكنك إنشاء الأشكال ومعالجتها بسهولة، مما يجعل مستنداتك أكثر جاذبية من الناحية المرئية وعملية. اتبع الخطوات الموضحة في هذا البرنامج التعليمي، وسوف تصبح محترفًا في وقت قصير!

## الأسئلة الشائعة

### هل يمكنني إضافة أكثر من شكلين إلى GroupShape؟
 نعم، يمكنك إضافة أي عدد تريده من الأشكال إلى ملف`GroupShape` . مجرد استخدام`AppendChild` طريقة لكل شكل

### هل من الممكن تصميم الأشكال داخل GroupShape؟
 قطعاً! يمكن تصميم كل شكل على حدة باستخدام الخصائص المتوفرة في`Shape` فصل.

### كيف يمكنني وضع GroupShape داخل المستند؟
 يمكنك وضع`GroupShape` من خلال تحديدها`Left`و`Top` ملكيات.

### هل يمكنني إضافة نص إلى الأشكال داخل GroupShape؟
 نعم، يمكنك إضافة نص إلى الأشكال باستخدام`AppendChild` طريقة اضافة أ`Paragraph` تحتوي على`Run` العقد مع النص.

### هل من الممكن تجميع الأشكال ديناميكيًا بناءً على إدخال المستخدم؟
نعم، يمكنك إنشاء الأشكال وتجميعها ديناميكيًا بناءً على إدخال المستخدم عن طريق ضبط الخصائص والأساليب وفقًا لذلك.