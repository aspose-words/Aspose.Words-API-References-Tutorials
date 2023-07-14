---
title: Клонирование документа
linktitle: Клонирование документа
second_title: API обработки документов Aspose.Words
description: Узнайте, как клонировать документ Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/clone-and-combine-documents/cloning-document/
---

В этом уроке мы расскажем вам, как клонировать документ Word, используя функцию клонирования Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и создать точную копию существующего документа.

## Шаг 1: Загрузка документа

Для начала укажите каталог документов и загрузите существующий документ в объект Document. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Шаг 2. Клонируйте документ

Теперь мы собираемся клонировать документ, создав его точную копию. Вот как:

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### Пример исходного кода для клонирования документа с использованием Aspose.Words для .NET

Вот полный исходный код функции клонирования документов Aspose.Words для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
Document doc = new Document(MyDir + "Document.docx");

Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
```

С помощью этого кода вы сможете клонировать документ Word, используя Aspose.Words для .NET. Точная копия документа будет сохранена под новым именем файла.

