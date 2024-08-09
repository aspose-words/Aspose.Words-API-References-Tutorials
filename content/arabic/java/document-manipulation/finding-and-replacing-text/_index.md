---
title: البحث عن النص واستبداله في Aspose.Words لـ Java
linktitle: البحث عن النص واستبداله
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية البحث عن النص واستبداله في مستندات Word باستخدام Aspose.Words for Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية. عزز مهاراتك في التعامل مع مستندات Java.
type: docs
weight: 15
url: /ar/java/document-manipulation/finding-and-replacing-text/
---

## مقدمة للبحث عن النص واستبداله في Aspose.Words لـ Java

Aspose.Words for Java عبارة عن واجهة برمجة تطبيقات Java قوية تتيح لك العمل مع مستندات Word برمجيًا. إحدى المهام الشائعة عند التعامل مع مستندات Word هي البحث عن النص واستبداله. سواء كنت بحاجة إلى تحديث العناصر النائبة في القوالب أو إجراء عمليات معالجة نصية أكثر تعقيدًا، يمكن أن يساعدك Aspose.Words for Java على تحقيق أهدافك بكفاءة.

## المتطلبات الأساسية

قبل أن نتعمق في تفاصيل البحث عن النص واستبداله، تأكد من توفر المتطلبات الأساسية التالية:

