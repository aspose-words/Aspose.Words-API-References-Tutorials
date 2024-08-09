---
title: إنشاء قسم تكرار الجدول المعين لجزء Xml المخصص
linktitle: إنشاء قسم تكرار الجدول المعين لجزء Xml المخصص
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء جدول يحتوي على قسم متكرر معين إلى CustomXmlPart في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---
## مقدمة

في هذا البرنامج التعليمي، سنتعرف على عملية إنشاء جدول يحتوي على قسم متكرر تم تعيينه إلى جزء XML مخصص باستخدام Aspose.Words for .NET. يعد هذا مفيدًا بشكل خاص لإنشاء المستندات ديناميكيًا استنادًا إلى البيانات المنظمة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من[موقع أسبوز](https://releases.aspose.com/words/net/).
2. فهم أساسي لـ C# وXML.

## استيراد مساحات الأسماء

تأكد من تضمين مساحات الأسماء الضرورية في مشروعك:

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Tables;
```

## الخطوة 1: تهيئة المستند و DocumentBuilder

 أولاً، قم بإنشاء مستند جديد وتهيئة ملف`DocumentBuilder`:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إضافة جزء XML مخصص

أضف جزءًا XML مخصصًا إلى المستند. يحتوي ملف XML هذا على البيانات التي نريد تعيينها لجدولنا:

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
    "<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
    "<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
    "<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## الخطوة 3: إنشاء هيكل الجدول

 بعد ذلك، استخدم`DocumentBuilder` لإنشاء رأس الجدول:

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## الخطوة 4: إنشاء قسم مكرر

 إنشاء أ`StructuredDocumentTag` (SDT) للقسم المكرر وقم بتعيينه على بيانات XML:

```csharp
StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## الخطوة 5: إنشاء عنصر القسم المتكرر

أنشئ SDT لعنصر القسم المكرر وأضفه إلى القسم المكرر:

```csharp
StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## الخطوة 6: تعيين بيانات XML إلى خلايا الجدول

قم بإنشاء SDTs للعنوان والمؤلف، وقم بتعيينها إلى بيانات XML، وألحقها بالصف:

```csharp
StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## الخطوة 7: احفظ المستند

أخيرًا، احفظ المستند في الدليل المحدد:

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

## خاتمة

باتباع هذه الخطوات، تكون قد نجحت في إنشاء جدول يحتوي على قسم متكرر تم تعيينه إلى جزء XML مخصص باستخدام Aspose.Words for .NET. وهذا يسمح بإنشاء محتوى ديناميكي استنادًا إلى البيانات المنظمة، مما يجعل إنشاء المستندات أكثر مرونة وقوة.

## الأسئلة الشائعة

### ما هي علامة الوثيقة المنظمة (SDT)؟
إن SDT، المعروف أيضًا باسم التحكم في المحتوى، هو منطقة محددة في مستند يتم استخدامه لاحتواء البيانات المنظمة.

### هل يمكنني استخدام أنواع بيانات أخرى في جزء XML المخصص؟
نعم، يمكنك هيكلة جزء XML المخصص الخاص بك باستخدام أي أنواع بيانات وتعيينها وفقًا لذلك.

### كيف يمكنني إضافة المزيد من الصفوف إلى القسم المكرر؟
يقوم القسم المكرر تلقائيًا بتكرار بنية الصف لكل عنصر في مسار XML المعين.