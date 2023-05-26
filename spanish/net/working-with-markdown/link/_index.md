---
title: وصلة
linktitle: وصلة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج الروابط مع Aspose.Words for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /es/net/working-with-markdown/link/
---

في هذا المثال ، سنرشدك إلى كيفية استخدام ميزة الروابط مع Aspose.Words for .NET. تُستخدم الروابط لإنشاء مراجع قابلة للنقر لمواقع الويب أو المستندات الأخرى.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة الثانية: إدخال ارتباط

 يمكننا إدراج ارتباط باستخدام ملف`Insertlink` طريقة منشئ الوثيقة. نحتاج إلى تحديد نص الرابط ، هنا "Aspose" ، بالإضافة إلى عنوان URL المقصود.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com "، خطأ) ؛
```

### مثال على شفرة المصدر للروابط مع Aspose.Words for .NET


```csharp
	// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
	DocumentBuilder builder = new DocumentBuilder();

	// أدخل ارتباط.
	builder.Insertlink("Aspose", "https://www.aspose.com "، خطأ) ؛
            
```
تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة الروابط مع Aspose.Words for .NET.

