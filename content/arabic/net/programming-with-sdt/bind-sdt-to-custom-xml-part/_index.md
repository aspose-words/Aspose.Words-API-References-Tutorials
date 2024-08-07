---
title: ربط SDT بجزء Xml المخصص
linktitle: ربط SDT بجزء Xml المخصص
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ربط علامات المستندات المنظمة (SDTs) بأجزاء XML المخصصة في مستندات Word باستخدام Aspose.Words لـ .NET من خلال هذا البرنامج التعليمي خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---
## مقدمة

يمكن أن يؤدي إنشاء مستندات Word ديناميكية تتفاعل مع بيانات XML المخصصة إلى تحسين مرونة تطبيقاتك ووظائفها بشكل كبير. يوفر Aspose.Words for .NET ميزات قوية لربط علامات المستندات المنظمة (SDTs) بأجزاء XML المخصصة، مما يسمح لك بإنشاء مستندات تعرض البيانات ديناميكيًا. في هذا البرنامج التعليمي، سنرشدك خلال عملية ربط SDT بجزء XML مخصص خطوة بخطوة. دعونا الغوص في!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Words for .NET: يمكنك تنزيل أحدث إصدار من[Aspose.Words لإصدارات .NET](https://releases.aspose.com/words/net/).
- بيئة التطوير: Visual Studio أو أي برنامج .NET IDE آخر متوافق.
- الفهم الأساسي لـ C#: الإلمام بلغة البرمجة C# وإطار عمل .NET.

## استيراد مساحات الأسماء

لاستخدام Aspose.Words لـ .NET بشكل فعال، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروعك. أضف ما يلي باستخدام التوجيهات في الجزء العلوي من ملف التعليمات البرمجية الخاص بك:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Saving;
```

دعونا نقسم العملية إلى خطوات يمكن التحكم فيها لتسهيل متابعتها. ستغطي كل خطوة جزءًا محددًا من المهمة.

## الخطوة 1: تهيئة المستند

أولاً، تحتاج إلى إنشاء مستند جديد وإعداد البيئة.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

// تهيئة مستند جديد
Document doc = new Document();
```

في هذه الخطوة، نقوم بتهيئة مستند جديد سيحتوي على بيانات XML المخصصة لدينا وSDT.

## الخطوة 2: إضافة جزء XML مخصص

بعد ذلك، نقوم بإضافة جزء XML مخصص إلى المستند. سيحتوي هذا الجزء على بيانات XML التي نريد ربطها بالمعاملة الخاصة والتفضيلية (SDT).

```csharp
// قم بإضافة جزء XML مخصص إلى المستند
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

هنا، نقوم بإنشاء جزء XML مخصص جديد بمعرف فريد ونضيف بعض نماذج بيانات XML.

## الخطوة 3: إنشاء علامة مستند منظم (SDT)

بعد إضافة جزء XML المخصص، نقوم بإنشاء SDT لعرض بيانات XML.

```csharp
// إنشاء علامة مستند منظمة (SDT)
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

نقوم بإنشاء SDT من النوع PlainText وإلحاقه بالقسم الأول من نص المستند.

## الخطوة 4: ربط SDT بجزء XML المخصص

الآن، نقوم بربط SDT بجزء XML المخصص باستخدام تعبير XPath.

```csharp
// قم بربط SDT بجزء XML المخصص
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

 تقوم هذه الخطوة بتعيين المعاملة الخاصة والتفضيلية إلى`<text>` عنصر داخل`<root>` عقدة جزء XML المخصص لدينا.

## الخطوة 5: احفظ المستند

وأخيرًا، نقوم بحفظ المستند في الدليل المحدد.

```csharp
// احفظ المستند
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

يحفظ هذا الأمر المستند مع SDT المنضم إلى الدليل المخصص لك.

## خاتمة

تهانينا! لقد نجحت في ربط SDT بجزء XML مخصص باستخدام Aspose.Words لـ .NET. تتيح لك هذه الميزة القوية إنشاء مستندات ديناميكية يمكن تحديثها بسهولة ببيانات جديدة بمجرد تعديل محتوى XML. سواء كنت تقوم بإنشاء تقارير، أو إنشاء قوالب، أو أتمتة سير عمل المستندات، فإن Aspose.Words for .NET يوفر الأدوات التي تحتاجها لجعل مهامك أسهل وأكثر كفاءة.

## الأسئلة الشائعة

### ما هي علامة الوثيقة المنظمة (SDT)؟
تعد علامة المستند المنظمة (SDT) عنصرًا للتحكم في المحتوى في مستندات Word والتي يمكن استخدامها لربط البيانات الديناميكية، مما يجعل المستندات تفاعلية ومعتمدة على البيانات.

### هل يمكنني ربط عدة SDTs بأجزاء XML مختلفة في مستند واحد؟
نعم، يمكنك ربط عدة SDTs بأجزاء XML مختلفة في نفس المستند، مما يسمح باستخدام قوالب معقدة تعتمد على البيانات.

### كيف أقوم بتحديث بيانات XML في جزء XML المخصص؟
 يمكنك تحديث بيانات XML عن طريق الوصول إلى`CustomXmlPart` الكائن وتعديل محتوى XML الخاص به مباشرة.

### هل من الممكن ربط SDTs بسمات XML بدلاً من العناصر؟
نعم، يمكنك ربط SDTs بسمات XML عن طريق تحديد تعبير XPath المناسب الذي يستهدف السمة المطلوبة.

### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Words لـ .NET؟
 يمكنك العثور على وثائق شاملة حول Aspose.Words لـ .NET على الموقع[Aspose.توثيق الكلمات](https://reference.aspose.com/words/net/).