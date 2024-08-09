---
title: أدخل حقل الدمج باستخدام DOM
linktitle: أدخل حقل الدمج باستخدام DOM
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج حقول الدمج وتكوينها في مستندات Word باستخدام Aspose.Words لـ .NET من خلال هذا البرنامج التعليمي الشامل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-merge-field-using-dom/
---
## مقدمة

إذا كنت تعمل على معالجة المستندات في .NET، فمن المحتمل أنك صادفت Aspose.Words. توفر هذه المكتبة القوية مجموعة واسعة من الميزات لمعالجة مستندات Word برمجياً. في هذا البرنامج التعليمي، سنركز على ميزة واحدة محددة: إدراج حقل دمج باستخدام نموذج كائن المستند (DOM) في Aspose.Words لـ .NET. سيرشدك هذا الدليل خلال كل خطوة، بدءًا من إعداد بيئتك وحتى إدراج حقل دمج وتحديثه في مستند Word.

## المتطلبات الأساسية

قبل الغوص في التعليمات البرمجية، دعنا نتأكد من أن لديك كل ما تحتاج إلى متابعته مع هذا البرنامج التعليمي.

1. المعرفة الأساسية بـ C#: يجب أن تكون مرتاحًا لبرمجة C#.
2. تثبيت Visual Studio: تأكد من تثبيت Visual Studio أو أي برنامج C# IDE آخر على جهازك.
3.  Aspose.Words for .NET: قم بتنزيل أحدث إصدار من Aspose.Words for .NET وتثبيته من[الإصدارات](https://releases.aspose.com/words/net/).
4.  ترخيص صالح: إذا لم يكن لديك ترخيص، يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) للتقييم.

## الخطوة 1: قم بإعداد مشروعك

أول الأشياء أولاً، لنقم بإعداد مشروع جديد في Visual Studio.

1. افتح فيجوال ستوديو.
2. إنشاء مشروع جديد: انتقل إلى ملف > جديد > مشروع. حدد تطبيق وحدة التحكم C#.
3. قم بتسمية مشروعك: قم بتسمية مشروعك باسم ذو معنى وانقر فوق إنشاء.

## الخطوة 2: تثبيت Aspose.Words

لاستخدام Aspose.Words، تحتاج إلى إضافته إلى مشروعك. يمكن القيام بذلك عبر NuGet Package Manager.

1. افتح NuGet Package Manager: انقر بزر الماوس الأيمن على مشروعك في Solution Explorer، ثم حدد Manage NuGet Packages.
2. البحث عن Aspose.Words: في NuGet Package Manager، ابحث عن "Aspose.Words".
3. تثبيت الحزمة: انقر فوق "تثبيت" لإضافة Aspose.Words إلى مشروعك.

## الخطوة 3: استيراد مساحات الأسماء

لبدء استخدام Aspose.Words، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروعك. وإليك كيف يمكنك القيام بذلك:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

## الخطوة 4: تهيئة المستند الخاص بك

الآن بعد أن تم إعداد كل شيء، فلنقم بإنشاء مستند Word جديد وتهيئة DocumentBuilder.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وDocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 5: نقل المؤشر إلى فقرة محددة

بعد ذلك، نحتاج إلى تحريك المؤشر إلى فقرة معينة في المستند حيث نريد إدراج حقل الدمج.

```csharp
Paragraph para = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);
builder.MoveTo(para);
```

## الخطوة 6: أدخل حقل الدمج

 يعد إدراج حقل دمج أمرًا بسيطًا. سوف نستخدم`InsertField` طريقة`DocumentBuilder` فصل.

```csharp
// أدخل حقل دمج الحقول.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

## الخطوة 7: تكوين حقل الدمج

بعد إدراج حقل الدمج، يمكنك تعيين خصائص مختلفة لتكوينه وفقًا لاحتياجاتك.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field.TextAfter = "Test3";
field.IsMapped = true;
field.IsVerticalFormatting = true;
```

## الخطوة 8: تحديث وحفظ المستند

وأخيرًا، قم بتحديث الحقل للتأكد من تطبيق كافة الإعدادات وحفظ المستند.

```csharp
// قم بتحديث الحقل.
field.Update();

// احفظ المستند.
doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

## خاتمة

باتباع هذه الخطوات، يمكنك بسهولة إدراج حقول الدمج وتكوينها في مستند Word باستخدام Aspose.Words for .NET. غطى هذا البرنامج التعليمي الخطوات الأساسية بدءًا من إعداد البيئة الخاصة بك وحتى حفظ المستند النهائي. باستخدام Aspose.Words، يمكنك أتمتة مهام معالجة المستندات المعقدة، مما يجعل تطبيقات .NET الخاصة بك أكثر قوة وكفاءة.

## الأسئلة الشائعة

###  ما هو حقل الدمج؟
حقل الدمج هو عنصر نائب في مستند يمكن استبداله ديناميكيًا ببيانات من مصدر بيانات، مثل قاعدة بيانات أو ملف CSV.

###  هل يمكنني استخدام Aspose.Words مجانًا؟
 يقدم Aspose.Words نسخة تجريبية مجانية يمكنك تنزيلها[هنا](https://releases.aspose.com/). للاستخدام على المدى الطويل، سوف تحتاج إلى شراء ترخيص.

###  كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Words؟
 يمكنك الحصول على ترخيص مؤقت من موقع Aspose[هنا](https://purchase.aspose.com/temporary-license/).

### ما هي إصدارات .NET التي يدعمها Aspose.Words؟
يدعم Aspose.Words إصدارات متعددة من .NET، بما في ذلك .NET Framework و.NET Core و.NET Standard.

###  أين يمكنني العثور على وثائق واجهة برمجة التطبيقات الخاصة بـ Aspose.Words؟
 وثائق API متاحة[هنا](https://reference.aspose.com/words/net/).