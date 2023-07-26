---
title: مناطق قابلة للتحرير غير مقيدة في مستند Word
linktitle: مناطق قابلة للتحرير غير مقيدة في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إنشاء مناطق قابلة للتحرير غير مقيدة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-protection/unrestricted-editable-regions/
---
في هذا البرنامج التعليمي ، سنوجهك خلال الخطوات لاستخدام ميزة المناطق غير المقيدة القابلة للتحرير في Aspose.Words for .NET. تتيح لك هذه الميزة تحديد مناطق في مستند Word حيث يمكن تحرير المحتوى بدون قيود ، حتى إذا كان باقي المستند للقراءة فقط. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند وإعداد الحماية

ابدأ بتحميل المستند الحالي:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

حماية المستند عن طريق تعيين نوع الحماية للقراءة فقط وكلمة المرور

## الخطوة الثانية: إنشاء منطقة قابلة للتعديل

ابدأ بإنشاء منطقة قابلة للتحرير باستخدام كائنات EditableRangeStart و EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// تم إنشاء كائن EditableRange من أجل EditableRangeStart الذي قمنا به للتو.
EditableRange editableRange = edRangeStart.EditableRange;

// ضع شيئًا ما داخل النطاق القابل للتعديل.
builder.Writeln("Paragraph inside first editable range");

// يتم تشكيل النطاق القابل للتحرير بشكل جيد إذا كان له بداية ونهاية.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## الخطوة 3: أضف محتوى خارج المناطق القابلة للتحرير

يمكنك إضافة محتوى خارج المناطق القابلة للتحرير ، والتي ستبقى للقراءة فقط:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## الخطوة 4: احفظ المستند

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند بالمناطق القابلة للتحرير.

### مثال على شفرة المصدر للمناطق غير المقيدة القابلة للتحرير باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل للمناطق القابلة للتحرير غير المقيدة باستخدام Aspose.Words for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل مستند وجعله للقراءة فقط.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// ابدأ نطاقًا قابلًا للتحرير.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// تم إنشاء كائن EditableRange من أجل EditableRangeStart الذي قمنا به للتو.
EditableRange editableRange = edRangeStart.EditableRange;

// ضع شيئًا ما داخل النطاق القابل للتعديل.
builder.Writeln("Paragraph inside first editable range");

// يتم تشكيل النطاق القابل للتحرير بشكل جيد إذا كان له بداية ونهاية.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
باتباع هذه الخطوات ، يمكنك بسهولة إنشاء مناطق قابلة للتحرير غير مقيدة في مستند Word الخاص بك باستخدام Aspose.Words for .NET.

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية إنشاء مناطق قابلة للتحرير غير مقيدة في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المتوفرة ، يمكنك تحديد مناطق معينة داخل المستند حيث يمكن للمستخدمين تحرير المحتوى بحرية مع الاحتفاظ ببقية المستند للقراءة فقط. يوفر Aspose.Words for .NET ميزات قوية لحماية المستندات وتخصيصها ، مما يوفر لك التحكم في إمكانات التحرير لمستندات Word الخاصة بك.

### الأسئلة الشائعة للمناطق القابلة للتحرير غير المقيدة في مستند Word

#### س: ما هي المناطق القابلة للتحرير غير المقيدة في Aspose.Words for .NET؟

ج: المناطق القابلة للتحرير غير المقيدة في Aspose.Words for .NET هي مناطق داخل مستند Word حيث يمكن تحرير المحتوى دون أي قيود ، حتى إذا تم تعيين باقي المستند للقراءة فقط. توفر هذه المناطق طريقة لتعريف أجزاء معينة من المستند يمكن للمستخدمين تعديلها مع الحفاظ على الحماية الشاملة للمستند.

#### س: كيف يمكنني إنشاء مناطق قابلة للتحرير غير مقيدة باستخدام Aspose.Words for .NET؟

ج: لإنشاء مناطق قابلة للتحرير غير مقيدة في مستند Word باستخدام Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:
1.  قم بتحميل المستند الحالي باستخدام ملف`Document` فصل.
2.  اضبط حماية المستند على للقراءة فقط باستخدام ملف`Protect` طريقة`Document` هدف.
3.  استخدم ال`DocumentBuilder` class لإنشاء نطاق قابل للتحرير عن طريق إضافة`EditableRangeStart` كائن و`EditableRangeEnd` هدف.
4.  أضف محتوى داخل النطاق القابل للتحرير باستخدام امتداد`DocumentBuilder`.
5.  احفظ المستند المعدل باستخدام ملف`Save` طريقة`Document` هدف.

#### س: هل يمكنني الحصول على عدة مناطق قابلة للتحرير غير مقيدة في مستند Word؟

ج: نعم ، يمكن أن يكون لديك عدة مناطق قابلة للتحرير غير مقيدة في مستند Word. لتحقيق ذلك ، يمكنك إنشاء مجموعات متعددة من`EditableRangeStart` و`EditableRangeEnd` كائنات باستخدام`DocumentBuilder` فصل. ستحدد كل مجموعة من الكائنات منطقة منفصلة قابلة للتحرير حيث يمكن للمستخدمين تعديل المحتوى دون أي قيود.

#### س: هل يمكنني تداخل المناطق القابلة للتعديل داخل بعضها البعض؟

 ج: لا ، لا يمكنك إجراء تداخل بين المناطق القابلة للتعديل داخل بعضها باستخدام Aspose.Words for .NET. يتم تحديد كل منطقة قابلة للتحرير بواسطة ملف`EditableRangeStart` و`EditableRangeEnd` يجب أن يكون الزوج مستقلاً ولا يتداخل أو يتداخل في منطقة أخرى قابلة للتحرير. المناطق المتداخلة القابلة للتحرير غير مدعومة.

#### س: هل يمكنني إزالة الحماية للقراءة فقط من المستند داخل منطقة قابلة للتحرير؟

ج: لا ، لا يمكنك إزالة الحماية للقراءة فقط من المستند داخل منطقة قابلة للتحرير. يتم تطبيق الحماية للقراءة فقط على المستند بأكمله ، ولا يمكن إزالته بشكل انتقائي داخل مناطق محددة قابلة للتحرير. الغرض من المناطق القابلة للتحرير هو السماح بتعديل المحتوى مع الاحتفاظ بالمستند الكلي للقراءة فقط.