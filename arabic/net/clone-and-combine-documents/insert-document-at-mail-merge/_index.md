---
title: إدراج مستند في دمج المراسلات
linktitle: إدراج مستند في دمج المراسلات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج مستند في مستند آخر أثناء دمج البريد باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/clone-and-combine-documents/insert-document-at-mail-merge/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية إدراج مستند في مستند آخر أثناء دمج البريد باستخدام ميزة "إدراج مستند أثناء دمج المراسلات" في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم كود المصدر وإجراء عملية إدراج المستند.

## الخطوة 1: تحميل المستند الرئيسي

للبدء ، حدد الدليل للمستندات الخاصة بك وقم بتحميل المستند الرئيسي في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## الخطوة 2: تكوين دمج المراسلات

لنقم الآن بتكوين دمج المراسلات وتحديد رد نداء دمج الحقول لإدراج مستند في مستند آخر. إليك الطريقة:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## الخطوة 3: تشغيل دمج المراسلات

سنقوم بتشغيل دمج البريد من خلال توفير أسماء حقول الدمج والبيانات المقابلة. إليك الطريقة:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### مثال على شفرة المصدر لـ Insert Document At Mail Merge باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة "إدراج مستند في دمج المراسلات" في Aspose.Words for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// يحتوي المستند الرئيسي على حقل دمج يسمى "Document_1".
// تحتوي البيانات المقابلة لهذا الحقل على مسار مؤهل بالكامل إلى المستند.
// يجب إدراج ذلك في هذا المجال.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

باستخدام هذا الرمز ، ستتمكن من إدراج مستند في مستند آخر أثناء دمج البريد باستخدام Aspose.Words for .NET. سيتم حفظ المستند الناتج تحت اسم جديد



