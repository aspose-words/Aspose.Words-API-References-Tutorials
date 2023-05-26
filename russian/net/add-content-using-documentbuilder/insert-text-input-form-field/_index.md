---
title: أدخل حقل نموذج إدخال النص
linktitle: أدخل حقل نموذج إدخال النص
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام Aspose.Words for .NET لإدراج حقل نموذج إدخال النص في مستندات Word باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/insert-text-input-form-field/
---

في هذا الدليل المفصل خطوة بخطوة ، سنستكشف كيفية استخدام ميزة إدراج حقل نموذج إدخال نص في Aspose.Words for .NET لإضافة حقول نموذج إدخال النص ومعالجتها في مستندات Word باستخدام كود مصدر C #. تسمح حقول نموذج إدخال النص للمستخدمين بإدخال نص مخصص داخل المستند ، مما يجعلها مثالية لإنشاء نماذج واستبيانات تفاعلية. باتباع الإرشادات أدناه ، ستتمكن من إدراج حقول نموذج إدخال النص وتخصيصها بسهولة في مستنداتك. هيا بنا نبدأ!

## مقدمة عن ميزة "إدراج حقل نموذج إدخال النص" في Aspose.Words for .NET

تتيح لك ميزة "إدراج حقل نموذج إدخال النص" في Aspose.Words for .NET إضافة حقول نموذج إدخال نص برمجيًا إلى مستندات Word الخاصة بك. توفر حقول النموذج هذه عنصرًا تفاعليًا حيث يمكن للمستخدمين إدخال نص أو بيانات مخصصة.

## فهم متطلبات استخدام الميزة

قبل متابعة التنفيذ ، تأكد من استيفاء المتطلبات التالية:

1. تم تثبيت Aspose.Words for .NET library في مشروعك.
2. المعرفة الأساسية بلغة البرمجة C #.
3. مستند Word موجود أو مستند جديد لإدراج حقل نموذج إدخال النص.

تأكد من توفر هذه المتطلبات الأساسية للمضي قدمًا بسلاسة.

## دليل تفصيلي خطوة بخطوة لتنفيذ إدراج حقل نموذج إدخال نص باستخدام كود مصدر C #

اتبع الخطوات أدناه لتنفيذ ميزة إدراج حقل نموذج إدخال النص باستخدام كود مصدر C # المقدم:

### الخطوة 1: تهيئة مستند إنشاء المستندات

للبدء ، قم بتهيئة المستند ومنشئ المستندات. يُعد منشئ المستندات أداة قوية توفرها Aspose.Words for .NET والتي تتيح لنا إنشاء مستندات Word ومعالجتها برمجيًا. استخدم مقتطف الشفرة التالي:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### الخطوة 2: إدخال حقل نموذج إدخال النص

 بعد ذلك ، سنقوم بإدخال حقل نموذج إدخال النص في المستند باستخدام الامتداد`InsertTextInput` طريقة. تقبل هذه الطريقة معلمات مختلفة ، بما في ذلك اسم حقل النموذج ونوع حقل النموذج (في هذه الحالة ،`TextFormFieldType.Regular`والقيمة الافتراضية والحد الأقصى للطول. هذا مثال:

```csharp
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);
```

سوف يقوم الكود أعلاه بإدراج حقل نموذج إدخال نص بالاسم "TextInput" ، والقيمة الافتراضية "Hello" ، ولا يوجد حد أقصى للطول.

### الخطوة 3: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

سيحفظ هذا الرمز المستند مع حقل نموذج إدخال النص المدرج في الموقع المحدد.

### مثال على شفرة المصدر لإدراج حقل نموذج إدخال نص باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);

	doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
            
        
```
