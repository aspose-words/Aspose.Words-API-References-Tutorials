---
title: السماح فقط لحقول النموذج بالحماية
linktitle: السماح فقط لحقول النموذج بالحماية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام Aspose.Words for .NET لحماية المستندات والسماح فقط بتحرير حقول النموذج.
type: docs
weight: 10
url: /tr/net/document-protection/allow-only-form-fields-protect/
---

تعد حماية المستندات ميزة أساسية عند العمل مع الملفات داخل تطبيق C # الخاص بك. باستخدام مكتبة Aspose.Words لـ .NET ، يمكنك حماية مستنداتك بسهولة والسماح فقط بتحرير حقول النموذج. في هذا الدليل المفصل خطوة بخطوة ، سنرشدك إلى كيفية استخدام الكود المصدري C # للسماح فقط بتحرير حقول النموذج باستخدام ميزة Allow Only Form Fields Protect في Aspose.Words for .NET.

## الخطوة 1: إعداد دليل المستندات

الخطوة الأولى هي تحديد دليل المستند الخاص بك. يجب عليك تحديد المسار حيث تريد حفظ المستند المحمي. على سبيل المثال :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

تأكد من استبدال "دليل المستندات" بالمسار الفعلي إلى دليل المستندات.

## الخطوة الثانية: إدخال الأقسام والنص

بعد ذلك ، تحتاج إلى إدراج أقسام ونص في المستند. استخدم فئة DocumentBuilder المقدمة من Aspose.Words لبناء محتوى وثيقتك. اليك مثال بسيط:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

في هذا المثال ، نقوم بإنشاء مستند فارغ جديد ثم نستخدم DocumentBuilder لإضافة سطر من النص.

## الخطوة 3: تمكين حماية المستند

 تعمل حماية المستندات فقط عند تمكين حماية المستندات. يمكنك تمكين حماية المستندات باستخدام`Protect` طريقة فئة المستند. إليك الطريقة:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

في هذا المثال ، نقوم بتمكين حماية المستندات من خلال تحديد نوع الحماية `

AllowOnlyFormFields` وتعيين كلمة مرور.

## الخطوة 4: السماح فقط بحقول النموذج

الآن بعد أن تم تمكين حماية المستندات ، نحتاج إلى تحديد السماح فقط بتحرير حقول النموذج. هذا يضمن أن المستخدمين يمكنهم فقط تحرير أجزاء من المستند تمثل حقول نموذج. إليك الطريقة:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

تأكد من استبدال "كلمة المرور" بكلمة المرور التي قمت بتعيينها مسبقًا.

## الخطوة 5: حفظ المستند المحمي

أخيرًا ، يمكنك حفظ المستند المحمي باستخدام امتداد`Save` طريقة فئة المستند. حدد مسار الملف الكامل واسم الملف المطلوب. على سبيل المثال :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

تأكد من استبدال "dataDir" بالمسار إلى دليل المستند.

### مثال على شفرة المصدر لميزة Allow Only Form Fields Protect باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

// أدخل قسمين مع بعض النص.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// لا تعمل حماية المستند إلا عند تشغيل حماية المستند ولا يُسمح إلا بالتحرير في حقول النموذج.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// احفظ المستند المحمي.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## خاتمة

في هذا الدليل ، اكتشفنا كيفية استخدام مكتبة Aspose.Words لـ .NET لحماية مستند والسماح فقط بتحرير حقول النموذج. باتباع الخطوات المقدمة ، يمكنك بسهولة تنفيذ هذه الوظيفة في تطبيق C # الخاص بك. تعد حماية المستندات أمرًا ضروريًا لضمان أمان وسرية مستنداتك.
