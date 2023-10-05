---
title: تحويل Docx إلى Mhtml وإرسال البريد الإلكتروني
linktitle: تحويل Docx إلى Mhtml وإرسال البريد الإلكتروني
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحويل مستندات Word من Docx إلى MHTML وإرسالها كرسائل بريد إلكتروني باستخدام Aspose.Words وAspose.Email. البرنامج التعليمي خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

في هذا البرنامج التعليمي خطوة بخطوة، سنرشدك حول كيفية استخدام Aspose.Words for .NET لتحويل مستند Word بتنسيق Docx إلى MHTML وإرساله كبريد إلكتروني باستخدام Aspose.Email. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

 للبدء، تأكد من تثبيت مكتبات Aspose.Words for .NET وAspose.Email وإعدادها في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك، قم بتنزيل المكتبات وتثبيتها من[Aspose.Releases](https://releases.aspose.com/words/net/).

## الخطوة 1: تهيئة كائن المستند

 أولاً، قم بتهيئة`Document`الكائن بالمسار إلى مستندك المصدر بتنسيق Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## الخطوة 2: حفظ المستند بتنسيق MHTML

 بعد ذلك، قم بحفظ المستند إلى a`Stream` كائن بتنسيق MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## الخطوة 3: الترجيع الدفق

بما أن Aspose.Email يحتاج إلى قراءة الدفق من البداية، قم بإرجاع الدفق إلى البداية:

```csharp
stream.Position = 0;
```

## الخطوة 4: إنشاء رسالة Aspose.Email MIME

 إنشاء`MailMessage` كائن من الدفق باستخدام`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

لا تتردد في تخصيص خصائص الرسالة مثل المرسل والمستلم والموضوع.

## الخطوة 5: إرسال البريد الإلكتروني

 استخدم Aspose.Email`SmtpClient` لإرسال البريد الإلكتروني:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

تأكد من توفير عنوان مضيف خادم SMTP الصحيح.

هذا كل شيء! لقد نجحت في تحويل مستند Word بتنسيق Docx إلى MHTML وأرسلته كبريد إلكتروني باستخدام Aspose.Words for .NET وAspose.Email.

### مثال على التعليمات البرمجية المصدر لـ Docx To Mhtml وإرسال البريد الإلكتروني باستخدام Aspose.Words لـ .NET

```csharp

	// Document doc = new Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//قم بإرجاع الدفق إلى البداية حتى يتمكن Aspose.Email من قراءته.
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

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك المحددة.

### الأسئلة الشائعة

#### كيفية تحويل ملف DOCX إلى MHTML؟

لتحويل ملف DOCX إلى MHTML، يمكنك استخدام أدوات البرامج أو المكتبات التي توفر هذه الوظيفة. يعد Aspose.Words for .NET خيارًا موثوقًا به لهذا التحويل. يمكنك استخدام واجهة برمجة تطبيقات المكتبة لتحميل ملف DOCX وحفظه بتنسيق MHTML.

#### كيف أرسل بريدًا إلكترونيًا يحتوي على ملف MHTML مرفق؟

لإرسال بريد إلكتروني يحتوي على ملف MHTML كمرفق، يمكنك استخدام المكتبات أو الأدوات الخاصة بإرسال البريد الإلكتروني، مثل System.Net.Mail في .NET. يجب عليك إنشاء رسالة بريد إلكتروني وتحديد المستلم والموضوع والمحتوى، ثم إضافة ملف MHTML كمرفق بالرسالة قبل إرسالها.

#### ما هي القيود المفروضة على عملية تحويل وإرسال البريد الإلكتروني؟

تعتمد قيود عملية تحويل البريد الإلكتروني وإرساله على الأدوات المحددة التي تستخدمها. قد تحتوي بعض الأدوات على قيود تتعلق بحجم الملف أو إعدادات الأمان أو بروتوكولات البريد الإلكتروني المدعومة. من المهم اختيار الأدوات التي تناسب احتياجاتك ومراعاة هذه القيود عند التنفيذ.

#### هل Aspose أداة موثوقة لتحويل DOCX إلى MHTML وإرسال البريد الإلكتروني؟

نعم، يعد Aspose.Words for .NET أداة موثوقة لتحويل DOCX إلى MHTML وإرسال البريد الإلكتروني. يتم استخدامه على نطاق واسع من قبل المطورين والمهنيين لأدائه وجودته. توفر الأداة وثائق شاملة وميزات متقدمة ودعمًا فنيًا مخصصًا، مما يجعلها خيارًا موصى به لهذه المهام.