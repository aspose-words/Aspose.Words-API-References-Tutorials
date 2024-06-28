---
title: إدراج مستند في دمج البريد
linktitle: إدراج مستند في دمج البريد
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج المستندات في حقول دمج البريد باستخدام Aspose.Words for .NET في هذا البرنامج التعليمي الشامل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## مقدمة

مرحبًا بك في عالم أتمتة المستندات باستخدام Aspose.Words for .NET! هل تساءلت يومًا عن كيفية إدراج المستندات ديناميكيًا في حقول محددة داخل مستند رئيسي أثناء عملية دمج البريد؟ حسنا، أنت في المكان الصحيح. سيرشدك هذا البرنامج التعليمي خطوة بخطوة خلال عملية إدراج المستندات في حقول دمج البريد باستخدام Aspose.Words for .NET. إنه مثل تجميع قطعة أحجية، حيث تقع كل قطعة في مكانها بشكل مثالي. لذا، دعونا نتعمق!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1.  Aspose.Words لـ .NET: يمكنك ذلك[تحميل أحدث نسخة هنا](https://releases.aspose.com/words/net/) . إذا كنت بحاجة إلى شراء ترخيص، يمكنك القيام بذلك[هنا](https://purchase.aspose.com/buy) . وبدلاً من ذلك، يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) أو جربه مع[تجربة مجانية](https://releases.aspose.com/).
2. بيئة التطوير: Visual Studio أو أي C# IDE آخر.
3. المعرفة الأساسية بـ C#: الإلمام ببرمجة C# سيجعل هذا البرنامج التعليمي سهلاً.

## استيراد مساحات الأسماء

أول الأشياء أولاً، ستحتاج إلى استيراد مساحات الأسماء الضرورية. هذه هي مثل اللبنات الأساسية لمشروعك.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

دعونا نقسم العملية إلى خطوات يمكن التحكم فيها. ستعتمد كل خطوة على الخطوة السابقة، مما يقودك إلى الحل الكامل.

## الخطوة 1: إعداد الدليل الخاص بك

قبل أن تتمكن من البدء في إدراج المستندات، تحتاج إلى تحديد المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يتم فيه تخزين المستندات الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل المستند الرئيسي

بعد ذلك، عليك تحميل المستند الرئيسي. يحتوي هذا المستند على حقول الدمج حيث سيتم إدراج المستندات الأخرى.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## الخطوة 3: إعداد رد اتصال دمج الحقول

للتعامل مع عملية الدمج، ستحتاج إلى تعيين وظيفة رد الاتصال. ستكون هذه الوظيفة مسؤولة عن إدراج المستندات في حقول الدمج المحددة.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## الخطوة 4: تنفيذ دمج المراسلات

حان الوقت الآن لتنفيذ عملية دمج البريد. هذا هو المكان الذي يحدث السحر. ستحدد حقل الدمج والمستند الذي يجب إدراجه في هذا الحقل.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## الخطوة 5: حفظ المستند

بعد اكتمال عملية دمج البريد، ستقوم بحفظ المستند المعدل. سيحتوي هذا المستند الجديد على المحتوى المدرج في المكان الذي تريده.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## الخطوة 6: إنشاء معالج رد الاتصال

معالج رد الاتصال هو فئة تقوم بإجراء معالجة خاصة لحقل الدمج. يقوم بتحميل المستند المحدد في قيمة الحقل وإدراجه في حقل الدمج الحالي.

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## الخطوة 7: إدراج المستند

تقوم هذه الطريقة بإدراج المستند المحدد في الفقرة الحالية أو خلية الجدول.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
        foreach (Node srcNode in srcSection.Body)
        {
            if (srcNode.NodeType == NodeType.Paragraph)
            {
                Paragraph para = (Paragraph)srcNode;
                if (para.IsEndOfSection && !para.HasChildNodes)
                    continue;
            }

            Node newNode = importer.ImportNode(srcNode, true);
            destinationParent.InsertAfter(newNode, insertionDestination);
            insertionDestination = newNode;
        }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

## خاتمة

وهناك لديك! لقد قمت بإدراج المستندات بنجاح في حقول معينة أثناء عملية دمج البريد باستخدام Aspose.Words for .NET. يمكن لهذه الميزة القوية أن توفر عليك الكثير من الوقت والجهد، خاصة عند التعامل مع كميات كبيرة من المستندات. فكر في الأمر كأنك تمتلك مساعدًا شخصيًا يتولى جميع المهام الثقيلة نيابةً عنك. إذا انطلق وقم بالمحاولة. ترميز سعيد!

## الأسئلة الشائعة

### هل يمكنني إدراج مستندات متعددة في حقول دمج مختلفة؟
 نعم يمكنك ذلك. ما عليك سوى تحديد حقول الدمج المناسبة ومسارات المستندات المقابلة في الملف`MailMerge.Execute` طريقة.

### هل من الممكن تنسيق المستند المدرج بشكل مختلف عن المستند الرئيسي؟
 قطعاً! يمكنك استخدام ال`ImportFormatMode` المعلمات في`NodeImporter` للتحكم في التنسيق

### ماذا لو كان اسم حقل الدمج ديناميكيًا؟
يمكنك التعامل مع أسماء حقول الدمج الديناميكي عن طريق تمريرها كمعلمات إلى معالج رد الاتصال.

### هل يمكنني استخدام هذه الطريقة مع تنسيقات ملفات مختلفة؟
نعم، يدعم Aspose.Words تنسيقات ملفات متنوعة بما في ذلك DOCX وPDF والمزيد.

### كيف أتعامل مع الأخطاء أثناء عملية إدراج المستند؟
قم بتنفيذ معالجة الأخطاء في معالج رد الاتصال الخاص بك لإدارة أي استثناءات قد تحدث.