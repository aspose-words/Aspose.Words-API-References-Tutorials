---
title: قسم غير مقيد في مستند Word
linktitle: قسم غير مقيد في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تحديد الأقسام غير المقيدة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-protection/unrestricted-section/
---
في هذا البرنامج التعليمي ، سنوجهك خلال الخطوات لاستخدام ميزة القسم غير المقيد في Aspose.Words for .NET. تتيح لك هذه الميزة تحديد أقسام معينة في مستند Word غير محمية ، حتى إذا كان باقي المستند محميًا. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند والأقسام

ابدأ بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أضف محتوى إلى المستند
استخدم كائن DocumentBuilder لإضافة محتوى إلى المستند وإدراج فواصل المقاطع:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## الخطوة 3: حماية المستند والأقسام

تعمل حماية القسم فقط عندما يتم تمكين حماية المستند ولا يُسمح إلا بالتحرير في حقول النموذج. يمكنك حماية المستند باستخدام طريقة Protect () الخاصة بكائن المستند:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

تأكد من تحديد نوع الحماية الصحيح وتعيين كلمة المرور المطلوبة.

## الخطوة 4: تعطيل الحماية لقسم معين

بشكل افتراضي ، تكون جميع الأقسام محمية ، ولكن يمكنك تعطيل الحماية بشكل انتقائي لقسم معين باستخدام خاصية ProtectedForForms الخاصة بكائن القسم:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

في هذا المثال ، تم تعطيل الحماية للقسم الأول.

## الخطوة 5: احفظ المستند

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند بأقسام غير مقيدة.

### مثال على شفرة المصدر للقسم غير المقيد باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل للقسم غير المقيد باستخدام Aspose.Words for .NET:


```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// أدخل قسمين مع بعض النص.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// تعمل حماية القسم فقط عندما يتم تشغيل حماية المستند ولا يُسمح إلا بالتحرير في حقول النموذج.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//بشكل افتراضي ، تكون جميع الأقسام محمية ، ولكن يمكننا إيقاف الحماية بشكل انتقائي.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

باتباع هذه الخطوات ، ستتمكن بسهولة من تحديد الأقسام غير المقيدة في مستند Word الخاص بك باستخدام Aspose.Words for .NET.

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا ميزة القسم غير المقيد في Aspose.Words for .NET ، والتي تسمح لأقسام معينة في مستند Word بأن تظل غير محمية بينما تتم حماية بقية المستند. باتباع الخطوات المقدمة ، يمكنك بسهولة تحديد أقسام داخل المستند الخاص بك حيث يمكن للمستخدمين تحرير المحتوى بحرية مع الحفاظ على الحماية للأقسام الأخرى. يوفر Aspose.Words for .NET إمكانات قوية لحماية المستندات وتخصيصها ، مما يمنحك التحكم في أذونات التحرير في مستندات Word الخاصة بك.

### الأسئلة الشائعة للقسم غير المقيد في مستند Word

#### س: ما هي الأقسام غير المقيدة في Aspose.Words for .NET؟

ج: الأقسام غير المقيدة في Aspose.Words for .NET هي أقسام محددة في مستند Word غير محمية ، حتى لو كان باقي المستند محميًا. تسمح هذه الأقسام للمستخدمين بتعديل المحتوى بداخلها مع الحفاظ على الحماية للأجزاء المتبقية من المستند.

#### س: كيف يمكنني إنشاء أقسام غير مقيدة باستخدام Aspose.Words for .NET؟

ج: لإنشاء أقسام غير مقيدة في مستند Word باستخدام Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:
1.  قم بإنشاء مثيل لـ`Document` فئة وأ`DocumentBuilder` هدف.
2.  استخدم ال`DocumentBuilder` لإضافة محتوى إلى المستند وإدراج فواصل المقاطع.
3.  قم بحماية المستند باستخدام`Protect` طريقة`Document` كائن ، مع تحديد نوع الحماية المطلوب وكلمة المرور.
4.  قم بتعطيل الحماية لقسم معين عن طريق تعيين`ProtectedForForms` الممتلكات المقابلة`Section` يعترض على`false`.
5. احفظ المستند المعدل.

#### س: هل يمكنني الحصول على عدة أقسام غير مقيدة داخل مستند Word؟

 ج: نعم ، يمكن أن يكون لديك عدة أقسام غير مقيدة داخل مستند Word. عن طريق تعطيل الحماية بشكل انتقائي لأقسام محددة باستخدام`ProtectedForForms` ممتلكات`Section`كائن ، يمكنك تحديد أقسام متعددة حيث يمكن للمستخدمين تعديل المحتوى بحرية مع الحفاظ على الأقسام الأخرى محمية.

#### س 4. هل يمكنني إزالة الحماية من قسم كان محميًا في البداية؟
 نعم ، يمكنك إزالة الحماية من قسم كان محميًا في البداية عن طريق تعيين`ProtectedForForms` الممتلكات المقابلة`Section` يعترض على`false`. يتيح ذلك للمستخدمين تحرير المحتوى داخل هذا القسم المحدد دون أي قيود.

#### س: ما أنواع الحماية التي يمكن تطبيقها على مستند Word؟

ج: يوفر Aspose.Words for .NET أنواع حماية متنوعة يمكن تطبيقها على مستند Word ، بما في ذلك:
- NoProtection: لا توجد حماية.
- AllowOnlyRevisions: يمكن للمستخدمين فقط إجراء مراجعات على المستند.
- AllowOnlyComments: يمكن للمستخدمين إضافة تعليقات فقط إلى المستند.
- AllowOnlyFormFields: يمكن للمستخدمين فقط تحرير حقول النموذج في المستند.
- للقراءة فقط: المستند للقراءة فقط ، ولا يُسمح بالتحرير.


