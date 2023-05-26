---
title: تعديل إعداد الصفحة في جميع الأقسام
linktitle: تعديل إعداد الصفحة في جميع الأقسام
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، تعرف على كيفية تعديل إعداد الصفحة في جميع أقسام مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/working-with-section/modify-page-setup-in-all-sections/
---

في هذا البرنامج التعليمي ، سوف نوضح لك كيفية تعديل إعداد الصفحة في جميع أقسام مستند Word باستخدام مكتبة Aspose.Words لـ .NET. يمكن أن يتضمن تغيير إعداد الصفحة إعدادات مثل حجم الورق والهوامش والاتجاه وما إلى ذلك. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
 أولاً ، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بإنشاء مستند وإضافة محتوى وأقسام
بعد ذلك ، سننشئ مستندًا فارغًا عن طريق إنشاء مثيل`Document` فئة وما يرتبط بها`DocumentBuilder` المُنشئ لإضافة محتوى وأقسام إلى المستند. في هذا المثال ، نضيف محتوى وثلاثة أقسام.

```csharp
// قم بإنشاء مستند
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أضف المحتوى والأقسام
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");
```

## الخطوة 3: تحرير إعداد الصفحة في جميع الأقسام
 لتغيير إعداد الصفحة في جميع أقسام المستند ، نستخدم ملف`foreach` حلقة للحلقة خلال كل قسم والوصول إلى ملف`PageSetup` ملكية. في هذا المثال ، نقوم بتغيير حجم الورق لجميع الأقسام عن طريق تعيين القيمة إلى`PaperSize.Letter`.

```csharp
foreach(Section section in doc.Sections)
     section.PageSetup.PaperSize = PaperSize.Letter;
```

### نموذج لشفرة مصدر لتعديل إعداد الصفحة في جميع الأقسام باستخدام Aspose.Words for .NET 

```csharp

// المسار إلى دليل المستند الخاص بك
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

// من المهم أن نفهم أن المستند يمكن أن يحتوي على العديد من الأقسام ،
// ولكل قسم إعداد صفحته. في هذه الحالة ، نريد تعديلها جميعًا.
foreach (Section section in doc)
	section.PageSetup.PaperSize = PaperSize.Letter;
doc.Save(dataDir + "WorkingWithSection.ModifyPageSetupInAllSections.doc");

```

## خاتمة
في هذا البرنامج التعليمي ، رأينا كيفية تعديل إعداد الصفحة في جميع أقسام مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة ، يمكنك الوصول بسهولة إلى كل قسم وتخصيص إعدادات تكوين الصفحة. لا تتردد في تكييف هذه الميزة واستخدامها لتلبية احتياجاتك الخاصة.
