---
title: تكوين ارتباط إلى المحتوى
linktitle: تكوين ارتباط إلى المحتوى
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل تفصيلي خطوة بخطوة لإعداد الارتباط بالمحتوى في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-properties/configuring-link-to-content/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لإعداد الارتباط بالمحتوى باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة الارتباط بمحتوى معين في مستند.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: إنشاء المستند والمنشئ

في هذه الخطوة ، سننشئ مستندًا جديدًا ونهيئ المُنشئ. استخدم الكود التالي:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إنشاء إشارة مرجعية

الآن سنقوم بإنشاء إشارة مرجعية في المستند. استخدم الكود التالي لإنشاء إشارة مرجعية بنص بداخلها:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

ينشئ هذا الرمز إشارة مرجعية تسمى "MyBookmark" ويضيف بعض النص بداخله.

## الخطوة الرابعة: إعداد رابط المحتوى

الآن سنقوم بتكوين رابط المحتوى باستخدام خصائص المستند. استخدم الكود التالي لإضافة واسترداد ارتباط المحتوى:

```csharp
// احصل على قائمة بجميع الخصائص المخصصة في المستند.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// أضف خاصية مرتبطة بالمحتوى.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

يضيف هذا الرمز خاصية متعلقة بالمحتوى تسمى "Bookmark" مع الإشارة المرجعية "MyBookmark". بعد ذلك ، يقوم باسترداد معلومات الخاصية المتعلقة بالمحتوى مثل حالة الارتباط ومصدر الارتباط وقيمة الخاصية.

### مثال على شفرة المصدر لتكوين ارتباط إلى المحتوى باستخدام Aspose.Words for .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// استرجع قائمة بكل خصائص المستند المخصصة من الملف.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// إضافة مرتبطة بخاصية المحتوى.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

لقد تعلمت الآن كيفية تكوين رابط المحتوى في مستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة إنشاء وتكوين روابط لمحتوى معين في مستنداتك الخاصة.