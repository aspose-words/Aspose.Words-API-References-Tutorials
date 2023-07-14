---
title: تحويل Docx إلى Mhtml وإرسال بريد إلكتروني
linktitle: تحويل Docx إلى Mhtml وإرسال بريد إلكتروني
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تحويل مستندات Word من Docx إلى MHTML وإرسالها كرسائل بريد إلكتروني باستخدام Aspose.Words و Aspose.Email. البرنامج التعليمي خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لتحويل مستند Word بتنسيق Docx إلى MHTML وإرساله كبريد إلكتروني باستخدام Aspose.Email. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد مكتبات Aspose.Words لكل من .NET و Aspose.Email في بيئة التطوير لديك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبات وتثبيتها من مواقعها الرسمية على الويب.

## الخطوة 1: تهيئة كائن المستند

 أولاً ، قم بتهيئة ملف`Document` كائن مع المسار إلى مستندك المصدر بتنسيق Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## الخطوة 2: حفظ المستند بتنسيق MHTML

 بعد ذلك ، احفظ المستند في ملف`Stream` كائن بتنسيق MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## الخطوة 3: إرجاع الدفق

منذ Aspose.Email يحتاج إلى قراءة الدفق من البداية ، قم بإعادة البث إلى البداية:

```csharp
stream.Position = 0;
```

## الخطوة 4: إنشاء Aspose.Email رسالة بريد إلكتروني

 إنشاء`MailMessage` كائن من الدفق باستخدام`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

لا تتردد في تخصيص خصائص الرسالة مثل المرسل والمستلم والموضوع.

## الخطوة الخامسة: إرسال البريد الإلكتروني

 استخدم Aspose`SmtpClient` لإرسال البريد الإلكتروني:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

تأكد من توفير عنوان مضيف خادم SMTP الصحيح.

هذا كل شيء! لقد نجحت في تحويل مستند Word بتنسيق Docx إلى MHTML وأرسلته كبريد إلكتروني باستخدام Aspose.Words for .NET و Aspose.Email.

### مثال على شفرة المصدر لـ Docx To Mhtml وإرسال بريد إلكتروني باستخدام Aspose.Words for .NET

```csharp

	// مستند doc = مستند جديد (MyDir + "Document.docx") ؛

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	// قم بإعادة البث إلى البداية حتى يتمكن Aspose.Email من قراءته.
	stream.Position = 0;

	// قم بإنشاء رسالة بريد إلكتروني Aspose.Email MIME من الدفق.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// أرسل الرسالة باستخدام Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.

### أسئلة وأجوبة

#### كيفية تحويل ملف DOCX إلى MHTML؟

لتحويل ملف DOCX إلى MHTML ، يمكنك استخدام أدوات البرامج أو المكتبات التي توفر هذه الوظيفة. يعد Aspose.Words for .NET خيارًا موثوقًا به لهذا التحويل. يمكنك استخدام مكتبة API لتحميل ملف DOCX وحفظه بتنسيق MHTML.

#### كيف أرسل بريدًا إلكترونيًا يحتوي على ملف MHTML مرفق؟

لإرسال بريد إلكتروني مع ملف MHTML كمرفق ، يمكنك استخدام المكتبات أو الأدوات الخاصة بإرسال البريد الإلكتروني ، مثل System.Net.Mail في .NET. يجب عليك إنشاء رسالة بريد إلكتروني ، وتحديد المستلم والموضوع والمحتوى ، ثم إضافة ملف MHTML كمرفق بالرسالة قبل إرسالها.

#### ما هي حدود عملية تحويل البريد الإلكتروني وإرساله؟

تعتمد قيود عملية تحويل البريد الإلكتروني وإرساله على الأدوات المحددة التي تستخدمها. قد يكون لبعض الأدوات قيود تتعلق بحجم الملف أو إعدادات الأمان أو بروتوكولات البريد الإلكتروني المدعومة. من المهم اختيار الأدوات التي تناسب احتياجاتك ومراعاة هذه القيود عند التنفيذ.

#### هل Aspose أداة موثوقة لتحويل DOCX إلى MHTML وإرسال البريد الإلكتروني؟

نعم ، Aspose.Words for .NET أداة موثوقة لتحويل DOCX إلى MHTML وإرسال البريد الإلكتروني. يستخدم على نطاق واسع من قبل المطورين والمحترفين لأدائه وجودته. توفر الأداة توثيقًا شاملاً وميزات متقدمة ودعمًا فنيًا مخصصًا ، مما يجعلها خيارًا موصى به لهذه المهام.