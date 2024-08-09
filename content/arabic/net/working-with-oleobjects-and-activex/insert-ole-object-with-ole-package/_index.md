---
title: إدراج كائن Ole في Word باستخدام حزمة Ole
linktitle: إدراج كائن Ole في Word باستخدام حزمة Ole
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج كائنات OLE في مستندات Word باستخدام Aspose.Words لـ .NET. اتبع دليلنا المفصل خطوة بخطوة لتضمين الملفات بسلاسة.
type: docs
weight: 10
url: /ar/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---
## مقدمة

إذا كنت تريد تضمين ملف في مستند Word، فأنت في المكان الصحيح. سواء كان ملف ZIP أو ورقة Excel أو أي نوع آخر من الملفات، فإن تضمينه مباشرة في مستند Word الخاص بك يمكن أن يكون مفيدًا بشكل لا يصدق. فكر في الأمر كما لو كان لديك حجرة سرية في وثيقتك حيث يمكنك تخزين جميع أنواع الكنوز. واليوم، سنتعرف على كيفية القيام بذلك باستخدام Aspose.Words for .NET. هل أنت مستعد لتصبح معالج Word؟ دعونا الغوص في!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. Aspose.Words for .NET: إذا لم تكن قد قمت بذلك بالفعل، فقم بتنزيله من[هنا](https://releases.aspose.com/words/net/).
2. بيئة التطوير: Visual Studio أو أي بيئة تطوير .NET أخرى.
3. الفهم الأساسي لـ C#: لست بحاجة إلى أن تكون خبيرًا، ولكن معرفة طريقك نحو C# سيساعدك.
4. دليل المستندات: مجلد يمكنك من خلاله تخزين المستندات واسترجاعها.

## استيراد مساحات الأسماء

أول الأشياء أولاً، دعونا نرتب مساحات الأسماء لدينا. تحتاج إلى تضمين مساحات الأسماء التالية في مشروعك:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

دعونا نقسم ذلك إلى خطوات صغيرة، بحيث يكون من السهل متابعتها.

## الخطوة 1: قم بإعداد المستند الخاص بك

تخيل أنك فنان بلوحة قماشية فارغة. أولاً، نحتاج إلى قماشنا الفارغ، وهو مستند Word الخاص بنا. إليك كيفية إعداده:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

يقوم هذا الرمز بتهيئة مستند Word جديد وإعداد DocumentBuilder، والذي سنستخدمه لإدراج المحتوى في مستندنا.

## الخطوة 2: اقرأ كائن Ole الخاص بك

بعد ذلك، دعنا نقرأ الملف الذي تريد تضمينه. فكر في هذا على أنه التقاط الكنز الذي تريد إخفاءه في مقصورتك السرية:

```csharp
byte[] bs = File.ReadAllBytes(dataDir + "Zip file.zip");
```

يقرأ هذا السطر كافة وحدات البايت من ملف ZIP الخاص بك ويخزنها في مصفوفة بايت.

## الخطوة 3: أدخل كائن Ole

الآن يأتي الجزء السحري. سنقوم بتضمين الملف في مستند Word الخاص بنا:

```csharp
using (Stream stream = new MemoryStream(bs))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);
    OlePackage olePackage = shape.OleFormat.OlePackage;
    olePackage.FileName = "filename.zip";
    olePackage.DisplayName = "displayname.zip";
}
```

 هنا، نقوم بإنشاء دفق ذاكرة من مصفوفة البايت ونستخدم`InsertOleObject` طريقة تضمينه في المستند. نقوم أيضًا بتعيين اسم الملف واسم العرض للكائن المضمن.

## الخطوة 4: احفظ المستند الخاص بك

وأخيرا، دعونا نحفظ تحفتنا:

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

يؤدي هذا إلى حفظ المستند مع ملفك المضمن في الدليل المحدد.

## خاتمة

وهنا لديك! لقد قمت بنجاح بتضمين كائن OLE في مستند Word باستخدام Aspose.Words لـ .NET. إنه مثل إضافة جوهرة مخفية داخل مستندك والتي يمكن كشفها في أي وقت. يمكن أن تكون هذه التقنية مفيدة بشكل لا يصدق لمجموعة متنوعة من التطبيقات، بدءًا من الوثائق الفنية وحتى التقارير الديناميكية. 

## الأسئلة الشائعة

### هل يمكنني تضمين أنواع ملفات أخرى باستخدام هذه الطريقة؟
نعم، يمكنك تضمين أنواع مختلفة من الملفات مثل أوراق Excel وملفات PDF والصور.

### هل أحتاج إلى ترخيص لـ Aspose.Words؟
 نعم، أنت بحاجة إلى ترخيص ساري المفعول. يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) للتقييم.

### كيف يمكنني تخصيص اسم العرض لكائن OLE؟
 يمكنك ضبط`DisplayName` ملكية`OlePackage` لتخصيصه.

### هل Aspose.Words متوافق مع .NET Core؟
نعم، يدعم Aspose.Words كلاً من .NET Framework و.NET Core.

### هل يمكنني تحرير كائن OLE المضمن في مستند Word؟
لا، لا يمكنك تحرير كائن OLE مباشرة داخل Word. تحتاج إلى فتحه في تطبيقه الأصلي.