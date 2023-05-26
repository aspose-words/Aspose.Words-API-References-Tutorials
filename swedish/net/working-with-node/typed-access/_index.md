---
title: الوصول المكتوب
linktitle: الوصول المكتوب
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام الوصول المكتوب لمعالجة الجداول في Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/working-with-node/typed-access/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح شفرة المصدر C # أدناه والتي توضح كيفية استخدام ميزة الوصول المكتوب مع Aspose.Words for .NET.

## الخطوة 1: استيراد المراجع الضرورية
قبل أن تبدأ ، تأكد من استيراد المراجع الضرورية لاستخدام Aspose.Words for .NET في مشروعك. يتضمن ذلك استيراد مكتبة Aspose.Words وإضافة مساحات الأسماء المطلوبة إلى ملف المصدر الخاص بك.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## الخطوة 2: قم بإنشاء مستند جديد
 في هذه الخطوة ، سننشئ مستندًا جديدًا باستخدام امتداد`Document` فصل.

```csharp
Document doc = new Document();
```

## الخطوة 3: قم بالوصول إلى القسم والجسم
للوصول إلى الجداول الواردة في المستند ، يجب علينا أولاً الوصول إلى قسم ونص الوثيقة.

```csharp
Section section = doc.FirstSection;
Body body = section.Body;
```

## الخطوة 4: الوصول السريع والمكتوب إلى الجداول
الآن بعد أن أصبح لدينا نص المستند ، يمكننا استخدام الوصول السريع والمكتوب للوصول إلى جميع الجداول الموجودة في النص.

```csharp
TableCollection tables = body.Tables;
```

## الخطوة 5: تصفح الجداول
 باستخدام ملف`foreach` loop ، يمكننا المرور عبر جميع الجداول وإجراء عمليات محددة على كل جدول.

```csharp
foreach(Table table in tables)
{
     // الوصول السريع والمكتوب إلى الصف الأول من الجدول.
     table.FirstRow?.Remove();

     // الوصول السريع والمكتوب إلى الصف الأخير من الجدول.
     table.LastRow?.Remove();
}
```

في هذا المثال ، نحذف الصف الأول والأخير من كل جدول باستخدام الوصول السريع والمكتوب المقدم من Aspose.Words.

### نموذج التعليمات البرمجية المصدر للوصول المكتوب باستخدام Aspose.Words for .NET

```csharp
	Document doc = new Document();

	Section section = doc.FirstSection;
	Body body = section.Body;
	
	// وصول سريع مكتوب إلى جميع العقد الفرعية التابعة للجدول الموجودة في النص الأساسي.
	TableCollection tables = body.Tables;

	foreach (Table table in tables)
	{
		// وصول سريع مكتوب إلى الصف الأول من الجدول.
		table.FirstRow?.Remove();

		// وصول سريع مكتوب إلى الصف الأخير من الجدول.
		table.LastRow?.Remove();
	}
            
```

هذا نموذج كامل من التعليمات البرمجية للوصول المكتوب إلى الجداول باستخدام Aspose.Words for .NET. تأكد من استيراد المراجع الضرورية واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك.

---
