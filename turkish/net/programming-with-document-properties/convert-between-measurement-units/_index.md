---
title: التحويل بين وحدات القياس
linktitle: التحويل بين وحدات القياس
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة للتحويل بين وحدات القياس في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/convert-between-measurement-units/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # للتحويل بين وحدات القياس باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة تحديد الهوامش ومسافات الرأس والتذييل وما إلى ذلك في وحدات قياس مختلفة.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: إنشاء المستند والمنشئ

في هذه الخطوة ، سننشئ مستندًا جديدًا ونهيئ المُنشئ. استخدم الكود التالي:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: تكوين وحدات القياس

سنقوم الآن بتحويل قيم الهوامش ومسافات الرأس والتذييل وما إلى ذلك في وحدات قياس مختلفة. استخدم الكود التالي لتحديد القيم في وحدات قياس معينة:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 يستخدم هذا الرمز الامتداد`ConvertUtil` فئة Aspose. Words لتحويل القيم المحددة إلى بوصة (`InchToPoint` ). يمكنك أيضًا استخدام طرق التحويل الأخرى المتوفرة في ملف`ConvertUtil` فئة لتحويل القيم إلى وحدات قياس أخرى.

### مثال على شفرة المصدر للتحويل بين وحدات القياس باستخدام Aspose.Words for .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

لقد تعلمت الآن كيفية التحويل بين وحدات القياس عند تحديد الهوامش ومسافات الرأس والتذييل وما إلى ذلك في مستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة تحديد القيم في وحدات القياس المطلوبة في مستنداتك الخاصة.