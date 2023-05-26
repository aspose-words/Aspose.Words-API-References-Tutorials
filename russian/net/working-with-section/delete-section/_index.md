---
title: حذف القسم
linktitle: حذف القسم
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، تعرف على كيفية إزالة قسم معين من مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/working-with-section/delete-section/
---

في هذا البرنامج التعليمي ، سوف نوضح لك كيفية حذف قسم معين من مستند Word باستخدام مكتبة Aspose.Words لـ .NET. يمكن أن يكون حذف قسم مفيدًا لإعادة ترتيب أو حذف أجزاء معينة من المستند. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك

## الخطوة 1: قم بإنشاء مستند ومنشئ
 أولاً ، سننشئ مثيلاً لملف`Document` فئة وما يرتبط بها`DocumentBuilder` المُنشئ لبناء المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة الثانية: إضافة محتوى وأقسام
 بعد ذلك ، سنستخدم ملف`DocumentBuilder` المُنشئ لإضافة محتوى وأقسام إلى المستند. في هذا المثال ، نضيف سطرين من النص وقسمين.

```csharp
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello2");
doc.AppendChild(new Section(doc));
```

## الخطوة 3: حذف قسم معين
 لإزالة قسم معين من المستند ، سنستخدم ملف`RemoveAt` طريقة المستند`Sections` المجموعة ، مع تحديد فهرس القسم المراد إزالته.

```csharp
doc.Sections.RemoveAt(0);
```

### نموذج التعليمات البرمجية المصدر لـ Delete Section باستخدام Aspose.Words for .NET 

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.Writeln("Hello1");
	doc.AppendChild(new Section(doc));
	builder.Writeln("Hello2");
	doc.AppendChild(new Section(doc));
	doc.Sections.RemoveAt(0);

```

## خاتمة
في هذا البرنامج التعليمي ، رأينا كيفية إزالة قسم معين من مستند Word باستخدام Aspose.Words for .NET. يتيح لك حذف الأقسام إعادة ترتيب أجزاء معينة من المستند أو حذفها. لا تتردد في تخصيص هذه الميزة واستخدامها وفقًا لاحتياجاتك الخاصة.

