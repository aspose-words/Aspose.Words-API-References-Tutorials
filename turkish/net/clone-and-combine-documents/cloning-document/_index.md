---
title: وثيقة الاستنساخ
linktitle: وثيقة الاستنساخ
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استنساخ مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/clone-and-combine-documents/cloning-document/
---

في هذا البرنامج التعليمي ، سنخبرك بكيفية استنساخ مستند Word باستخدام ميزة النسخ في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم التعليمات البرمجية المصدر وإنشاء نسخة طبق الأصل من مستند موجود.

## الخطوة 1: تحميل المستند

للبدء ، حدد دليل المستند الخاص بك وقم بتحميل المستند الموجود في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## الخطوة 2: استنساخ المستند

سنقوم الآن باستنساخ المستند لإنشاء نسخة طبق الأصل منه. إليك الطريقة:

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### مثال على شفرة المصدر لنسخ المستند باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة استنساخ مستندات Aspose.Words لـ .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";            
	Document doc = new Document(MyDir + "Document.docx");

	Document clone = doc.Clone();
	clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
	
```

باستخدام هذا الرمز ، ستتمكن من استنساخ مستند Word باستخدام Aspose.Words for .NET. سيتم حفظ النسخة الدقيقة من المستند باسم ملف جديد.

