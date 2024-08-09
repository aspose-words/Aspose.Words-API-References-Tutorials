---
title: إنشاء سطر توقيع جديد وتعيين معرف الموفر
linktitle: إنشاء سطر توقيع جديد وتعيين معرف الموفر
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء سطر توقيع جديد وتعيين معرف الموفر في مستندات Word باستخدام Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## مقدمة

مرحبًا يا عشاق التكنولوجيا! هل تساءلت يومًا عن كيفية إضافة سطر توقيع في مستندات Word الخاصة بك برمجيًا؟ حسنًا، سنتعمق اليوم في هذا الأمر باستخدام Aspose.Words for .NET. سيرشدك هذا الدليل خلال كل خطوة، مما يجعل من السهل إنشاء سطر توقيع جديد وتعيين معرف الموفر في مستندات Word الخاصة بك. سواء كنت تقوم بأتمتة معالجة المستندات أو تتطلع فقط إلى تبسيط سير عملك، فإن هذا البرنامج التعليمي يوفر لك كل ما تحتاجه.

## المتطلبات الأساسية

قبل أن نتسخ أيدينا، دعونا نتأكد من أن لدينا كل ما نحتاجه:

1.  Aspose.Words for .NET: إذا لم تكن قد قمت بذلك بالفعل، فقم بتنزيله[هنا](https://releases.aspose.com/words/net/).
2. بيئة التطوير: Visual Studio أو أي بيئة تطوير أخرى لـ C#.
3. .NET Framework: تأكد من تثبيت .NET Framework.
4. شهادة PFX: لتوقيع المستندات، ستحتاج إلى شهادة PFX. يمكنك الحصول على واحدة من مرجع مصدق موثوق به.

## استيراد مساحات الأسماء

أول الأشياء أولاً، لنستورد مساحات الأسماء الضرورية في مشروع C# الخاص بك:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

حسنًا ، دعنا ننتقل إلى التفاصيل الجوهرية. فيما يلي تفاصيل تفصيلية لكل خطوة لإنشاء سطر توقيع جديد وتعيين معرف الموفر.

## الخطوة 1: إنشاء مستند جديد

للبدء، نحن بحاجة إلى إنشاء مستند Word جديد. ستكون هذه هي اللوحة القماشية لخط توقيعنا.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 في هذا المقتطف، نقوم بتهيئة ملف جديد`Document` و أ`DocumentBuilder` . ال`DocumentBuilder` يساعدنا على إضافة عناصر إلى وثيقتنا.

## الخطوة 2: تحديد خيارات خط التوقيع

بعد ذلك، نحدد الخيارات لخط التوقيع الخاص بنا. يتضمن ذلك اسم المُوقع والمسمى الوظيفي والبريد الإلكتروني والتفاصيل الأخرى.

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

تعمل هذه الخيارات على تخصيص سطر التوقيع، مما يجعله واضحًا واحترافيًا.

## الخطوة 3: أدخل سطر التوقيع

بعد ضبط الخيارات، يمكننا الآن إدراج سطر التوقيع في المستند.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 هنا،`InsertSignatureLine` تضيف الطريقة سطر التوقيع، ونقوم بتعيين معرف موفر فريد له.

## الخطوة 4: احفظ المستند

بعد إدراج سطر التوقيع، دعونا نحفظ المستند.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

يؤدي هذا إلى حفظ المستند الخاص بك بسطر التوقيع المضاف حديثًا.

## الخطوة 5: إعداد خيارات التوقيع

الآن، نحن بحاجة إلى إعداد الخيارات لتوقيع الوثيقة. يتضمن ذلك معرف سطر التوقيع ومعرف الموفر والتعليقات ووقت التوقيع.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

تضمن هذه الخيارات توقيع المستند بالتفاصيل الصحيحة.

## الخطوة 6: إنشاء حامل الشهادة

لتوقيع المستند، سنستخدم شهادة PFX. لنقم بإنشاء حامل شهادة لذلك.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 تأكد من استبدال`"morzal.pfx"` مع ملف الشهادة الفعلي الخاص بك و`"aw"` مع كلمة مرور الشهادة الخاصة بك.

## الخطوة 7: قم بالتوقيع على الوثيقة

وأخيرًا، نقوم بتوقيع المستند باستخدام أداة التوقيع الرقمي.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

يؤدي هذا إلى توقيع المستند وحفظه كملف جديد.

## خاتمة

وهنا لديك! لقد نجحت في إنشاء سطر توقيع جديد وتعيين معرف الموفر في مستند Word باستخدام Aspose.Words for .NET. تعمل هذه المكتبة القوية على تسهيل إدارة مهام معالجة المستندات وأتمتتها بشكل لا يصدق. جربه وشاهد كيف يمكنه تبسيط سير عملك.

## الأسئلة الشائعة

### هل يمكنني تخصيص مظهر سطر التوقيع؟
قطعاً! يمكنك تعديل الخيارات المختلفة في`SignatureLineOptions` لتناسب احتياجاتك.

### ماذا لو لم يكن لدي شهادة PFX؟
ستحتاج إلى الحصول على واحدة من مرجع مصدق موثوق به. إنه ضروري لتوقيع المستندات رقميًا.

### هل يمكنني إضافة أسطر توقيع متعددة إلى مستند؟
نعم، يمكنك إضافة أي عدد تريده من أسطر التوقيع عن طريق تكرار عملية الإدراج مع خيارات مختلفة.

### هل Aspose.Words for .NET متوافق مع .NET Core؟
نعم، يدعم Aspose.Words for .NET .NET Core، مما يجعله متعدد الاستخدامات لبيئات التطوير المختلفة.

### ما مدى أمان التوقيعات الرقمية؟
التوقيعات الرقمية التي تم إنشاؤها باستخدام Aspose.Words آمنة للغاية، بشرط استخدام شهادة صالحة وموثوقة.