---
title: Вставить поле, включить текст без построителя документов
linktitle: Вставка FieldIncludeText без построителя документов
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить поле FieldIncludeText в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Ниже приведено пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция «Вставить поле FieldIncludeText» Aspose.Words для .NET. Обязательно внимательно выполняйте каждый шаг, чтобы получить желаемые результаты.

## Шаг 1. Настройка каталога документов

В предоставленном коде вы должны указать каталог ваших документов. Замените значение «КАТАЛОГ ВАШЕГО ДОКУМЕНТА» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Создание документа и абзаца

Начнем с создания нового документа и инициализации абзаца.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Шаг 3. Вставка поля FieldIncludeText

 Мы используем`AppendField()` метод для вставки поля FieldIncludeText в абзац.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Затем мы настраиваем свойства поля FieldIncludeText, указав имя закладки и имя исходного файла.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Далее мы добавляем абзац в тело документа.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Наконец, мы вызываем`Update()` метод обновления поля.

```csharp
fieldIncludeText.Update();
```

### Пример исходного кода для вставки поля FieldIncludeText с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и абзац.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Вставьте поле FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

В этом примере мы создали новый документ, инициализировали абзац, вставили FieldIncludeTexten, указав имя закладки и имя исходного файла, и сохранили документ с указанным именем файла.

На этом мы завершаем наше руководство по использованию функции «Вставка FieldIncludeText» в Aspose.Words для .NET.

### Часто задаваемые вопросы

#### Вопрос: Как указать исходный файл для поля включения текста в Aspose.Words для .NET?

 О: Чтобы указать исходный файл для поля включения текста в Aspose.Words for .NET, вы можете использовать команду`FieldIncludeText.SourceFullName`свойство, чтобы установить полный путь к исходному файлу. Убедитесь, что исходный файл доступен и содержит контент, который вы хотите включить в поле включения текста.

#### Вопрос: Могу ли я включить текст из макроса в поле включения текста с помощью Aspose.Words для .NET?

 О: Да, вы можете включить текст из макроса в поле включения текста с помощью Aspose.Words для .NET. Вы можете использовать`FieldIncludeText.IncludeText` Свойство, позволяющее указать имя макроса, содержимое которого должно быть включено в поле.

#### Вопрос: Влияет ли вставка поля включения текста без построителя документов на структуру документа Word с помощью Aspose.Words для .NET?

О: Вставка поля включения текста без построителя документов не влияет напрямую на структуру документа Word. Однако он добавляет новый элемент поля к содержимому документа. Вы можете манипулировать структурой документа, добавляя, удаляя или изменяя существующие элементы в соответствии с вашими потребностями.

#### Вопрос: Могу ли я настроить внешний вид поля включения текста в документе Word с помощью Aspose.Words для .NET?

О: Поле включения текста не позволяет напрямую настроить его внешний вид в документе Word. Однако вы можете форматировать включенный текст, используя свойства абзаца, свойства шрифта и другие объекты форматирования, доступные в Aspose.Words для .NET.