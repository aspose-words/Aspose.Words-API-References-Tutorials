---
title: احصل على فاصل نمط الفقرة
linktitle: احصل على فاصل نمط الفقرة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية الحصول على فاصل نمط الفقرة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-formatting/get-paragraph-style-separator/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية استخدام ميزة Get Paragraph Style Separator مع Aspose.Words for .NET. اتبع الخطوات أدناه لفهم شفرة المصدر وتطبيق التغييرات.

## الخطوة 1: تحميل المستند

للبدء ، حدد الدليل للمستندات الخاصة بك وقم بتحميل المستند في كائن المستند. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## الخطوة 2: البحث عن فواصل نمط الفقرة

سنقوم الآن بتكرار جميع الفقرات في المستند والتحقق مما إذا كانت الفقرة هي فاصل نمط. إليك الطريقة:

```csharp
foreach(Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (paragraph.BreakIsStyleSeparator)
     {
         Console.WriteLine("Separator found!");
     }
}
```

### مثال على شفرة المصدر للحصول على فاصل نمط الفقرة باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لميزة Get Paragraph Style Separator مع Aspose.Words for .NET:

```csharp

            Document doc = new Document(MyDir + "Document.docx");

            foreach (Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
            {
                if (paragraph.BreakIsStyleSeparator)
                {
                    Console.WriteLine("Separator Found!");
                }
            }
        
```

باستخدام هذا الرمز ، ستتمكن من العثور على فواصل نمط الفقرة في مستند باستخدام Aspose.Words for .NET.

