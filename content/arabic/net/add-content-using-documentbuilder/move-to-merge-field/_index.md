---
title: الانتقال لدمج الحقل في مستند Word
linktitle: الانتقال لدمج الحقل في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تنفيذ ميزة Move To Merge Field في مستند Word الخاصة بـ Aspose.Words for .NET باستخدام دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/move-to-merge-field/
---
في هذا المثال، سوف نستكشف ميزة النقل لدمج الحقل في مستند Word في Aspose.Words for .NET. Aspose.Words هي مكتبة قوية لمعالجة المستندات تمكن المطورين من إنشاء مستندات Word وتعديلها وتحويلها برمجيًا. تتيح لنا ميزة Move To Merge Field التنقل لدمج الحقول داخل المستند وإجراء عمليات متنوعة عليها.


## شرح الكود المصدري خطوة بخطوة

دعنا نستعرض التعليمات البرمجية المصدر خطوة بخطوة لفهم كيفية استخدام ميزة Move To Merge Field باستخدام Aspose.Words for .NET.

## الخطوة 1: تهيئة المستند ومنشئ المستندات

أولاً، قم بتهيئة كائنات Document وDocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إدراج حقل دمج وإضافة نص بعده

استخدم الأسلوب InsertField الخاص بالفئة DocumentBuilder لإدراج حقل دمج، ثم قم بإضافة نص بعده:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## الخطوة 3: مؤشر المنشئ موجود حاليًا في نهاية المستند.

```csharp
Assert.Null(builder.CurrentNode);
```
## الخطوة 4: نقل مؤشر منشئ المستندات إلى حقل الدمج

لتحريك مؤشر منشئ المستندات إلى حقل الدمج، استخدم أسلوب MoveToField الخاص بفئة DocumentBuilder:

```csharp
builder.MoveToField(field, true);
```

## إضافة نص مباشرة بعد حقل الدمج

بمجرد أن يكون مؤشر منشئ المستندات داخل حقل الدمج، يمكنك إضافة نص مباشرة بعده باستخدام طريقة الكتابة:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### مثال على التعليمات البرمجية المصدر لحقل Move To Merge باستخدام Aspose.Words لـ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإدراج حقل باستخدام DocumentBuilder وأضف سلسلة من النص بعده.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// يوجد مؤشر المنشئ حاليًا في نهاية المستند.
Assert.Null(builder.CurrentNode);
// يمكننا نقل المنشئ إلى حقل مثل هذا، مع وضع المؤشر مباشرة بعد الحقل.
builder.MoveToField(field, true);

// لاحظ أن المؤشر موجود في مكان ما بعد عقدة FieldEnd للحقل، مما يعني أننا لسنا داخل الحقل فعليًا.
// إذا أردنا نقل DocumentBuilder إلى داخل الحقل،
// سنحتاج إلى نقله إلى عقدة FieldStart أو FieldSeparator الخاصة بالحقل باستخدام طريقة DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## خاتمة

لقد استكشفنا ميزة Move To Merge Field في Aspose.Words لـ .NET. لقد تعلمنا كيفية التنقل لدمج الحقول داخل مستند باستخدام فئة DocumentBuilder وتنفيذ العمليات عليها. هذه الميزة مفيدة عند معالجة الكلمات برمجياً مع الدمج

### الأسئلة الشائعة حول الانتقال إلى دمج الحقل في مستند Word

#### س: ما هو الغرض من ميزة النقل لدمج الحقل في Aspose.Words لـ .NET؟

ج: تتيح ميزة Move To Merge Field في Aspose.Words for .NET للمطورين التنقل لدمج الحقول داخل مستند Word وإجراء عمليات متنوعة عليها برمجيًا. حقول الدمج هي عناصر نائبة خاصة تُستخدم في مستندات Word لعمليات دمج البريد.

#### س: كيف يمكنني إدراج حقل دمج في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: يمكنك استخدام الأسلوب InsertField الخاص بالفئة DocumentBuilder لإدراج حقل دمج في المستند. بعد إدراج حقل الدمج، يمكنك إضافة محتوى، مثل النص، قبل الحقل أو بعده باستخدام أسلوب الكتابة.

#### س: كيف يمكنني نقل مؤشر منشئ المستندات إلى حقل دمج محدد؟

ج: لتحريك مؤشر منشئ المستندات إلى حقل دمج محدد، استخدم أسلوب MoveToField الخاص بفئة DocumentBuilder وقم بتمرير الحقل كمعلمة. سيؤدي هذا إلى وضع المؤشر مباشرة بعد حقل الدمج.

#### س: هل يمكنني إضافة نص داخل حقل دمج باستخدام ميزة النقل إلى حقل الدمج؟

ج: لا، فميزة النقل إلى حقل الدمج تضع مؤشر أداة إنشاء المستندات مباشرة بعد حقل الدمج. لإضافة نص داخل حقل الدمج، يمكنك استخدام الأسلوب DocumentBuilder.MoveTo لنقل المؤشر إلى عقدة FieldStart أو FieldSeparator لحقل الدمج.

#### س: كيف يمكنني إجراء عمليات دمج البريد باستخدام Aspose.Words لـ .NET؟

ج: يوفر Aspose.Words for .NET دعمًا شاملاً لعمليات دمج البريد. يمكنك استخدام فئة MailMerge لإجراء دمج البريد باستخدام بيانات من مصادر مختلفة مثل المصفوفات أو مجموعات البيانات أو مصادر البيانات المخصصة.