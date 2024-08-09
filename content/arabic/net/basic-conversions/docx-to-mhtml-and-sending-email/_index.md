---
title: تحويل Docx إلى Mhtml وإرسال البريد الإلكتروني
linktitle: تحويل Docx إلى Mhtml وإرسال البريد الإلكتروني
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحويل DOCX إلى MHTML وإرسال رسائل البريد الإلكتروني باستخدام Aspose.Words لـ .NET في هذا الدليل التفصيلي خطوة بخطوة. عزز إنتاجيتك من خلال التشغيل الآلي السهل.
type: docs
weight: 10
url: /ar/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## مقدمة

في العصر الرقمي الحالي، يعد تحويل المستندات من تنسيق إلى آخر وإرسالها عبر البريد الإلكتروني مهمة شائعة. سترشدك هذه المقالة خلال عملية تحويل ملف DOCX إلى تنسيق MHTML ثم إرساله كبريد إلكتروني باستخدام Aspose.Words for .NET. سنقوم بتفصيل كل خطوة في دليل مفصل وسهل المتابعة، مما يضمن فهمك للعملية من البداية إلى النهاية. دعونا الغوص في!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. Aspose.Words for .NET: قم بتنزيل وتثبيت مكتبة Aspose.Words for .NET من[صفحة الإصدارات Aspose](https://releases.aspose.com/words/net/).
2.  Aspose.Email for .NET: قم بتنزيل وتثبيت مكتبة Aspose.Email for .NET من[صفحة الإصدارات Aspose](https://releases.aspose.com/email/net/).
3. .NET Framework: تأكد من تثبيت .NET Framework على جهازك.
4. خادم SMTP: تحتاج إلى الوصول إلى خادم SMTP لإرسال رسائل البريد الإلكتروني.

## استيراد مساحات الأسماء

لاستخدام Aspose.Words وAspose.Email في مشروعك، تحتاج إلى استيراد مساحات الأسماء الضرورية. أضف ما يلي باستخدام التوجيهات الموجودة أعلى ملف C# الخاص بك:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

دعنا نقسم العملية إلى خطوات متعددة للتأكد من أنك تفهم كل جزء بوضوح.

## الخطوة 1: قم بتحميل مستند DOCX

 أولاً، تحتاج إلى تحميل مستند DOCX الذي تريد تحويله. استخدم`Document` فئة من Aspose.Words لتحميل ملف DOCX الخاص بك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## الخطوة 2: احفظ المستند باسم MHTML

 بعد ذلك، احفظ المستند الذي تم تحميله كملف MHTML. ويتم ذلك باستخدام`Save` طريقة`Document` فصل.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// قم بإرجاع الدفق إلى البداية حتى يتمكن Aspose.Email من قراءته.
stream.Position = 0;
```

## الخطوة 3: إنشاء رسالة بريد إلكتروني

الآن، قم بإنشاء رسالة بريد إلكتروني من دفق MHTML باستخدام Aspose.Email. سوف تستخدم`MailMessage` الطبقة لهذا الغرض.

```csharp
// قم بإنشاء رسالة بريد إلكتروني Aspose.Email MIME من الدفق.
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## الخطوة 4: أرسل البريد الإلكتروني

 وأخيرًا، أرسل البريد الإلكتروني باستخدام عميل SMTP. قم بتكوين عميل SMTP باستخدام تفاصيل خادم SMTP الخاص بك واستخدم`Send` طريقة إرسال الرسالة.

```csharp
// أرسل الرسالة باستخدام Aspose.Email.
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## خاتمة

تهانينا! لقد نجحت في تحويل مستند DOCX إلى MHTML وأرسلته عبر البريد الإلكتروني باستخدام Aspose.Words for .NET. تتضمن هذه العملية تحميل المستند وتحويله إلى MHTML وإنشاء رسالة بريد إلكتروني وإرسالها باستخدام عميل SMTP. باستخدام هذه الخطوات، يمكنك بسهولة أتمتة تحويل المستندات وإرسالها عبر البريد الإلكتروني في تطبيقاتك.

## الأسئلة الشائعة

### هل يمكنني استخدام هذه الطريقة لتحويل تنسيقات المستندات الأخرى؟
نعم، يدعم Aspose.Words العديد من التنسيقات، ويمكنك تحويل المستندات مثل DOC، وDOCX، وRTF، والمزيد إلى MHTML.

### كيف يمكنني إضافة مرفقات إلى البريد الإلكتروني؟
 يمكنك استخدام`Attachments` ملكية`MailMessage`فئة لإضافة مرفقات إلى البريد الإلكتروني الخاص بك.

### هل Aspose.Words متوافق مع .NET Core؟
نعم، Aspose.Words متوافق مع .NET Core. يمكنك استخدامه في تطبيقات .NET Core أيضًا.

### هل أحتاج إلى ترخيص لـ Aspose.Words و Aspose.Email؟
 نعم، تتطلب كلا المكتبتين تراخيص. يمكنك الحصول على ترخيص مؤقت من[Aspose صفحة الشراء](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.

### أين يمكنني العثور على المزيد من الوثائق؟
 يمكنك العثور على وثائق مفصلة عن Aspose.Words[هنا](https://reference.aspose.com/words/net/) و Aspose.Email[هنا](https://reference.aspose.com/email/net/).
