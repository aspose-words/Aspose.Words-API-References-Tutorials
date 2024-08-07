---
title: استرداد نوع العرض المفضل
linktitle: استرداد نوع العرض المفضل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استرداد نوع العرض المفضل لخلايا الجدول في مستندات Word باستخدام Aspose.Words لـ .NET من خلال دليلنا خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-tables/retrieve-preferred-width-type/
---
## مقدمة

هل سبق لك أن تساءلت عن كيفية استرداد نوع العرض المفضل لخلايا الجدول في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET؟ حسنا، أنت في المكان الصحيح! في هذا البرنامج التعليمي، سنقوم بتقسيم العملية خطوة بخطوة، مما يجعلها سهلة مثل الفطيرة. سواء كنت مطورًا متمرسًا أو بدأت للتو، ستجد هذا الدليل مفيدًا وجذابًا. لذلك، دعونا نتعمق ونكتشف الأسرار الكامنة وراء إدارة عرض خلايا الجدول في مستندات Word.

## المتطلبات الأساسية

قبل أن نبدأ، هناك بعض الأشياء التي ستحتاج إليها:

1.  Aspose.Words for .NET: تأكد من تثبيت أحدث إصدار لديك. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/net/).
2. بيئة التطوير: ستحتاج إلى IDE مثل Visual Studio.
3. المعرفة الأساسية بـ C#: إن فهم أساسيات C# سيساعدك على المتابعة.
4.  نموذج مستند: قم بإعداد مستند Word مع الجداول التي يمكنك العمل عليها. يمكنك استخدام أي مستند، لكننا سنشير إليه باسم`Tables.docx` في هذا البرنامج التعليمي.

## استيراد مساحات الأسماء

أول الأشياء أولاً، فلنستورد مساحات الأسماء الضرورية. تعتبر هذه الخطوة حاسمة لأنها تهيئ بيئتنا لاستخدام ميزات Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Tables;
```

## الخطوة 1: قم بإعداد دليل المستندات الخاص بك

قبل أن نتعامل مع مستندنا، نحتاج إلى تحديد الدليل الذي يقع فيه. هذه خطوة بسيطة ولكنها أساسية.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك. هذا يخبر برنامجنا بمكان العثور على الملف الذي نريد العمل معه.

## الخطوة 2: قم بتحميل المستند

بعد ذلك، نقوم بتحميل مستند Word في تطبيقنا. وهذا يسمح لنا بالتفاعل مع محتوياته برمجياً.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

 يفتح هذا السطر من التعليمات البرمجية ملف`Tables.docx` مستند من الدليل المحدد. الآن وثيقتنا جاهزة لمزيد من العمليات.

## الخطوة 3: الوصول إلى الجدول

الآن بعد أن تم تحميل المستند، نحتاج إلى الوصول إلى الجدول الذي نريد العمل معه. للتبسيط، سنستهدف الجدول الأول في المستند.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

يسترد هذا السطر الجدول الأول من المستند. إذا كان المستند الخاص بك يحتوي على جداول متعددة، فيمكنك ضبط الفهرس لتحديد جدول مختلف.

## الخطوة 4: تمكين الاحتواء التلقائي للجدول

للتأكد من أن الجدول يقوم بضبط أعمدته تلقائيًا، نحتاج إلى تمكين خاصية الاحتواء التلقائي.

```csharp
table.AllowAutoFit = true;
```

 جلسة`AllowAutoFit` ل`true` يضمن تغيير حجم أعمدة الجدول بناءً على محتوياتها، مما يمنح طاولتنا طابعًا ديناميكيًا.

## الخطوة 5: استرداد نوع العرض المفضل للخلية الأولى

الآن يأتي جوهر البرنامج التعليمي لدينا - استرداد نوع العرض المفضل للخلية الأولى في الجدول.

```csharp
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

 تصل سطور التعليمات البرمجية هذه إلى الخلية الأولى في الصف الأول من الجدول وتسترد نوع العرض المفضل لها وقيمته. ال`PreferredWidthType` يمكن أن يكون`Auto`, `Percent` ، أو`Point`، مما يشير إلى كيفية تحديد العرض.

## الخطوة 6: عرض النتائج

أخيرًا، لنعرض المعلومات المستردة على وحدة التحكم.

```csharp
Console.WriteLine("Preferred Width Type: " + type);
Console.WriteLine("Preferred Width Value: " + value);
```

ستقوم هذه الأسطر بطباعة نوع العرض المفضل والقيمة إلى وحدة التحكم، مما يسمح لك برؤية نتائج تنفيذ التعليمات البرمجية الخاصة بك.

## خاتمة

وهنا لديك! يعد استرداد نوع العرض المفضل لخلايا الجدول في مستندات Word باستخدام Aspose.Words لـ .NET أمرًا سهلاً عند تقسيمه إلى خطوات يمكن التحكم فيها. باتباع هذا الدليل، يمكنك بسهولة التعامل مع خصائص الجدول في مستندات Word، مما يجعل مهام إدارة المستندات الخاصة بك أكثر كفاءة.

## الأسئلة الشائعة

### هل يمكنني استرداد نوع العرض المفضل لجميع الخلايا في الجدول؟

نعم، يمكنك التكرار خلال كل خلية في الجدول واسترداد أنواع العرض المفضلة لها بشكل فردي.

###  ما هي القيم المحتملة ل`PreferredWidthType`?

`PreferredWidthType` يمكن أن يكون`Auto`, `Percent` ، أو`Point`.

### هل من الممكن ضبط نوع العرض المفضل برمجياً؟

 قطعاً! يمكنك تعيين نوع العرض المفضل والقيمة باستخدام`PreferredWidth` ملكية`CellFormat` فصل.

### هل يمكنني استخدام هذه الطريقة للجداول في مستندات أخرى غير Word؟

يغطي هذا البرنامج التعليمي مستندات Word على وجه التحديد. بالنسبة لأنواع المستندات الأخرى، ستحتاج إلى استخدام مكتبة Aspose المناسبة.

### هل أحتاج إلى ترخيص لاستخدام Aspose.Words لـ .NET؟

 نعم، Aspose.Words for .NET هو منتج مرخص. يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/) أو ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).