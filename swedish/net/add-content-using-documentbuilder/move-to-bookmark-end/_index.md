---
title: الانتقال إلى نهاية الإشارة المرجعية
linktitle: الانتقال إلى نهاية الإشارة المرجعية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام Aspose.Words for .NET للانتقال إلى نهاية إشارة مرجعية في مستندات Word باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/move-to-bookmark-end/
---

في هذا المثال ، سوف نستكشف ميزة Move To Bookmark End في Aspose.Words for .NET. Aspose.Words مكتبة قوية لمعالجة المستندات تمكن المطورين من إنشاء وتعديل وتحويل مستندات Word برمجيًا. تسمح لنا ميزة Move To Bookmark End بالانتقال إلى نهاية إشارة مرجعية معينة داخل مستند وإضافة محتوى بعدها.

## تهيئة البيئة

قبل الخوض في تفاصيل التنفيذ ، دعنا نتأكد من إعداد البيئة اللازمة للعمل مع Aspose.Words for .NET. تأكد من حصولك على ما يلي:

- تثبيت عملي لـ Aspose.Words لمكتبة .NET
- المعرفة الأساسية بلغة البرمجة C #
- الوصول إلى بيئة تطوير .NET

## فهم ميزة Move To Bookmark End في Aspose.Words for .NET

تسمح لك ميزة Move To Bookmark End بالانتقال إلى نهاية إشارة مرجعية في مستند Word باستخدام Aspose.Words for .NET. هذه الميزة مفيدة عندما تريد إضافة محتوى بعد إشارة مرجعية معينة في وثيقتك برمجيًا.

## شرح شفرة المصدر خطوة بخطوة

دعنا نقسم كود المصدر المقدم خطوة بخطوة لفهم كيفية استخدام ميزة Move To Bookmark End في Aspose.Words for .NET.

## الخطوة 1: تهيئة مستند إنشاء المستندات

 أولاً ، نحتاج إلى تهيئة`Document` و`DocumentBuilder` أشياء:

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: الانتقال إلى نهاية الإشارة المرجعية

 للانتقال إلى نهاية إشارة مرجعية ، استخدم ملحق`MoveToBookmark` طريقة`DocumentBuilder` فصل:

```csharp
builder.MoveToBookmark("MyBookmark1", false, true);
```

 ال`MoveToBookmark` تأخذ الطريقة ثلاث معلمات:
- اسم الإشارة المرجعية: أدخل اسم الإشارة المرجعية التي تريد الانتقال إليها.
-  IsBookmarkStart: اضبط على`false` للانتقال إلى نهاية الإشارة المرجعية.
-  IsBookmarkEnd: اضبط على`true` للإشارة إلى أنك تريد الانتقال إلى نهاية الإشارة المرجعية.

## الخطوة 3: إضافة محتوى في نهاية الإشارة المرجعية

بمجرد الانتقال إلى نهاية الإشارة المرجعية ، يمكنك إضافة محتوى باستخدام الطرق المختلفة التي يوفرها`DocumentBuilder` فصل. في هذا المثال ، نستخدم الامتداد`Writeln` طريقة كتابة سطر من النص:

```csharp
builder.Writeln("This is a bookmark.");
```

 ال`Writeln` تقوم الطريقة بإلحاق النص المحدد كفقرة جديدة في الموضع الحالي لملف`DocumentBuilder`.

### مثال على شفرة المصدر لـ Move To Bookmark End باستخدام Aspose.Words for .NET

```csharp

	Document doc = new Document(MyDir + "Bookmarks.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.MoveToBookmark("MyBookmark1", false, true);
	builder.Writeln("This is a bookmark.");
	
```

## خاتمة

استكشفنا ميزة Move To Bookmark End في Aspose.Words for .NET. لقد تعلمنا كيفية الانتقال إلى نهاية إشارة مرجعية وإضافة محتوى برمجيًا باستخدام كود المصدر المقدم. توفر هذه الميزة المرونة في التعامل مع مستندات Word باستخدام Aspose.Words for .NET.

