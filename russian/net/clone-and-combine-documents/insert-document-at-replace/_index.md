---
title: Вставить документ при замене
linktitle: Вставить документ при замене
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить документ о замене с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/clone-and-combine-documents/insert-document-at-replace/
---

В этом руководстве мы расскажем вам, как вставить документ в другой документ при замене с помощью функции «Вставить документ при замене» в Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и выполнить вставку документа.

## Шаг 1: Загрузка основного документа

Для начала укажите каталог для ваших документов и загрузите основной документ в объект Document. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Шаг 2. Настройте параметры поиска и замены

Теперь мы настроим параметры поиска и замены, указав направление поиска и обратный вызов замены, чтобы вставить документ в другой документ. Вот как:

```csharp
//Настройте параметры поиска и замены.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Шаг 3: Вызов метода замены

Теперь мы вызовем метод замены, чтобы найти и заменить указанный текст пустой строкой, используя настроенные параметры. Вот как:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Пример исходного кода для вставки документа при замене с использованием Aspose.Words для .NET

Вот полный исходный код для функции «Вставить документ» при замене Aspose.Words для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Установите параметры поиска и замены.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Вызовите метод замены.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```