- بيئة تطوير جافا
- Aspose.Words لمكتبة جافا
- نموذج مستند Word للعمل معه

 يمكنك تنزيل مكتبة Aspose.Words for Java من[هنا](https://releases.aspose.com/words/java/).

## البحث عن نص بسيط واستبداله

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// إنشاء منشئ المستندات
DocumentBuilder builder = new DocumentBuilder(doc);

// البحث عن النص واستبداله
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

 في هذا المثال، نقوم بتحميل مستند Word، وإنشاء ملف`DocumentBuilder` ، واستخدم`replace` طريقة للعثور على "النص القديم" واستبداله بـ "النص الجديد" داخل المستند.

## استخدام التعبيرات العادية

توفر التعبيرات العادية إمكانات قوية لمطابقة الأنماط للبحث عن النص واستبداله. يدعم Aspose.Words for Java التعبيرات العادية لعمليات البحث والاستبدال الأكثر تقدمًا.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// إنشاء منشئ المستندات
DocumentBuilder builder = new DocumentBuilder(doc);

// استخدم التعبيرات العادية للبحث عن النص واستبداله
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

في هذا المثال، نستخدم نمط التعبير العادي للبحث عن النص واستبداله داخل المستند.

## تجاهل النص داخل الحقول

يمكنك تكوين Aspose.Words لتجاهل النص الموجود داخل الحقول عند إجراء عمليات البحث والاستبدال.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// قم بإنشاء مثيل FindReplaceOptions وقم بتعيين IgnoreFields على true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// استخدم الخيارات عند استبدال النص
doc.getRange().replace("text-to-replace", "new-text", options);

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

يكون هذا مفيدًا عندما تريد استبعاد النص الموجود داخل الحقول، مثل حقول الدمج، من الاستبدال.

## تجاهل النص داخل حذف المراجعات

يمكنك تكوين Aspose.Words لتجاهل النص الموجود داخل حذف المراجعات أثناء عمليات البحث والاستبدال.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// قم بإنشاء مثيل FindReplaceOptions وقم بتعيين IgnoreDeleted على true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// استخدم الخيارات عند استبدال النص
doc.getRange().replace("text-to-replace", "new-text", options);

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

يسمح لك هذا باستبعاد النص الذي تم وضع علامة عليه للحذف في التغييرات المتعقبة من الاستبدال.

## تجاهل النص داخل إدراج المراجعات

يمكنك تكوين Aspose.Words لتجاهل النص الموجود داخل مراجعات الإدراج أثناء عمليات البحث والاستبدال.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// قم بإنشاء مثيل FindReplaceOptions وقم بتعيين IgnoreInserted على true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// استخدم الخيارات عند استبدال النص
doc.getRange().replace("text-to-replace", "new-text", options);

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

يتيح لك هذا استبعاد النص الذي تم وضع علامة عليه كمدرج في التغييرات المتعقبة من الاستبدال.

## استبدال النص بـ HTML

يمكنك استخدام Aspose.Words for Java لاستبدال النص بمحتوى HTML.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// قم بإنشاء مثيل FindReplaceOptions مع رد اتصال استبدال مخصص
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// استخدم الخيارات عند استبدال النص
doc.getRange().replace("text-to-replace", "new-html-content", options);

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

 في هذا المثال، نستخدم العرف`ReplaceWithHtmlEvaluator` لاستبدال النص بمحتوى HTML.

## استبدال النص في الرؤوس والتذييلات

يمكنك البحث عن النص واستبداله داخل الرؤوس والتذييلات لمستند Word الخاص بك.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// احصل على مجموعة الرؤوس والتذييلات
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// اختر نوع الرأس أو التذييل الذي تريد استبدال النص فيه (على سبيل المثال، HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// قم بإنشاء مثيل FindReplaceOptions وقم بتطبيقه على نطاق التذييل
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

يسمح لك هذا بإجراء عمليات استبدال النص على وجه التحديد في الرؤوس والتذييلات.

## عرض التغييرات لأوامر الرأس والتذييل

يمكنك استخدام Aspose.Words لإظهار التغييرات الخاصة بأوامر الرؤوس والتذييلات في مستندك.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// الحصول على القسم الأول
Section firstPageSection = doc.getFirstSection();

// قم بإنشاء مثيل FindReplaceOptions وقم بتطبيقه على نطاق المستند
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//استبدال النص الذي يؤثر على أوامر الرأس والتذييل
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

يتيح لك ذلك تصور التغييرات المتعلقة بأوامر الرأس والتذييل في مستندك.

## استبدال النص بالحقول

يمكنك استبدال النص بالحقول باستخدام Aspose.Words for Java.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// قم بإنشاء مثيل FindReplaceOptions وقم بتعيين رد اتصال استبدال مخصص للحقول
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// استخدم الخيارات عند استبدال النص
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

 في هذا المثال، نستبدل النص بالحقول ونحدد نوع الحقل (على سبيل المثال،`FieldType.FIELD_MERGE_FIELD`).

## الاستبدال بمقيم

يمكنك استخدام مقيم مخصص لتحديد النص البديل ديناميكيًا.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// قم بإنشاء مثيل FindReplaceOptions وقم بتعيين رد اتصال استبدال مخصص
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// استخدم الخيارات عند استبدال النص
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

في هذا المثال، نستخدم مقيمًا مخصصًا (`MyReplaceEvaluator`) لاستبدال النص.

## الاستبدال بـ Regex

يتيح لك Aspose.Words for Java استبدال النص باستخدام التعبيرات العادية.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// استخدم التعبيرات العادية للبحث عن النص واستبداله
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

في هذا المثال، نستخدم نمط التعبير العادي للبحث عن النص واستبداله داخل المستند.

## التعرف على البدائل ضمن أنماط الاستبدال

يمكنك التعرف على البدائل وإجراء البدائل ضمن أنماط الاستبدال باستخدام Aspose.Words for Java.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

//قم بإنشاء مثيل FindReplaceOptions مع ضبط UseSubstitutions على true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// استخدم الخيارات عند استبدال النص بنمط
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

يتيح لك هذا إجراء عمليات الاستبدال ضمن أنماط الاستبدال لعمليات الاستبدال الأكثر تقدمًا.

## الاستبدال بسلسلة

يمكنك استبدال النص بسلسلة بسيطة باستخدام Aspose.Words لـ Java.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// استبدل النص بسلسلة
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

في هذا المثال، نستبدل "النص المراد استبداله" بـ "سلسلة جديدة" داخل المستند.

## استخدام النظام القديم

يمكنك استخدام الترتيب القديم عند إجراء عمليات البحث والاستبدال.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// قم بإنشاء مثيل FindReplaceOptions وقم بتعيين UseLegacyOrder على القيمة true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// استخدم الخيارات عند استبدال النص
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

يتيح لك هذا استخدام الترتيب القديم لعمليات البحث والاستبدال.

## استبدال النص في الجدول

يمكنك البحث عن النص واستبداله داخل الجداول في مستند Word الخاص بك.

```java
// قم بتحميل المستند
Document doc = new Document("your-document.docx");

// الحصول على جدول محدد (على سبيل المثال، الجدول الأول)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// استخدم FindReplaceOptions لاستبدال النص في الجدول
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// احفظ المستند المعدل
doc.save("modified-document.docx");
```

يتيح لك ذلك إجراء عمليات استبدال النص على وجه التحديد داخل الجداول.

## خاتمة

يوفر Aspose.Words for Java إمكانات شاملة للعثور على النص واستبداله داخل مستندات Word. سواء كنت بحاجة إلى إجراء عمليات استبدال بسيطة للنص أو عمليات أكثر تقدمًا باستخدام التعبيرات العادية أو المعالجة الميدانية أو أدوات التقييم المخصصة، فإن Aspose.Words for Java يلبي احتياجاتك. تأكد من استكشاف الوثائق والأمثلة الشاملة التي تقدمها Aspose لتسخير الإمكانات الكاملة لمكتبة Java القوية هذه.

## الأسئلة الشائعة

### كيف أقوم بتنزيل Aspose.Words لـ Java؟

 يمكنك تنزيل Aspose.Words for Java من موقع الويب من خلال زيارة[هذا الرابط](https://releases.aspose.com/words/java/).

### هل يمكنني استخدام التعبيرات العادية لاستبدال النص؟

نعم، يمكنك استخدام التعبيرات العادية لاستبدال النص في Aspose.Words لـ Java. يتيح لك هذا إجراء عمليات بحث واستبدال أكثر تقدمًا ومرونة.

### كيف يمكنني تجاهل النص داخل الحقول أثناء الاستبدال؟

 لتجاهل النص الموجود داخل الحقول أثناء الاستبدال، يمكنك ضبط`IgnoreFields` ملكية`FindReplaceOptions` ل`true`وهذا يضمن استبعاد النص الموجود داخل الحقول، مثل حقول الدمج، من الاستبدال.

### هل يمكنني استبدال النص داخل الرؤوس والتذييلات؟

 نعم، يمكنك استبدال النص الموجود داخل الرؤوس والتذييلات لمستند Word الخاص بك. ما عليك سوى الوصول إلى الرأس أو التذييل المناسب واستخدام`replace` الطريقة مع المطلوب`FindReplaceOptions`.

### ما هو خيار UseLegacyOrder؟

 ال`UseLegacyOrder` الخيار في`FindReplaceOptions` يسمح لك باستخدام الترتيب القديم عند إجراء عمليات البحث والاستبدال. يمكن أن يكون هذا مفيدًا في سيناريوهات معينة حيث يكون سلوك الطلب القديم مرغوبًا فيه.