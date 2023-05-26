---
title: إنشاء وإضافة فقرة العقدة
linktitle: إنشاء وإضافة فقرة العقدة
second_title: Aspose.Words لمراجع .NET API
description: قم بإنشاء وإضافة عقدة فقرة إلى مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/working-with-node/create-and-add-paragraph-node/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح شفرة المصدر C # أدناه والتي توضح كيفية إنشاء وإضافة عقدة فقرة باستخدام Aspose.Words for .NET.

## الخطوة 1: استيراد المراجع الضرورية
قبل أن تبدأ ، تأكد من استيراد المراجع الضرورية لاستخدام Aspose.Words for .NET في مشروعك. يتضمن ذلك استيراد مكتبة Aspose.Words وإضافة مساحات الأسماء المطلوبة إلى ملف المصدر الخاص بك.

```csharp
using Aspose.Words;
```

## الخطوة 2: قم بإنشاء مستند جديد
 في هذه الخطوة ، سننشئ مستندًا جديدًا باستخدام امتداد`Document` فصل.

```csharp
Document doc = new Document();
```

## الخطوة 3: قم بإنشاء عقدة فقرة
 الآن سنقوم بإنشاء عقدة فقرة باستخدام امتداد`Paragraph` فئة وتمرير الوثيقة كمعامل.

```csharp
Paragraph para = new Paragraph(doc);
```

## الخطوة 4: الوصول إلى قسم المستند
 لإضافة فقرة إلى المستند ، نحتاج إلى الوصول إلى القسم الأخير من المستند باستخدام ملف`LastSection` ملكية.

```csharp
Section section = doc.LastSection;
```

## الخطوة 5: أضف عقدة الفقرة إلى المستند
 الآن بعد أن أصبح لدينا قسم المستند ، يمكننا إضافة عقدة الفقرة إلى القسم باستخدام ملف`AppendChild` طريقة على القسم`Body` ملكية.

```csharp
section.Body.AppendChild(para);
```

## الخطوة 6: احفظ المستند
 أخيرًا ، لحفظ المستند ، يمكنك استخدام ملف`Save` عن طريق تحديد تنسيق الإخراج المطلوب ، مثل تنسيق DOCX.

```csharp
doc.Save("output.docx", SaveFormat.Docx);
```

### نموذج التعليمات البرمجية المصدر لإنشاء وإضافة فقرة عقدة باستخدام Aspose.Words for .NET

```csharp
Document doc = new Document();

Paragraph para = new Paragraph(doc);

Section section = doc.LastSection;
section.Body.AppendChild(para);

```

هذا مثال رمز كامل لإنشاء وإضافة فقرة باستخدام Aspose.Words for .NET. تأكد من استيراد المراجع الضرورية واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك.