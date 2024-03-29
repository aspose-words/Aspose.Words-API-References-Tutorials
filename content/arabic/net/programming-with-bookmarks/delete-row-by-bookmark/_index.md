---
title: حذف الصف حسب الإشارة المرجعية في مستند Word
linktitle: حذف الصف حسب الإشارة المرجعية في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية حذف صف جدول بناءً على إشارة مرجعية محددة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/delete-row-by-bookmark/
---

في هذه المقالة، سوف نستكشف كود مصدر C# أعلاه لفهم كيفية استخدام وظيفة حذف الصف حسب الإشارة المرجعية في Aspose.Words لمكتبة .NET. تتيح لك هذه الميزة حذف صف جدول بناءً على إشارة مرجعية محددة في مستند Word.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: الحصول على الإشارة المرجعية

 نحن نستخدم ال`Bookmarks` خاصية نطاق المستند للحصول على الإشارة المرجعية المحددة التي نريد استخدامها لحذف صف الجدول:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## الخطوة 2: حذف صف الجدول

 نحن نستخدم ال`GetAncestor` طريقة الحصول على`Row` اكتب العنصر الأصلي للإشارة المرجعية. بعد ذلك، نستخدم`Remove` طريقة إزالة صف الجدول:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### مثال على التعليمات البرمجية المصدر لحذف الصف حسب الإشارة المرجعية باستخدام Aspose.Words لـ .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح حذف صف جدول بناءً على إشارة مرجعية محددة باستخدام Aspose.Words for .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## خاتمة

في هذه المقالة، قمنا باستكشاف التعليمات البرمجية المصدر لـ C# لفهم كيفية استخدام وظيفة حذف الصف حسب الإشارة المرجعية في Aspose.Words لـ .NET. لقد اتبعنا دليلاً خطوة بخطوة لحذف صف جدول بناءً على إشارة مرجعية محددة في المستند.

### الأسئلة الشائعة لحذف الصف حسب الإشارة المرجعية في مستند Word

#### س: هل يمكنني حذف صفوف متعددة باستخدام نفس الإشارة المرجعية؟

ج: نعم، يمكنك حذف صفوف متعددة باستخدام نفس الإشارة المرجعية. ومع ذلك، يتعين عليك التعامل مع المنطق الموجود في التعليمات البرمجية الخاصة بك لتحديد عدد الصفوف المطلوب حذفها وإجراء التعديلات اللازمة على مقتطف التعليمات البرمجية المقدم.

#### س: ماذا يحدث إذا كانت الإشارة المرجعية غير موجودة في المستند؟

ج: إذا كانت الإشارة المرجعية المحددة غير موجودة في المستند، فسيقوم مقتطف التعليمات البرمجية بإرجاع قيمة فارغة لكائن الإشارة المرجعية. لذلك، تحتاج إلى التعامل مع هذا السيناريو في التعليمات البرمجية الخاصة بك عن طريق إضافة عمليات التحقق المناسبة قبل محاولة حذف صف الجدول.

#### س: هل مكتبة Aspose.Words مجانية الاستخدام؟

 ج: مكتبة Aspose.Words هي مكتبة تجارية، وقد تحتاج إلى ترخيص صالح لاستخدامها في مشاريعك. يمكنك زيارة[Aspose.Words لمراجع .NET API](https://reference.aspose.com/words/net/) لمعرفة المزيد حول خيارات الترخيص والأسعار.

#### س: هل يمكنني حذف صفوف من جدول في قسم معين من مستند Word؟

ج: نعم، يمكنك حذف صفوف من جدول في قسم معين من مستند Word. يمكنك تعديل مقتطف الشفرة المقدم لاستهداف قسم معين باستخدام النطاق أو الإشارة المرجعية المناسبة داخل هذا القسم.