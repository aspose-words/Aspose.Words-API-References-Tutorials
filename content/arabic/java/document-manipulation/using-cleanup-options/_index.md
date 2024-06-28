---
title: استخدام خيارات التنظيف في Aspose.Words لـ Java
linktitle: استخدام خيارات التنظيف
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: قم بتحسين وضوح المستند باستخدام Aspose.Words لخيارات تنظيف Java. تعرف على كيفية إزالة الفقرات الفارغة والمناطق غير المستخدمة والمزيد.
type: docs
weight: 10
url: /ar/java/document-manipulation/using-cleanup-options/
---

## مقدمة لاستخدام خيارات التنظيف في Aspose.Words لـ Java

في هذا البرنامج التعليمي، سوف نستكشف كيفية استخدام خيارات التنظيف في Aspose.Words for Java لمعالجة المستندات وتنظيفها أثناء عملية دمج البريد. تتيح لك خيارات التنظيف التحكم في الجوانب المختلفة لتنظيف المستند، مثل إزالة الفقرات الفارغة والمناطق غير المستخدمة والمزيد.

## المتطلبات الأساسية

 قبل أن نبدأ، تأكد من دمج مكتبة Aspose.Words for Java في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/java/).

## الخطوة 1: إزالة الفقرات الفارغة

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إدراج حقول الدمج
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// ضبط خيارات التنظيف
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// تمكين الفقرات النظيفة مع علامات الترقيم
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// تنفيذ دمج البريد
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// احفظ المستند
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

في هذا المثال، نقوم بإنشاء مستند جديد، وإدراج حقول الدمج، وضبط خيارات التنظيف لإزالة الفقرات الفارغة. بالإضافة إلى ذلك، نقوم بتمكين إزالة الفقرات التي تحتوي على علامات الترقيم. بعد تنفيذ عملية دمج البريد، يتم حفظ المستند مع تطبيق عملية التنظيف المحددة.

## الخطوة 2: إزالة المناطق غير المدمجة

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// قم بتعيين خيارات التنظيف لإزالة المناطق غير المستخدمة
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// تنفيذ دمج البريد مع المناطق
doc.getMailMerge().executeWithRegions(data);

// احفظ المستند
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

في هذا المثال، نفتح مستندًا موجودًا يحتوي على مناطق دمج، ونضبط خيارات التنظيف لإزالة المناطق غير المستخدمة، ثم نقوم بتنفيذ دمج البريد ببيانات فارغة. تقوم هذه العملية تلقائيًا بإزالة المناطق غير المستخدمة من المستند.

## الخطوة 3: إزالة الحقول الفارغة

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// قم بتعيين خيارات التنظيف لإزالة الحقول الفارغة
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// تنفيذ دمج البريد
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// احفظ المستند
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

في هذا المثال، نفتح مستندًا يحتوي على حقول الدمج، ونضبط خيارات التنظيف لإزالة الحقول الفارغة، وننفذ دمج البريد مع البيانات. بعد الدمج، ستتم إزالة أي حقول فارغة من المستند.

## الخطوة 4: إزالة الحقول غير المستخدمة

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// قم بتعيين خيارات التنظيف لإزالة الحقول غير المستخدمة
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// تنفيذ دمج البريد
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// احفظ المستند
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

في هذا المثال، نفتح مستندًا يحتوي على حقول الدمج، ونضبط خيارات التنظيف لإزالة الحقول غير المستخدمة، وننفذ دمج البريد مع البيانات. بعد الدمج، ستتم إزالة أي حقول غير مستخدمة من المستند.

## الخطوة 5: إزالة الحقول المحتوية

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// قم بتعيين خيارات التنظيف لإزالة الحقول التي تحتوي عليها
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// تنفيذ دمج البريد
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// احفظ المستند
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

في هذا المثال، نفتح مستندًا يحتوي على حقول مدمجة، ونضبط خيارات التنظيف لإزالة الحقول التي تحتوي عليها، وننفذ دمج البريد مع البيانات. بعد الدمج، ستتم إزالة الحقول نفسها من المستند.

## الخطوة 6: إزالة صفوف الجدول الفارغة

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// قم بتعيين خيارات التنظيف لإزالة صفوف الجدول الفارغة
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// تنفيذ دمج البريد
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// احفظ المستند
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

