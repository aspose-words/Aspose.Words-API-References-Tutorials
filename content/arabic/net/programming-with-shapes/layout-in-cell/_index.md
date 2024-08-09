---
title: التخطيط في الخلية
linktitle: التخطيط في الخلية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين التخطيط في الخلية باستخدام Aspose.Words for .NET باستخدام هذا الدليل الشامل. مثالي للمطورين الذين يتطلعون إلى تخصيص مستندات Word.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/layout-in-cell/
---
## مقدمة

إذا كنت تريد تحسين تخطيط خلايا الجدول في مستندات Word برمجيًا، فأنت في المكان الصحيح. اليوم، سوف نتعمق في كيفية تعيين التخطيط في الخلية باستخدام Aspose.Words for .NET. سنتناول مثالًا عمليًا، وسنقسمه خطوة بخطوة حتى تتمكن من المتابعة بسهولة.

## المتطلبات الأساسية

قبل أن ننتقل إلى الكود، دعونا نتأكد من أن لديك كل ما تحتاجه:

1.  Aspose.Words for .NET: تأكد من تثبيت مكتبة Aspose.Words for .NET. إذا لم تقم بذلك، يمكنك[قم بتنزيله هنا](https://releases.aspose.com/words/net/).
2. بيئة التطوير: ستحتاج إلى إعداد بيئة تطوير باستخدام .NET. يعد Visual Studio خيارًا رائعًا إذا كنت تبحث عن توصيات.
3. المعرفة الأساسية بـ C#: بينما سأشرح كل خطوة، فإن الفهم الأساسي لـ C# سيساعدك على المتابعة بسهولة أكبر.
4.  دليل المستندات: قم بإعداد مسار الدليل حيث ستحفظ مستنداتك. سوف نشير إلى هذا باسم`YOUR DOCUMENT DIRECTORY`.

## استيراد مساحات الأسماء

للبدء، تأكد من استيراد مساحات الأسماء الضرورية في مشروعك:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

دعونا نقسم العملية إلى خطوات يمكن التحكم فيها.

## الخطوة 1: إنشاء مستند جديد

 أولاً، سنقوم بإنشاء مستند Word جديد وتهيئة ملف`DocumentBuilder` كائن لمساعدتنا في بناء المحتوى الخاص بنا.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: بدء جدول وتعيين تنسيق الصف

سنبدأ في إنشاء جدول وتحديد قاعدة الارتفاع والارتفاع للصفوف.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## الخطوة 3: إدراج الخلايا وملء المحتوى

بعد ذلك، نقوم بحلقة لإدراج الخلايا في الجدول. لكل 7 خلايا، سننهي الصف لإنشاء خلية جديدة.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## الخطوة 4: إضافة شكل علامة مائية

 الآن، دعونا نضيف علامة مائية إلى وثيقتنا. سنقوم بإنشاء`Shape` الكائن وتعيين خصائصه.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // عرض الشكل خارج خلية الجدول إذا كان سيتم وضعه في خلية.
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## الخطوة 5: تخصيص مظهر العلامة المائية

سنقوم أيضًا بتخصيص مظهر العلامة المائية من خلال تعيين خصائص اللون والنص الخاصة بها.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## الخطوة 6: أدخل العلامة المائية في المستند

سنبحث عن آخر تشغيل في المستند ونقوم بإدراج العلامة المائية في هذا الموضع.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## الخطوة 7: تحسين المستند لبرنامج Word 2010

لضمان التوافق، سنقوم بتحسين المستند لبرنامج Word 2010.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## الخطوة 8: احفظ المستند

وأخيرًا، سنقوم بحفظ المستند في الدليل المحدد.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## خاتمة

وهنا لديك! لقد نجحت في إنشاء مستند Word بتخطيط جدول مخصص وإضافة علامة مائية باستخدام Aspose.Words for .NET. يهدف هذا البرنامج التعليمي إلى توفير دليل واضح خطوة بخطوة لمساعدتك على فهم كل جزء من العملية. باستخدام هذه المهارات، يمكنك الآن إنشاء مستندات Word أكثر تعقيدًا وتخصيصًا برمجيًا.

## الأسئلة الشائعة

### هل يمكنني استخدام خط مختلف لنص العلامة المائية؟
 نعم، يمكنك تغيير الخط عن طريق ضبط`watermark.TextPath.FontFamily` الخاصية إلى الخط الذي تريده.

### كيف يمكنني ضبط موضع العلامة المائية؟
 يمكنك تعديل`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` ، و`VerticalAlignment` خصائص لضبط موضع العلامة المائية.

### هل من الممكن استخدام صورة بدلاً من النص للعلامة المائية؟
 قطعاً! يمكنك إنشاء`Shape` مع النوع`ShapeType.Image` وتعيين صورته باستخدام`ImageData.SetImage` طريقة.

### هل يمكنني إنشاء جداول بارتفاعات صفوف مختلفة؟
نعم، يمكنك ضبط ارتفاعات مختلفة لكل صف عن طريق تغيير`RowFormat.Height` الخاصية قبل إدراج الخلايا في هذا الصف.

### كيف يمكنني إزالة العلامة المائية من المستند؟
 يمكنك إزالة العلامة المائية عن طريق تحديد موقعها في مجموعة أشكال المستند واستدعاء`Remove` طريقة.