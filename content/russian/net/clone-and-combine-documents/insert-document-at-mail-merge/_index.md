---
title: Вставить документ при слиянии писем
linktitle: Вставить документ при слиянии писем
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставлять документы в поля слияния почты с помощью Aspose.Words for .NET, в этом подробном пошаговом руководстве.
type: docs
weight: 10
url: /ru/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## Введение

Добро пожаловать в мир автоматизации документов с помощью Aspose.Words для .NET! Вы когда-нибудь задумывались, как динамически вставлять документы в определенные поля основного документа во время операции слияния писем? Ну, вы в правильном месте. Это руководство шаг за шагом проведет вас через процесс вставки документов в поля слияния почты с помощью Aspose.Words для .NET. Это похоже на сборку пазла, где каждый кусочек идеально встает на свое место. Итак, давайте погрузимся!

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1.  Aspose.Words для .NET: вы можете[Скачать последнюю версию здесь](https://releases.aspose.com/words/net/) . Если вам необходимо приобрести лицензию, вы можете это сделать[здесь](https://purchase.aspose.com/buy) . В качестве альтернативы вы можете получить[временная лицензия](https://purchase.aspose.com/temporary-license/) или попробуйте это с[бесплатная пробная версия](https://releases.aspose.com/).
2. Среда разработки: Visual Studio или любая другая среда разработки C#.
3. Базовые знания C#: Знакомство с программированием на C# облегчит изучение этого руководства.

## Импортировать пространства имен

Прежде всего, вам необходимо импортировать необходимые пространства имен. Это своего рода строительные блоки вашего проекта.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

Давайте разобьем процесс на управляемые этапы. Каждый шаг будет основываться на предыдущем, что приведет вас к полному решению.

## Шаг 1. Настройка каталога

Прежде чем вы сможете начать вставлять документы, вам необходимо определить путь к каталогу ваших документов. Здесь хранятся ваши документы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузка основного документа

Далее вы загрузите основной документ. Этот документ содержит поля слияния, куда будут вставлены другие документы.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## Шаг 3. Настройка обратного вызова слияния полей

Чтобы справиться с процессом слияния, вам необходимо установить функцию обратного вызова. Эта функция будет отвечать за вставку документов в указанные поля слияния.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Шаг 4. Выполнение слияния почты

Теперь пришло время выполнить слияние почты. Вот где происходит волшебство. Вы укажете поле слияния и документ, который должен быть вставлен в это поле.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## Шаг 5: Сохранение документа

После завершения слияния вы сохраните измененный документ. В этот новый документ будет вставлен контент именно там, где вы хотите.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## Шаг 6. Создание обработчика обратного вызова

Обработчик обратного вызова — это класс, который выполняет специальную обработку поля слияния. Он загружает документ, указанный в значении поля, и вставляет его в текущее поле слияния.

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

## Шаг 7: Вставка документа

Этот метод вставляет указанный документ в текущий абзац или ячейку таблицы.

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

## Заключение

И вот оно! Вы успешно вставили документы в определенные поля во время операции слияния почты с помощью Aspose.Words для .NET. Эта мощная функция может сэкономить вам массу времени и усилий, особенно при работе с большими объемами документов. Думайте об этом как о личном помощнике, который возьмет на себя всю тяжелую работу за вас. Так что давай, попробуй. Приятного кодирования!

## Часто задаваемые вопросы

### Могу ли я вставить несколько документов в разные поля слияния?
Да, ты можешь. Просто укажите соответствующие поля слияния и соответствующие пути к документам в`MailMerge.Execute` метод.

### Можно ли отформатировать вставленный документ иначе, чем основной документ?
 Абсолютно! Вы можете использовать`ImportFormatMode` параметр в`NodeImporter` для управления форматированием.

### Что делать, если имя поля слияния является динамическим?
Вы можете обрабатывать имена полей динамического слияния, передавая их в качестве параметров обработчику обратного вызова.

### Могу ли я использовать этот метод с разными форматами файлов?
Да, Aspose.Words поддерживает различные форматы файлов, включая DOCX, PDF и другие.

### Как обрабатывать ошибки в процессе вставки документа?
Реализуйте обработку ошибок в обработчике обратного вызова, чтобы управлять любыми исключениями, которые могут возникнуть.