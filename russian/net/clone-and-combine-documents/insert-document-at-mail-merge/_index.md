---
title: Вставить документ при слиянии
linktitle: Вставить документ при слиянии
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить документ в другой во время слияния с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/clone-and-combine-documents/insert-document-at-mail-merge/
---

В этом руководстве мы расскажем вам, как вставить документ в другой документ во время слияния с помощью функции «Вставить документ во время слияния» в Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и выполнить вставку документа.

## Шаг 1: Загрузка основного документа

Для начала укажите каталог для ваших документов и загрузите основной документ в объект Document. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Шаг 2. Настройте слияние почты

Теперь давайте настроим слияние почты и укажем обратный вызов слияния полей, чтобы вставить документ в другой документ. Вот как:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Шаг 3: Запуск слияния почты

Мы запустим слияние, указав имена полей слияния и соответствующие данные. Вот как:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Пример исходного кода для вставки документа при слиянии с использованием Aspose.Words для .NET

Вот полный исходный код для функции «Вставить документ в слияние» Aspose.Words для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// В основном документе есть поле слияния под названием «Документ_1».
// Соответствующие данные для этого поля содержат полный путь к документу.
// Это должно быть вставлено в это поле.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

С помощью этого кода вы сможете вставлять документ в другой документ во время слияния почты, используя Aspose.Words для .NET. Полученный документ будет сохранен под новым именем



