---
title: تكوين الارتباط إلى المحتوى
linktitle: تكوين الارتباط إلى المحتوى
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإعداد الارتباط بالمحتوى في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-properties/configuring-link-to-content/
---

في هذا البرنامج التعليمي، سنرشدك خلال التعليمات البرمجية المصدر لـ C# لإعداد الارتباط بالمحتوى باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة الارتباط بمحتوى محدد في المستند.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: إنشاء المستند والمنشئ

في هذه الخطوة سنقوم بإنشاء مستند جديد وتهيئة المنشئ. استخدم الكود التالي:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إنشاء إشارة مرجعية

الآن سنقوم بإنشاء إشارة مرجعية في المستند. استخدم الكود التالي لإنشاء إشارة مرجعية تحتوي على نص بداخلها:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

ينشئ هذا الرمز إشارة مرجعية تسمى "MyBookmark" ويضيف بعض النص بداخلها.

## الخطوة 4: إعداد رابط المحتوى

سنقوم الآن بتكوين الارتباط بالمحتوى باستخدام خصائص المستند. استخدم الكود التالي لإضافة واسترداد الرابط للمحتوى:

```csharp
// احصل على قائمة بجميع الخصائص المخصصة في المستند.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// إضافة خاصية مرتبطة بالمحتوى.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

يضيف هذا الرمز خاصية مرتبطة بالمحتوى تسمى "إشارة مرجعية" مع الإشارة المرجعية "MyBookmark". ثم يقوم بعد ذلك باسترداد معلومات الخاصية ذات الصلة بالمحتوى مثل حالة الارتباط ومصدر الارتباط وقيمة الخاصية.

### مثال على التعليمات البرمجية المصدر لتكوين الارتباط بالمحتوى باستخدام Aspose.Words لـ .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// استرداد قائمة بجميع خصائص المستند المخصصة من الملف.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// إضافة مرتبطة بخاصية المحتوى.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

لقد تعلمت الآن كيفية تكوين الارتباط بالمحتوى في مستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة إنشاء وتكوين روابط لمحتوى معين في مستنداتك الخاصة.