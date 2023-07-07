---
title: Вставить ASKField без Document Builder
linktitle: Вставить ASKField без Document Builder
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить поле ASK в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором используется функция «Вставить поле ASK без DocumentBuilder» в Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа и абзаца

Начнем с создания нового документа и извлечения первого абзаца.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Шаг 3: Вставка поля ASK

 Мы используем`AppendField()` способ вставки поля ASK в абзац.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Затем мы настраиваем различные свойства поля ASK, указав нужные значения.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Наконец, мы вызываем`Update()` способ обновления поля.

```csharp
field. Update();
```

### Пример исходного кода для вставки поля ASK без DocumentBuilder с Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Вставьте поле ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

В этом примере мы создали новый документ, вставили поле ASK без использования DocumentBuilder, настроили различные свойства поля и сохранили документ с указанным именем файла.

На этом мы завершаем наше руководство по использованию функции «Вставить поле ASK без DocumentBuilder» с Aspose.Words для .NET.

### Часто задаваемые вопросы

#### В: Что такое поле ASK в Aspose.Words?

A: Поле ASK в Aspose.Words используется для того, чтобы задать пользователю вопрос при открытии документа. Он часто используется для запроса конкретной информации или обратной связи, которая может варьироваться от пользователя к пользователю.

#### В: Как вставить поле ASK в документ Word без использования Document Builder в Aspose.Words?

О: Чтобы вставить поле ASK в документ Word без использования Document Builder в Aspose.Words, выполните следующие действия:

1. Импортировать класс Document и Field из пространства имен Aspose.Words.Fields.
2. Создайте экземпляр Document, загрузив существующий документ.
3. Используйте метод InsertField, чтобы вставить поле ASK, указав имя вопроса.
4. Сохраните документ.

#### Вопрос. Как получить ответ пользователя для поля ASK в документе Word?

О: Чтобы получить ответ пользователя для поля ASK в документе Word, вы можете использовать метод GetFieldNames, доступный в классе Document. Этот метод возвращает список имен полей, присутствующих в документе. Затем вы можете проверить, присутствует ли имя поля ASK в списке, и получить соответствующий ответ.

#### В: Можно ли использовать поле ASK для запроса дополнительной информации от пользователя?

О: Да, поле ASK можно использовать для запроса нескольких фрагментов информации от пользователя. Вы можете вставить в документ несколько полей ASK, каждое из которых содержит отдельный вопрос. При открытии документа пользователю будет предложено ввести соответствующие ответы.