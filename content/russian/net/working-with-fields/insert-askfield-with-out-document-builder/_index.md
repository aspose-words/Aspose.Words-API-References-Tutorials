---
title: Вставьте ASKField без построителя документов
linktitle: Вставьте ASKField без построителя документов
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить поле ASK в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Ниже приведено пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция «Вставить поле ASK без DocumentBuilder» в Aspose.Words для .NET. Обязательно внимательно выполняйте каждый шаг, чтобы получить желаемые результаты.

## Шаг 1. Настройка каталога документов

В предоставленном коде вы должны указать каталог ваших документов. Замените значение «КАТАЛОГ ВАШЕГО ДОКУМЕНТА» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Создание документа и абзаца

Мы начинаем с создания нового документа и получения первого абзаца.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Шаг 3. Вставка поля ASK.

 Мы используем`AppendField()` метод для вставки поля ASK в абзац.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Затем мы настраиваем различные свойства поля ASK, указывая нужные значения.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Наконец, мы вызываем`Update()` метод обновления поля.

```csharp
field. Update();
```

### Пример исходного кода для вставки поля ASK без DocumentBuilder с помощью Aspose.Words для .NET

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

На этом мы завершаем наше руководство по использованию функции «Вставить поле ASK без DocumentBuilder» в Aspose.Words для .NET.

### Часто задаваемые вопросы

#### Вопрос: Что такое поле ASK в Aspose.Words?

О: Поле ASK в Aspose.Words используется для того, чтобы задать пользователю вопрос при открытии документа. Он часто используется для запроса конкретной информации или отзывов, которые могут различаться от пользователя к пользователю.

#### Вопрос: Как вставить поле ASK в документ Word без использования Document Builder в Aspose.Words?

О: Чтобы вставить поле ASK в документ Word без использования Document Builder в Aspose.Words, вы можете выполнить следующие действия:

1. Импортируйте класс документа и поля из пространства имен Aspose.Words.Fields.
2. Создайте экземпляр Document, загрузив существующий документ.
3. Используйте метод InsertField, чтобы вставить поле ASK, указав имя вопроса.
4. Сохраните документ.

#### Вопрос: Как получить ответ пользователя на поле ASK в документе Word?

О: Чтобы получить ответ пользователя на поле ASK в документе Word, вы можете использовать метод GetFieldNames, доступный в классе Document. Этот метод возвращает список названий полей, присутствующих в документе. Затем вы можете проверить, присутствует ли имя поля ASK в списке, и получить соответствующий ответ.

#### Вопрос: Можно ли использовать поле ASK для запроса дополнительной информации у пользователя?

О: Да, поле ASK можно использовать для запроса нескольких фрагментов информации у пользователя. Вы можете вставить в документ несколько полей ASK, каждое из которых содержит отдельный вопрос. При открытии документа пользователю будут предложены соответствующие ответы.