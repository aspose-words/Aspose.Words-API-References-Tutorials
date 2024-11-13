---
title: إدراج حقل الدمج باستخدام DOM
linktitle: إدراج حقل الدمج باستخدام DOM
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج حقول الدمج وتكوينها في مستندات Word باستخدام Aspose.Words لـ .NET من خلال هذا البرنامج التعليمي الشامل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-merge-field-using-dom/
---
## مقدمة

إذا كنت تعمل على معالجة المستندات في .NET، فمن المحتمل أنك صادفت Aspose.Words. تقدم هذه المكتبة القوية مجموعة واسعة من الميزات لمعالجة مستندات Word برمجيًا. في هذا البرنامج التعليمي، سنركز على ميزة واحدة محددة: إدراج حقل دمج باستخدام نموذج كائن المستند (DOM) في Aspose.Words لـ .NET. سيرشدك هذا الدليل خلال كل خطوة، من إعداد البيئة الخاصة بك إلى إدراج حقل دمج وتحديثه في مستند Word.

## المتطلبات الأساسية

قبل الغوص في الكود، دعنا نتأكد من أن لديك كل ما تحتاجه لمتابعة هذا البرنامج التعليمي.

1. المعرفة الأساسية بلغة C#: يجب أن تكون مرتاحًا في برمجة C#.
2. تم تثبيت Visual Studio: تأكد من تثبيت Visual Studio أو أي C# IDE آخر على جهازك.
3.  Aspose.Words for .NET: قم بتنزيل أحدث إصدار من Aspose.Words for .NET وتثبيته من[الإصدارات](https://releases.aspose.com/words/net/).
4.  رخصة صالحة: إذا لم يكن لديك ترخيص، يمكنك الحصول على[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) للتقييم.

## الخطوة 1: إعداد مشروعك

أولاً وقبل كل شيء، دعونا نقوم بإعداد مشروع جديد في Visual Studio.

1. افتح Visual Studio.
2. إنشاء مشروع جديد: انتقل إلى ملف > جديد > مشروع. حدد تطبيق وحدة التحكم C#.
3. قم بتسمية مشروعك: قم بتسمية مشروعك باسم ذو معنى وانقر فوق "إنشاء".

## الخطوة 2: تثبيت Aspose.Words

لاستخدام Aspose.Words، يجب عليك إضافته إلى مشروعك. يمكن القيام بذلك عبر NuGet Package Manager.

1. افتح مدير حزم NuGet: انقر بزر الماوس الأيمن فوق مشروعك في مستكشف الحلول، ثم حدد إدارة حزم NuGet.
2. ابحث عن Aspose.Words: في مدير الحزم NuGet، ابحث عن "Aspose.Words".
3. تثبيت الحزمة: انقر فوق "تثبيت" لإضافة Aspose.Words إلى مشروعك.

## الخطوة 3: استيراد المساحات الاسمية

للبدء في استخدام Aspose.Words، تحتاج إلى استيراد المساحات الأساسية اللازمة إلى مشروعك. إليك كيفية القيام بذلك:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

## الخطوة 4: تهيئة المستند الخاص بك

الآن بعد إعداد كل شيء، دعنا نقوم بإنشاء مستند Word جديد ونقوم بتشغيل DocumentBuilder.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء المستند و DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 5: نقل المؤشر إلى فقرة محددة

بعد ذلك، نحتاج إلى نقل المؤشر إلى فقرة محددة في المستند حيث نريد إدراج حقل الدمج.

```csharp
Paragraph para = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);
builder.MoveTo(para);
```

## الخطوة 6: إدراج حقل الدمج

 إن إدراج حقل الدمج أمر بسيط. سوف نستخدم`InsertField` طريقة`DocumentBuilder` فصل.

```csharp
// إدراج حقل دمج الحقل.
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

## الخطوة 8: تحديث المستند وحفظه

وأخيرًا، قم بتحديث الحقل للتأكد من تطبيق كافة الإعدادات ثم احفظ المستند.

```csharp
// تحديث المجال.
field.Update();

// احفظ المستند.
doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

## خاتمة

باتباع هذه الخطوات، يمكنك بسهولة إدراج وتكوين حقول الدمج في مستند Word باستخدام Aspose.Words for .NET. تناول هذا البرنامج التعليمي الخطوات الأساسية من إعداد البيئة الخاصة بك إلى حفظ المستند النهائي. باستخدام Aspose.Words، يمكنك أتمتة مهام معالجة المستندات المعقدة، مما يجعل تطبيقات .NET الخاصة بك أكثر قوة وكفاءة.

## الأسئلة الشائعة

###  ما هو حقل الدمج؟
حقل الدمج هو عنصر نائب في مستند يمكن استبداله بشكل ديناميكي ببيانات من مصدر بيانات، مثل قاعدة بيانات أو ملف CSV.

###  هل يمكنني استخدام Aspose.Words مجانًا؟
 يقدم Aspose.Words نسخة تجريبية مجانية يمكنك تنزيلها[هنا](https://releases.aspose.com/)للاستخدام طويل الأمد، ستحتاج إلى شراء ترخيص.

###  كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Words؟
 يمكنك الحصول على ترخيص مؤقت من موقع Aspose[هنا](https://purchase.aspose.com/temporary-license/).

### ما هي إصدارات .NET التي يدعمها Aspose.Words؟
يدعم Aspose.Words إصدارات متعددة من .NET، بما في ذلك .NET Framework، و.NET Core، و.NET Standard.

###  أين يمكنني العثور على وثائق API لـ Aspose.Words؟
 وثائق واجهة برمجة التطبيقات متاحة[هنا](https://reference.aspose.com/words/net/).