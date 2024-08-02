---
title: إدراج الشكل
linktitle: إدراج الشكل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج الأشكال ومعالجتها في مستندات Word باستخدام Aspose.Words لـ .NET من خلال دليلنا خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/insert-shape/
---
## مقدمة

عندما يتعلق الأمر بإنشاء مستندات Word جذابة بصريًا وجيدة التنظيم، يمكن أن تلعب الأشكال دورًا حيويًا. سواء كنت تضيف أسهمًا أو مربعات أو حتى أشكالًا مخصصة معقدة، فإن القدرة على التعامل مع هذه العناصر برمجيًا توفر مرونة لا مثيل لها. في هذا البرنامج التعليمي، سوف نستكشف كيفية إدراج الأشكال ومعالجتها في مستندات Word باستخدام Aspose.Words for .NET.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

1.  Aspose.Words for .NET: قم بتنزيل أحدث إصدار من .NET وتثبيته[صفحة الإصدارات Aspose](https://releases.aspose.com/words/net/).
2. بيئة التطوير: بيئة تطوير .NET مناسبة مثل Visual Studio.
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# والمفاهيم الأساسية.

## استيراد مساحات الأسماء

للبدء، ستحتاج إلى استيراد مساحات الأسماء الضرورية في مشروع C# الخاص بك:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## الخطوة 1: قم بإعداد مشروعك

قبل أن تتمكن من البدء في إدراج الأشكال، تحتاج إلى إعداد مشروعك وإضافة مكتبة Aspose.Words for .NET.

1. إنشاء مشروع جديد: افتح Visual Studio وقم بإنشاء مشروع تطبيق وحدة تحكم C# جديد.
2. إضافة Aspose.Words لـ .NET: قم بتثبيت مكتبة Aspose.Words لـ .NET عبر NuGet Package Manager.

```bash
Install-Package Aspose.Words
```

## الخطوة 2: تهيئة المستند

أولاً، ستحتاج إلى تهيئة مستند جديد وأداة إنشاء المستندات، مما سيساعد في إنشاء المستند.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

// تهيئة مستند جديد
Document doc = new Document();

// قم بتهيئة DocumentBuilder للمساعدة في إنشاء المستند
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: أدخل الشكل

الآن، دعونا نقوم بإدراج شكل في المستند. سنبدأ بإضافة مربع نص بسيط.

```csharp
// قم بإدراج شكل مربع نص في المستند
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100, RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// تدوير الشكل
shape.Rotation = 30.0;
```

في هذا المثال، قمنا بإدراج مربع نص في الموضع (100، 100) بعرض وارتفاع 50 وحدة لكل منهما. نقوم أيضًا بتدوير الشكل بمقدار 30 درجة.

## الخطوة 4: إضافة شكل آخر

دعونا نضيف شكلاً آخر إلى المستند، هذه المرة دون تحديد الموضع.

```csharp
// إضافة شكل مربع نص آخر
Shape secondShape = builder.InsertShape(ShapeType.TextBox, 50, 50);

// تدوير الشكل
secondShape.Rotation = 30.0;
```

يقوم مقتطف الكود هذا بإدراج مربع نص آخر بنفس الأبعاد والتدوير مثل المربع الأول ولكن دون تحديد موضعه.

## الخطوة 5: احفظ المستند

 بعد إضافة الأشكال، الخطوة الأخيرة هي حفظ المستند. سوف نستخدم`OoxmlSaveOptions` لتحديد تنسيق الحفظ.

```csharp
// تحديد خيارات الحفظ مع الامتثال
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};

// احفظ المستند
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## خاتمة

وهناك لديك! لقد نجحت في إدراج الأشكال ومعالجتها في مستند Word باستخدام Aspose.Words لـ .NET. غطى هذا البرنامج التعليمي الأساسيات، لكن Aspose.Words يقدم العديد من الميزات المتقدمة للتعامل مع الأشكال، مثل الأنماط المخصصة والموصلات وأشكال المجموعات.

 لمزيد من المعلومات التفصيلية، قم بزيارة[Aspose.Words لوثائق .NET](https://reference.aspose.com/words/net/).

## الأسئلة الشائعة

### كيف يمكنني إدراج أنواع مختلفة من الأشكال؟
يمكنك تغيير`ShapeType` في ال`InsertShape` طريقة لإدراج أنواع مختلفة من الأشكال مثل الدوائر والمستطيلات والأسهم.

### هل يمكنني إضافة نص داخل الأشكال؟
 نعم يمكنك استخدام`builder.Write` طريقة إضافة نص داخل الأشكال بعد إدراجها.

### هل من الممكن تصميم الأشكال؟
 نعم، يمكنك تصميم الأشكال عن طريق تعيين خصائص مثل`FillColor`, `StrokeColor` ، و`StrokeWeight`.

### كيف يمكنني تحديد موضع الأشكال بالنسبة للعناصر الأخرى؟
 استخدم ال`RelativeHorizontalPosition`و`RelativeVerticalPosition` خصائص لتحديد موضع الأشكال بالنسبة للعناصر الأخرى في المستند.

### هل يمكنني تجميع أشكال متعددة معًا؟
 نعم، يسمح لك Aspose.Words for .NET بتجميع الأشكال باستخدام`GroupShape` فصل.