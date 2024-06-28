---
title: تنسيق القاعدة الأفقية في مستند Word
linktitle: تنسيق القاعدة الأفقية في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج قواعد أفقية قابلة للتخصيص في مستندات Word باستخدام Aspose.Words لـ .NET. تعزيز أتمتة المستندات الخاصة بك.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/horizontal-rule-format/
---
## مقدمة

في مجال تطوير .NET، يمكن أن تكون معالجة مستندات Word وتنسيقها برمجيًا مهمة شاقة. لحسن الحظ، يوفر Aspose.Words for .NET حلاً قويًا، يمكّن المطورين من أتمتة إنشاء المستندات وتحريرها وإدارتها بسهولة. تتعمق هذه المقالة في إحدى الميزات الأساسية: إدراج القواعد الأفقية في مستندات Word. سواء كنت مطورًا متمرسًا أو بدأت للتو في استخدام Aspose.Words، فإن إتقان هذه الإمكانية سيعزز عملية إنشاء المستندات لديك.

## المتطلبات الأساسية

قبل الغوص في تنفيذ القواعد الأفقية باستخدام Aspose.Words لـ .NET، تأكد من أن لديك المتطلبات الأساسية التالية:

- Visual Studio: قم بتثبيت Visual Studio IDE لتطوير .NET.
- Aspose.Words لـ .NET: قم بتنزيل Aspose.Words لـ .NET وتثبيته من[هنا](https://releases.aspose.com/words/net/).
- المعرفة الأساسية بـ C#: الإلمام بأساسيات لغة البرمجة C#.
-  فئة DocumentBuilder: فهم`DocumentBuilder` فئة في Aspose.Words لمعالجة المستندات.

## استيراد مساحات الأسماء

للبدء، قم باستيراد مساحات الأسماء الضرورية في مشروع C# الخاص بك:

```csharp
using Aspose.Words;
using System.Drawing;
```

توفر مساحات الأسماء هذه إمكانية الوصول إلى فئات Aspose.Words لمعالجة المستندات وفئات .NET القياسية لمعالجة الألوان.

دعنا نقسم عملية إضافة قاعدة أفقية في مستند Word باستخدام Aspose.Words لـ .NET إلى خطوات شاملة:

## الخطوة 1: تهيئة DocumentBuilder وتعيين الدليل

 أولاً، قم بتهيئة أ`DocumentBuilder` الكائن وقم بتعيين مسار الدليل حيث سيتم حفظ المستند.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة 2: أدخل القاعدة الأفقية

 استخدم ال`InsertHorizontalRule()` طريقة`DocumentBuilder` فئة لإضافة قاعدة أفقية.

```csharp
Shape shape = builder.InsertHorizontalRule();
```

## الخطوة 3: تخصيص تنسيق القاعدة الأفقية

 الوصول إلى`HorizontalRuleFormat` خاصية الشكل المدرج لتخصيص مظهر القاعدة الأفقية.

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

- المحاذاة: تحديد محاذاة القاعدة الأفقية (`HorizontalRuleAlignment.Center` في هذا المثال).
- WidthPercent: يضبط عرض القاعدة الأفقية كنسبة مئوية من عرض الصفحة (70% في هذا المثال).
- الارتفاع: يحدد ارتفاع القاعدة الأفقية بالنقاط (3 نقاط في هذا المثال).
- اللون: يضبط لون القاعدة الأفقية (`Color.Blue` في هذا المثال).
- NoShade: يحدد ما إذا كان يجب أن يكون للقاعدة الأفقية ظل (`true` في هذا المثال).

## الخطوة 4: حفظ المستند

 وأخيرًا، احفظ المستند المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
builder.Document.Save(dataDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

## خاتمة

يؤدي إتقان إدراج القواعد الأفقية في مستندات Word باستخدام Aspose.Words for .NET إلى تحسين قدرات أتمتة المستندات لديك. من خلال الاستفادة من مرونة وقوة Aspose.Words، يمكن للمطورين تبسيط عمليات إنشاء المستندات وتنسيقها بكفاءة.

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟
تعد Aspose.Words for .NET مكتبة قوية للعمل مع مستندات Word برمجيًا في تطبيقات .NET.

### كيف يمكنني تنزيل Aspose.Words لـ .NET؟
 يمكنك تنزيل Aspose.Words لـ .NET من[هنا](https://releases.aspose.com/words/net/).

### هل يمكنني تخصيص مظهر القواعد الأفقية في Aspose.Words؟
نعم، يمكنك تخصيص جوانب مختلفة مثل المحاذاة والعرض والارتفاع واللون وتظليل القواعد الأفقية باستخدام Aspose.Words.

### هل Aspose.Words مناسب لمعالجة المستندات على مستوى المؤسسة؟
نعم، يتم استخدام Aspose.Words على نطاق واسع في بيئات المؤسسات نظرًا لإمكانياته القوية في معالجة المستندات.

### أين يمكنني الحصول على الدعم لـ Aspose.Words لـ .NET؟
 للحصول على الدعم والمشاركة المجتمعية، قم بزيارة[منتدى Aspose.Words](https://forum.aspose.com/c/words/8).
