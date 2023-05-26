---
title: الانتقال إلى خلية الجدول
linktitle: الانتقال إلى خلية الجدول
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لاستخدام Move To Table Cell في Aspose.Words for .NET
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/move-to-table-cell/
---

في هذا المثال ، سنرشدك إلى كيفية استخدام ميزة Move To Table Cell في Aspose.Words for .NET باستخدام كود المصدر C # المقدم خطوة بخطوة. تتيح لك هذه الميزة التنقل والتعامل مع خلايا معينة داخل جدول في مستند Word. اتبع الخطوات أدناه لدمج هذه الوظيفة في تطبيقك.

## الخطوة 1: قم بتحميل المستند الذي يحتوي على الجدول

أولاً ، نحتاج إلى تحميل المستند الذي يحتوي على الجدول الذي نريد نقل الخلية إليه. استخدم الكود التالي لإنجاز هذه الخطوة:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

يقوم هذا الرمز بتحميل المستند المحدد (استبدل "MyDir +" Tables.docx“” مع المسار الفعلي للمستند الذي يحتوي على الجدول).

## الخطوة 2: انقل DocumentBuilder إلى خلية جدول محددة

بعد ذلك ، سننقل DocumentBuilder إلى خلية جدول محددة. استخدم الكود التالي لإجراء هذه الخطوة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

 ينشئ هذا الرمز DocumentBuilder من المستند الموجود ثم ينقل المؤشر من DocumentBuilder إلى خلية الجدول المحددة. أخيرًا ، يضيف محتوى إلى تلك الخلية باستخدام ملف DocumentBuilder`Write()` طريقة.

## الخطوة 3: تحقق من النتيجة

يمكنك الآن التحقق من نجاح الانتقال إلى خلية الجدول. استخدم الكود التالي لإنجاز هذه الخطوة:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

يتحقق هذا الرمز من أن الخلية المحددة هي بالفعل الخلية الحالية لـ DocumentBuilder. كما يتحقق من أن المحتوى الذي تمت إضافته بواسطة DocumentBuilder قد تم حفظه بشكل صحيح في خلية الجدول.

هذا كل شئ ! لقد فهمت الآن كيفية استخدام وظيفة الانتقال إلى خلية الجدول في Aspose.Words for .NET باستخدام كود المصدر المقدم. يمكنك الآن دمج هذه الوظيفة في التطبيق الخاص بك ومعالجة خلايا جدول معينة في مستندات Word.


### مثال على شفرة المصدر للانتقال إلى خلية جدول باستخدام Aspose.Words for .NET


```csharp

	Document doc = new Document(MyDir + "Tables.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	// انقل المنشئ إلى الصف 3 ، الخلية 4 من الجدول الأول.
	builder.MoveToCell(0, 2, 3, 0);
	builder.Write("\nCell contents added by DocumentBuilder");
	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
	Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());

```