في هذا المثال، نفتح مستندًا يحتوي على جدول وندمج الحقول، ونضبط خيارات التنظيف لإزالة صفوف الجدول الفارغة، وننفذ دمج البريد مع البيانات. بعد الدمج، ستتم إزالة أي صفوف جدول فارغة من المستند.

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية استخدام خيارات التنظيف في Aspose.Words for Java لمعالجة المستندات وتنظيفها أثناء عملية دمج البريد. توفر هذه الخيارات تحكمًا دقيقًا في تنظيف المستندات، مما يسمح لك بإنشاء مستندات مصقولة ومخصصة بسهولة.

## الأسئلة الشائعة

### ما هي خيارات التنظيف في Aspose.Words لـ Java؟

خيارات التنظيف في Aspose.Words for Java هي إعدادات تسمح لك بالتحكم في الجوانب المختلفة لتنظيف المستند أثناء عملية دمج البريد. إنها تمكنك من إزالة العناصر غير الضرورية مثل الفقرات الفارغة والمناطق غير المستخدمة والمزيد، مما يضمن أن المستند النهائي الخاص بك منظم جيدًا ومصقول.

### كيف يمكنني إزالة الفقرات الفارغة من وثيقتي؟

 لإزالة الفقرات الفارغة من مستندك باستخدام Aspose.Words for Java، يمكنك تعيين`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` خيار صحيح. سيؤدي هذا تلقائيًا إلى حذف الفقرات التي لا تحتوي على محتوى، مما يؤدي إلى الحصول على مستند أكثر نظافة.

###  ما هو الغرض من`REMOVE_UNUSED_REGIONS` cleanup option?

 ال`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` يتم استخدام الخيار لإزالة المناطق في المستند التي لا تحتوي على بيانات مقابلة أثناء عملية دمج المراسلات. فهو يساعد في الحفاظ على مستندك مرتبًا عن طريق التخلص من العناصر النائبة غير المستخدمة.

### هل يمكنني إزالة صفوف الجدول الفارغة من مستند باستخدام Aspose.Words for Java؟

 نعم، يمكنك إزالة صفوف الجدول الفارغة من المستند عن طريق تعيين`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`خيار التنظيف صحيح. سيؤدي هذا تلقائيًا إلى حذف أي صفوف جدول لا تحتوي على بيانات، مما يضمن جدولًا منظمًا بشكل جيد في مستندك.

###  ماذا يحدث عندما أقوم بتعيين`REMOVE_CONTAINING_FIELDS` option?

 وضع`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` سيقوم هذا الخيار بإزالة حقل الدمج بالكامل، بما في ذلك الفقرة التي تحتوي عليه، من المستند أثناء عملية دمج المراسلات. يعد هذا مفيدًا عندما تريد إزالة حقول الدمج والنص المرتبط بها.

### كيف يمكنني إزالة حقول الدمج غير المستخدمة من المستند الخاص بي؟

 لإزالة حقول الدمج غير المستخدمة من مستند، يمكنك تعيين`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` خيار صحيح. سيؤدي هذا تلقائيًا إلى إزالة حقول الدمج التي لم يتم ملؤها أثناء دمج المراسلات، مما يؤدي إلى الحصول على مستند أكثر نظافة.

###  ماهو الفرق بين`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

 ال`REMOVE_EMPTY_FIELDS` يقوم الخيار بإزالة حقول الدمج التي لا تحتوي على بيانات أو التي تكون فارغة أثناء عملية دمج المراسلات. ومن ناحية أخرى فإن`REMOVE_UNUSED_FIELDS`يقوم الخيار بإزالة حقول الدمج التي لم يتم ملؤها بالبيانات أثناء الدمج. يعتمد الاختيار بينهما على ما إذا كنت تريد إزالة الحقول التي لا تحتوي على محتوى أو تلك غير المستخدمة في عملية الدمج المحددة.

### كيف يمكنني تمكين إزالة الفقرات التي تحتوي على علامات الترقيم؟

 لتمكين إزالة الفقرات التي تحتوي على علامات الترقيم، يمكنك ضبط الإعداد`cleanupParagraphsWithPunctuationMarks` خيار صحيح وتحديد علامات الترقيم التي سيتم أخذها في الاعتبار عند التنظيف. يتيح لك هذا إنشاء مستند أكثر دقة عن طريق إزالة الفقرات غير الضرورية التي تحتوي على علامات الترقيم فقط.

### هل يمكنني تخصيص خيارات التنظيف في Aspose.Words لـ Java؟

نعم، يمكنك تخصيص خيارات التنظيف وفقًا لاحتياجاتك المحددة. يمكنك اختيار خيارات التنظيف التي سيتم تطبيقها وتكوينها وفقًا لمتطلبات تنظيف المستندات الخاصة بك، مما يضمن أن المستند النهائي الخاص بك يلبي المعايير المطلوبة.