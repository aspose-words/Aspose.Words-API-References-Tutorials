---
title: أدخل المستند عند الاستبدال
linktitle: أدخل المستند عند الاستبدال
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج مستند عند الاستبدال باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/clone-and-combine-documents/insert-document-at-replace/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية إدراج مستند في مستند آخر عند الاستبدال باستخدام ميزة "إدراج مستند عند استبدال" في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم كود المصدر وإجراء عملية إدراج المستند.

## الخطوة 1: تحميل المستند الرئيسي

للبدء ، حدد الدليل للمستندات الخاصة بك وقم بتحميل المستند الرئيسي في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## الخطوة 2: تكوين خيارات البحث والاستبدال

سنقوم الآن بتكوين خيارات البحث والاستبدال عن طريق تحديد اتجاه البحث واستبدال رد الاتصال لإدراج مستند في مستند آخر. إليك الطريقة:

```csharp
//تكوين خيارات البحث والاستبدال.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## الخطوة 3: استدعاء طريقة الاستبدال

سنقوم الآن باستدعاء طريقة الاستبدال للعثور على النص المحدد واستبداله بسلسلة فارغة ، باستخدام الخيارات التي تم تكوينها. إليك الطريقة:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### مثال على شفرة المصدر لـ Insert Document At Replace باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة "إدراج مستند" عند استبدال Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

	// تعيين خيارات البحث والاستبدال.
	FindReplaceOptions options = new FindReplaceOptions
	{
		Direction = FindReplaceDirection.Backward, 
		ReplacingCallback = new InsertDocumentAtReplaceHandler()
	};

	// اتصل بطريقة الاستبدال.
	mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
	mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");

```