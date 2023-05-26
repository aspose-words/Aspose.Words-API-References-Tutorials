---
title: رد اتصال الواصلة
linktitle: رد اتصال الواصلة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام رد نداء الواصلة في Aspose.Words for .NET للتعامل مع الواصلة في الكلمات.
type: docs
weight: 10
url: /zh/net/working-with-hyphenation/hyphenation-callback/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوضح لك كيفية استخدام ميزة رد الاتصال في Aspose.Words for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت Aspose.Words for .NET وتهيئته في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: حفظ تذكير الواصلة

 أولاً ، سنقوم بتسجيل رد نداء الواصلة باستخدام مخصص`CustomHyphenationCallback` فصل. سيسمح لنا ذلك بالتعامل مع الواصلة وفقًا لقواعدنا الخاصة:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 تأكد من أنك قمت بتنفيذ`CustomHyphenationCallback`فئة وفقًا لاحتياجاتك الخاصة.

## الخطوة 2: تحميل المستند وتطبيق الواصلة

بعد ذلك ، قم بتحميل المستند الخاص بك من الدليل المحدد وقم بوصل الكلمات باستخدام Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## الخطوة 3: معالجة أخطاء القاموس المفقودة

في حالة فقد قاموس الواصلة ، سنكتشف الاستثناء المقابل ونعرض رسالة خطأ:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## الخطوة 4: تنظيف وتعطيل تذكير الواصلة

أخيرًا ، للتنظيف وإيقاف تشغيل تذكير الواصلة ، قم بتنفيذ الخطوات التالية:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

يؤدي هذا إلى تنظيف وتعطيل تذكير الواصلة بعد الانتهاء من المعالجة.

لذا ! لقد نجحت في استخدام رد نداء الواصلة في Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لرد الاتصال الواصلة مع Aspose.Words for .NET

```csharp
try
{
	 // تسجيل رد الاتصال الواصلة.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله ليناسب احتياجاتك الخاصة.