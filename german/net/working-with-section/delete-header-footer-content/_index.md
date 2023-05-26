---
title: حذف محتوى رأس التذييل
linktitle: حذف محتوى رأس التذييل
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، تعرف على كيفية إزالة محتوى الرأس والتذييل من مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/working-with-section/delete-header-footer-content/
---

في هذا البرنامج التعليمي ، سوف نوضح لك كيفية إزالة محتوى الرأس والتذييل من مستند Word باستخدام مكتبة Aspose.Words لـ .NET. يمكن أن تكون إزالة المحتوى من الرؤوس والتذييلات مفيدة عندما تريد إعادة تعيين هذه العناصر أو إزالتها من المستند. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك
- مستند Word يحتوي على الرؤوس والتذييلات التي تريد إزالتها

## الخطوة 1: تحديد دليل المستند
 أولاً ، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند وانتقل إلى القسم
 بعد ذلك ، سنقوم بتحميل مستند Word في مثيل`Document` فصل. سنصل إلى القسم الأول من المستند باستخدام الفهرس 0.

```csharp
//قم بتحميل المستند
Document doc = new Document(dataDir + "Document.docx");

// قم بالوصول إلى القسم
Section section = doc.Sections[0];
```

## الخطوة 3: حذف محتوى الرأس والتذييل
 لإزالة محتوى الرأس والتذييل من القسم ، سنستخدم الامتداد`ClearHeadersFooters` طريقة.

```csharp
section.ClearHeadersFooters();
```

### نموذج التعليمات البرمجية المصدر لـ Delete Header Footer Content باستخدام Aspose.Words for .NET 

```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## خاتمة
في هذا البرنامج التعليمي ، رأينا كيفية إزالة محتوى الرأس والتذييل من مستند Word باستخدام Aspose.Words for .NET. تتيح لك إزالة المحتوى من الرؤوس والتذييلات إعادة تعيين هذه العناصر المحددة أو إزالتها من المستند. لا تتردد في تخصيص هذه الميزة واستخدامها وفقًا لاحتياجاتك الخاصة.
