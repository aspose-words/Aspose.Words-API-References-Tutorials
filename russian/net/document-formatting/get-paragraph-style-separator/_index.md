---
title: Получить разделитель стиля абзаца
linktitle: Получить разделитель стиля абзаца
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как получить разделитель стиля абзаца с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-formatting/get-paragraph-style-separator/
---

В этом руководстве мы расскажем вам, как использовать функцию «Получить разделитель стилей абзаца» с Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и применить изменения.

## Шаг 1: Загрузка документа

Для начала укажите каталог для ваших документов и загрузите документ в объект Document. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Шаг 2: Поиск разделителей стилей абзаца

Теперь мы пройдемся по всем абзацам в документе и проверим, является ли абзац разделителем стилей. Вот как:

```csharp
foreach(Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (paragraph.BreakIsStyleSeparator)
     {
         Console.WriteLine("Separator found!");
     }
}
```

### Пример исходного кода для получения разделителя стиля абзаца с использованием Aspose.Words для .NET

Вот полный исходный код функции «Получить разделитель стиля абзаца» в Aspose.Words для .NET:

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

С помощью этого кода вы сможете найти разделители стилей абзаца в документе, используя Aspose.Words для .NET.

