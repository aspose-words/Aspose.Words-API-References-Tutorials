---
title: تعديل إعداد صفحة Word في جميع الأقسام
linktitle: تعديل إعداد صفحة Word في جميع الأقسام
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: في هذا البرنامج التعليمي، تعرف على كيفية تعديل إعداد صفحة الكلمات في كافة أقسام مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-section/modify-page-setup-in-all-sections/
---

سنوضح لك في هذا البرنامج التعليمي كيفية تعديل إعداد صفحة الكلمة في جميع أقسام مستند Word باستخدام مكتبة Aspose.Words لـ .NET. يمكن أن يتضمن تغيير إعداد الصفحة إعدادات مثل حجم الورق والهوامش والاتجاه وما إلى ذلك. سنأخذك خطوة بخطوة لمساعدتك على فهم التعليمات البرمجية وتنفيذها في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C#
- تم تثبيت مكتبة Aspose.Words الخاصة بـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
 أولاً، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مستند وإضافة المحتوى والأقسام
 بعد ذلك، سنقوم بإنشاء مستند فارغ عن طريق إنشاء مثيل لـ`Document` الطبقة وما يرتبط بها`DocumentBuilder` منشئ لإضافة المحتوى والأقسام إلى الوثيقة. في هذا المثال، نقوم بإضافة محتوى وثلاثة أقسام.

```csharp
// قم بإنشاء مستند
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إضافة المحتوى والأقسام
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");
```

## الخطوة 3: تحرير إعداد الصفحة في جميع الأقسام
 لتغيير إعداد الصفحة في كافة أقسام الوثيقة، نستخدم`foreach` حلقة للتكرار خلال كل قسم والوصول إليه`PageSetup` ملكية. في هذا المثال، نقوم بتغيير حجم الورق لجميع الأقسام عن طريق ضبط القيمة على`PaperSize.Letter`.

```csharp
foreach(Section section in doc.Sections)
     section.PageSetup.PaperSize = PaperSize.Letter;
```

### نموذج التعليمات البرمجية المصدر لتعديل إعداد صفحة Word في كافة الأقسام باستخدام Aspose.Words لـ .NET 

```csharp

// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");

// من المهم أن نفهم أن الوثيقة يمكن أن تحتوي على العديد من الأقسام،
// ولكل قسم إعداد صفحته. وفي هذه الحالة، نريد تعديلها جميعًا.
foreach (Section section in doc)
	section.PageSetup.PaperSize = PaperSize.Letter;
doc.Save(dataDir + "WorkingWithSection.ModifyPageSetupInAllSections.doc");

```

## خاتمة
في هذا البرنامج التعليمي، رأينا كيفية تعديل إعداد صفحة الكلمات في جميع أقسام مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة، يمكنك الوصول بسهولة إلى كل قسم وتخصيص إعدادات تكوين الصفحة. لا تتردد في تكييف هذه الميزة واستخدامها لتلبية احتياجاتك الخاصة.

### الأسئلة الشائعة

#### س: كيفية تعيين دليل المستندات في Aspose.Words لـ .NET؟

 ج: لتعيين المسار إلى الدليل الذي يحتوي على مستنداتك، يجب عليك استبداله`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب هيريس كيفية القيام بذلك:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### س: كيفية إنشاء مستند وإضافة محتوى وأقسام في Aspose.Words لـ .NET؟

 ج: لإنشاء مستند فارغ عن طريق إنشاء مثيل لـ`Document` الطبقة وما يرتبط بها`DocumentBuilder` لإضافة محتوى وأقسام إلى المستند، يمكنك استخدام الكود التالي:

```csharp
// قم بإنشاء مستند
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إضافة المحتوى والأقسام
builder. Writen("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder. Writen("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");
```

#### س: كيفية تغيير إعداد الصفحة في كافة الأقسام في Aspose.Words لـ .NET؟

 ج: لتغيير إعداد الصفحة في كافة أقسام المستند، يمكنك استخدام ملف`foreach` حلقة للتكرار خلال كل قسم والوصول إليه`PageSetup` ملكية. في هذا المثال، نقوم بتغيير حجم الورق لجميع الأقسام عن طريق ضبط القيمة على`PaperSize.Letter`.

```csharp
foreach(Section section in doc.Sections)
      section.PageSetup.PaperSize = PaperSize.Letter;
```

#### س: كيف يتم حفظ المستند المعدل في Aspose.Words لـ .NET؟

ج: بمجرد قيامك بتغيير إعداد الصفحة في جميع الأقسام، يمكنك حفظ المستند الذي تم تغييره إلى ملف باستخدام الكود التالي:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```