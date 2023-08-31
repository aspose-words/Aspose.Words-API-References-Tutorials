---
title: مناطق غير مقيدة قابلة للتحرير في مستند Word
linktitle: مناطق غير مقيدة قابلة للتحرير في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء مناطق غير مقيدة قابلة للتحرير في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-protection/unrestricted-editable-regions/
---
في هذا البرنامج التعليمي، سنرشدك خلال خطوات استخدام ميزة المناطق القابلة للتحرير غير المقيدة في Aspose.Words for .NET. تتيح لك هذه الميزة تحديد المناطق في مستند Word حيث يمكن تحرير المحتوى دون قيود، حتى لو كان باقي المستند للقراءة فقط. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند وإعداد الحماية

ابدأ بتحميل المستند الموجود:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

قم بحماية المستند عن طريق تعيين نوع الحماية للقراءة فقط وكلمة المرور

## الخطوة 2: إنشاء منطقة قابلة للتحرير

ابدأ بإنشاء منطقة قابلة للتحرير باستخدام كائني EditableRangeStart وEditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// يتم إنشاء كائن EditableRange لـ EditableRangeStart الذي قمنا بإنشائه للتو.
EditableRange editableRange = edRangeStart.EditableRange;

// ضع شيئًا داخل النطاق القابل للتحرير.
builder.Writeln("Paragraph inside first editable range");

// يتم تشكيل النطاق القابل للتحرير بشكل جيد إذا كان له بداية ونهاية.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## الخطوة 3: إضافة محتوى خارج المناطق القابلة للتحرير

يمكنك إضافة محتوى خارج المناطق القابلة للتحرير، والتي ستظل للقراءة فقط:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## الخطوة 4: احفظ المستند

وأخيرا، احفظ الوثيقة المعدلة:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند بمساحات قابلة للتحرير.

### مثال على التعليمات البرمجية المصدر للمناطق غير المقيدة القابلة للتحرير باستخدام Aspose.Words لـ .NET

فيما يلي كود المصدر الكامل للمناطق غير المقيدة القابلة للتحرير باستخدام Aspose.Words for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بتحميل مستند وجعله للقراءة فقط.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// ابدأ نطاقًا قابلاً للتحرير.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// يتم إنشاء كائن EditableRange لـ EditableRangeStart الذي قمنا بإنشائه للتو.
EditableRange editableRange = edRangeStart.EditableRange;

// ضع شيئًا داخل النطاق القابل للتحرير.
builder.Writeln("Paragraph inside first editable range");

// يتم تشكيل النطاق القابل للتحرير بشكل جيد إذا كان له بداية ونهاية.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
باتباع هذه الخطوات، يمكنك بسهولة إنشاء مناطق غير مقيدة قابلة للتحرير في مستند Word الخاص بك باستخدام Aspose.Words for .NET.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء مناطق غير مقيدة قابلة للتحرير في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المتوفرة، يمكنك تحديد مناطق محددة داخل المستند حيث يمكن للمستخدمين تحرير المحتوى بحرية مع الاحتفاظ ببقية المستند للقراءة فقط. يوفر Aspose.Words for .NET ميزات قوية لحماية المستندات وتخصيصها، مما يوفر لك التحكم في إمكانيات التحرير لمستندات Word الخاصة بك.

### الأسئلة الشائعة للمناطق غير المقيدة القابلة للتحرير في مستند Word

#### س: ما هي المناطق غير المقيدة القابلة للتحرير في Aspose.Words لـ .NET؟

ج: المناطق غير المقيدة القابلة للتحرير في Aspose.Words لـ .NET هي مناطق داخل مستند Word حيث يمكن تحرير المحتوى دون أي قيود، حتى لو تم تعيين بقية المستند للقراءة فقط. توفر هذه المناطق طريقة لتحديد أجزاء معينة من المستند والتي يمكن للمستخدمين تعديلها مع الحفاظ على الحماية الشاملة للمستند.

#### س: كيف يمكنني إنشاء مناطق غير مقيدة قابلة للتحرير باستخدام Aspose.Words for .NET؟

ج: لإنشاء مناطق غير مقيدة قابلة للتحرير في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:
1.  قم بتحميل المستند الموجود باستخدام`Document` فصل.
2.  اضبط حماية المستند على القراءة فقط باستخدام`Protect` طريقة`Document` هدف.
3.  استخدم ال`DocumentBuilder` فئة لإنشاء نطاق قابل للتحرير عن طريق إضافة`EditableRangeStart` كائن و`EditableRangeEnd` هدف.
4.  أضف محتوى ضمن النطاق القابل للتحرير باستخدام`DocumentBuilder`.
5.  احفظ المستند المعدل باستخدام`Save` طريقة`Document` هدف.

#### س: هل يمكنني الحصول على مناطق متعددة غير مقيدة قابلة للتحرير في مستند Word؟

ج: نعم، يمكن أن يكون لديك مناطق متعددة غير مقيدة قابلة للتحرير في مستند Word. لتحقيق ذلك، يمكنك إنشاء مجموعات متعددة من`EditableRangeStart` و`EditableRangeEnd` الكائنات باستخدام`DocumentBuilder` فصل. ستحدد كل مجموعة من الكائنات منطقة منفصلة قابلة للتحرير حيث يمكن للمستخدمين تعديل المحتوى دون أي قيود.

#### س: هل يمكنني دمج المناطق القابلة للتحرير داخل بعضها البعض؟

 ج: لا، لا يمكنك دمج المناطق القابلة للتحرير داخل بعضها البعض باستخدام Aspose.Words لـ .NET. كل منطقة قابلة للتحرير محددة بواسطة`EditableRangeStart` و`EditableRangeEnd` يجب أن يكون الزوج مستقلاً وغير متداخل أو متداخل في منطقة أخرى قابلة للتحرير. المناطق المتداخلة القابلة للتحرير غير مدعومة.

#### س: هل يمكنني إزالة الحماية للقراءة فقط من المستند داخل منطقة قابلة للتحرير؟

ج: لا، لا يمكنك إزالة الحماية للقراءة فقط من المستند داخل منطقة قابلة للتحرير. يتم تطبيق حماية القراءة فقط على المستند بأكمله، ولا يمكن إزالتها بشكل انتقائي داخل مناطق محددة قابلة للتحرير. الغرض من المناطق القابلة للتحرير هو السماح بتعديل المحتوى مع الاحتفاظ بالمستند الإجمالي للقراءة فقط.