---
title: نقل إلى دمج الحقل
linktitle: نقل إلى دمج الحقل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تنفيذ ميزة Move To Merge Field في Aspose.Words for .NET باستخدام دليل خطوة بخطوة.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/move-to-merge-field/
---

في هذا المثال ، سوف نستكشف ميزة Move To Merge Field الخاصة بـ Aspose.Words for .NET. Aspose.Words مكتبة قوية لمعالجة المستندات تمكن المطورين من إنشاء وتعديل وتحويل مستندات Word برمجيًا. تتيح لنا ميزة Move To Merge Field التنقل لدمج الحقول داخل مستند وتنفيذ عمليات مختلفة عليها.


## شرح شفرة المصدر خطوة بخطوة

دعنا ننتقل إلى الكود المصدري خطوة بخطوة لفهم كيفية استخدام ميزة Move To Merge Field باستخدام Aspose.Words for .NET.

## الخطوة 1: تهيئة مستند إنشاء المستندات

أولاً ، قم بتهيئة كائنات Document و DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2 إدراج حقل دمج وإضافة نص بعده

استخدم الأسلوب InsertField لفئة DocumentBuilder لإدراج حقل دمج ، ثم قم بإضافة نص بعده:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## الخطوة 3: مؤشر المنشئ موجود حاليًا في نهاية المستند.

```csharp
Assert.Null(builder.CurrentNode);
```
## الخطوة 4: نقل مؤشر منشئ المستند إلى حقل الدمج

لنقل مؤشر منشئ المستند إلى حقل الدمج ، استخدم طريقة MoveToField لفئة DocumentBuilder:

```csharp
builder.MoveToField(field, true);
```

## إضافة نص مباشرة بعد حقل الدمج

بمجرد أن يكون مؤشر منشئ المستند داخل حقل الدمج ، يمكنك إضافة نص مباشرةً بعده باستخدام طريقة الكتابة:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### مثال على شفرة المصدر لـ Move To Merge Field باستخدام Aspose.Words for .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// أدخل حقلاً باستخدام DocumentBuilder وأضف سلسلة نصية بعده.
	Field field = builder.InsertField("MERGEFIELD field");
	builder.Write(" Text after the field.");

	// يوجد مؤشر المنشئ حاليًا في نهاية المستند.
	Assert.Null(builder.CurrentNode);
	// يمكننا نقل المنشئ إلى حقل مثل هذا ، ووضع المؤشر على الفور بعد الحقل.
	builder.MoveToField(field, true);

	// لاحظ أن المؤشر موجود في مكان ما بعد عقدة FieldEnd للحقل ، مما يعني أننا لسنا في الواقع داخل الحقل.
	// إذا كنا نرغب في نقل DocumentBuilder إلى داخل حقل ،
	// سنحتاج إلى نقله إلى عقدة FieldStart أو FieldSeparator باستخدام طريقة DocumentBuilder.MoveTo ().
	Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
	builder.Write(" Text immediately after the field.");
	
```

## خاتمة

لقد اكتشفنا ميزة Move To Merge Field الخاصة بـ Aspose.Words for .NET. لقد تعلمنا كيفية التنقل لدمج الحقول داخل مستند باستخدام فئة DocumentBuilder وتنفيذ العمليات عليها. هذه الميزة مفيدة عند العمل برمجيًا مع الدمج

