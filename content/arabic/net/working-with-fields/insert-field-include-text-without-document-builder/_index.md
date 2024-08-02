---
title: إدراج حقل يتضمن نصًا بدون أداة إنشاء المستندات
linktitle: قم بإدراج FieldIncludeText بدون منشئ المستندات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج FieldIncludeText دون استخدام DocumentBuilder في Aspose.Words لـ .NET من خلال دليلنا التفصيلي خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-field-include-text-without-document-builder/
---
## مقدمة

في عالم أتمتة المستندات ومعالجتها، يمثل Aspose.Words for .NET أداة قوية. اليوم، نحن نتعمق في دليل تفصيلي حول كيفية إدراج FieldIncludeText دون استخدام DocumentBuilder. سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة، مما يضمن فهمك لكل جزء من الكود والغرض منه.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، دعنا نتأكد من أن لديك كل ما تحتاجه:

1.  Aspose.Words for .NET: تأكد من تثبيت أحدث إصدار لديك. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/net/).
2. بيئة تطوير .NET: أي بيئة تطوير متكاملة متوافقة مع .NET مثل Visual Studio.
3. المعرفة الأساسية بـ C#: الإلمام ببرمجة C# سيساعدك على المتابعة.

## استيراد مساحات الأسماء

أول الأشياء أولاً، نحتاج إلى استيراد مساحات الأسماء الضرورية. توفر مساحات الأسماء هذه إمكانية الوصول إلى الفئات والأساليب المطلوبة لمعالجة مستندات Word.

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
```

الآن، دعونا نقسم المثال إلى خطوات متعددة. سيتم شرح كل خطوة بالتفصيل لضمان الوضوح.

## الخطوة 1: قم بتعيين مسار الدليل

الخطوة الأولى هي تحديد المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي سيتم فيه تخزين مستندات Word الخاصة بك والوصول إليها.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء الوثيقة والفقرة

بعد ذلك، نقوم بإنشاء مستند جديد وفقرة داخل هذا المستند. ستحتوي هذه الفقرة على الحقل FieldIncludeText.

```csharp
// قم بإنشاء المستند والفقرة.
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## الخطوة 3: أدخل حقل FieldIncludeText

الآن، نقوم بإدراج الحقل FieldIncludeText في الفقرة. يسمح لك هذا الحقل بتضمين النص من مستند آخر.

```csharp
// أدخل حقل FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

## الخطوة 4: تعيين خصائص الحقل

نحتاج إلى تحديد خصائص حقل FieldIncludeText. يتضمن ذلك تعيين اسم الإشارة المرجعية والمسار الكامل للمستند المصدر.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = dataDir + "IncludeText.docx";
```

## الخطوة 5: إلحاق فقرة بالمستند

بعد إعداد الحقل، نقوم بإلحاق الفقرة بنص القسم الأول من المستند.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## الخطوة 6: تحديث الحقل

قبل حفظ المستند، نحتاج إلى تحديث FieldIncludeText للتأكد من أنه يسحب المحتوى الصحيح من المستند المصدر.

```csharp
fieldIncludeText.Update();
```

## الخطوة 7: احفظ المستند

وأخيرًا، نقوم بحفظ المستند في الدليل المحدد.

```csharp
doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

## خاتمة

وهناك لديك! باتباع هذه الخطوات، يمكنك بسهولة إدراج FieldIncludeText دون استخدام DocumentBuilder في Aspose.Words لـ .NET. يوفر هذا الأسلوب طريقة مبسطة لتضمين محتوى من مستند إلى آخر، مما يجعل مهام أتمتة المستندات الخاصة بك أكثر بساطة.

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟  
Aspose.Words for .NET هي مكتبة قوية للعمل مع مستندات Word في تطبيقات .NET. يسمح بإنشاء المستندات وتحريرها وتحويلها برمجياً.

### لماذا استخدام FieldIncludeText؟  
يعد FieldIncludeText مفيدًا لتضمين المحتوى ديناميكيًا من مستند إلى آخر، مما يتيح المزيد من المستندات المعيارية والقابلة للصيانة.

### هل يمكنني استخدام هذه الطريقة لتضمين نص من تنسيقات ملفات أخرى؟  
يعمل FieldIncludeText بشكل خاص مع مستندات Word. بالنسبة للتنسيقات الأخرى، قد تحتاج إلى أساليب أو فئات مختلفة توفرها Aspose.Words.

### هل Aspose.Words for .NET متوافق مع .NET Core؟  
نعم، يدعم Aspose.Words for .NET .NET Framework و.NET Core و.NET 5/6.

### كيف يمكنني الحصول على نسخة تجريبية مجانية من Aspose.Words لـ .NET؟  
 يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).