---
title: هدف المقارنة
linktitle: هدف المقارنة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على ميزة مقارنة الهدف في Aspose.Words for .NET التي تسمح لك بمقارنة المستندات وإنشاء مستند جديد يحتوي على التغييرات التي تم إجراؤها.
type: docs
weight: 10
url: /es/net/compare-documents/comparison-target/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم وظيفة هدف المقارنة في Aspose.Words for .NET.

## الخطوة 1: مقدمة

تسمح لك ميزة المقارنة المستهدفة في Aspose.Words for .NET بمقارنة مستندين وإنشاء مستند جديد يحتوي على التغييرات التي تم إجراؤها على المستند الهدف. يمكن أن يكون هذا مفيدًا لتعقب التغييرات التي تم إجراؤها بين الإصدارات المختلفة من المستند.

## الخطوة الثانية: تهيئة البيئة

قبل أن تبدأ ، تحتاج إلى إعداد بيئة التطوير الخاصة بك للعمل مع Aspose.Words for .NET. تأكد من تثبيت مكتبة Aspose.Words وأن لديك مشروع C # مناسب لتضمين الكود.

## الخطوة 3: إضافة التجميعات المطلوبة

لاستخدام ميزة هدف المقارنة في Aspose.Words for .NET ، يجب عليك إضافة التجميعات الضرورية إلى مشروعك. تأكد من أن لديك المراجع المناسبة لـ Aspose. Words في مشروعك.

```csharp
using Aspose.Words;
```

## الخطوة 4: تهيئة المستند

في هذه الخطوة ، سنقوم بتهيئة وثيقتين للمقارنة. يجب عليك تحديد مسار الدليل حيث توجد المستندات الخاصة بك ، وكذلك اسم المستند المصدر.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// تهيئة الوثيقة أ للمقارنة.
Document docA = new Document(dataDir + "DocumentA.docx");

// قم بنسخ المستند A لإنشاء نسخة متطابقة من المستند B.
Document docB = docA.Clone();
```

## الخطوة 5: تكوين خيارات المقارنة

في هذه الخطوة ، سنقوم بتكوين خيارات المقارنة لتحديد سلوك المقارنة. تتضمن الخيارات القدرة على تجاهل التنسيق ، بالإضافة إلى هدف المقارنة ، وهو الخيار "إظهار التغييرات في" في مربع الحوار "مقارنة المستندات" في Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## الخطوة 6: مقارنة المستندات

سنقوم الآن بمقارنة المستندات وإنشاء النتيجة في مستند جديد.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 ال`Compare` يقارن الأسلوب المستند A بالمستند B ويحفظ التغييرات في المستند A. يمكنك تحديد اسم المستخدم وتاريخ المقارنة كمرجع.

### نموذج لشفرة مصدر للمقارنة الهدف باستخدام Aspose.Words for .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// يتعلق بخيار "إظهار التغييرات في" Microsoft Word في مربع الحوار "مقارنة المستندات".
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## خاتمة

في هذه المقالة ، استكشفنا ميزة هدف الفرق في Aspose.Words for .NET. تتيح لك هذه الميزة مقارنة مستندين وإنشاء مستند جديد يحتوي على التغييرات التي تم إجراؤها. يمكنك استخدام هذه المعرفة لتعقب التغييرات بين الإصدارات المختلفة من مستنداتك.

