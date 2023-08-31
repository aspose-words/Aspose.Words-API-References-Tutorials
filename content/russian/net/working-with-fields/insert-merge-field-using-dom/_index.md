---
title: Вставьте поле слияния с помощью DOM
linktitle: Вставьте поле слияния с помощью DOM
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставлять поля слияния настраиваемых полей в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-merge-field-using-dom/
---

Вот пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция «Вставить поле слияния» в Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа и DocumentBuilder

Начнем с создания нового документа и инициализации DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3: Перемещение курсора к абзацу

 Мы используем`MoveTo()` метод DocumentBuilder, чтобы переместить курсор в абзац, куда мы хотим вставить поле слияния полей.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Шаг 4: Вставка поля слияния полей

 Мы используем DocumentBuilder`InsertField()` метод вставки поля слияния полей в абзац.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Затем мы настраиваем свойства поля слияния полей, указав соответствующие параметры, такие как имя поля, текст до и после поля и параметры вертикального форматирования.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Наконец, мы вызываем`Update()` способ обновления поля.

```csharp
field. Update();
```

### Пример исходного кода для вставки поля слияния полей с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Подведите курсор к абзацу.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Вставить поле слияния полей.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Обновите поле.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

В этом примере мы создали новый документ, переместили курсор в нужный абзац, а затем вставили в документ поле слияния полей.

### Часто задаваемые вопросы

#### В: Как я могу вставить поле слияния в документ Word, используя Aspose.Words для .NET с DOM?

О: Чтобы вставить поле слияния в документ Word с помощью Aspose.Words для .NET с DOM, выполните следующие действия:

1. Перейдите к абзацу, в который вы хотите вставить поле слияния.
2.  Создать`FieldMergeField` объект.
3. Задайте свойства поля слияния, такие как имя поля и параметры форматирования.
4.  Добавьте поле слияния в абзац, используя`Paragraph.AppendChild` метод.

#### В: Как я могу указать исходные данные для поля слияния в Aspose.Words для .NET?

О: Чтобы указать исходные данные для поля слияния в Aspose.Words for .NET, вы можете использовать`FieldMergeField.FieldName` метод для установки имени поля слияния, которое является именем поля во внешнем источнике данных, таком как файл CSV, база данных и т. д. Вы также можете использовать метод`FieldMergeField.Text` метод, чтобы установить значение поля слияния напрямую.

#### В: Могу ли я настроить внешний вид поля слияния в документе Word с помощью Aspose.Words for .NET?

 О: Да, вы можете настроить внешний вид поля слияния в документе Word с помощью Aspose.Words для .NET. Вы можете установить параметры форматирования, такие как регистр, шрифт, цвет и т. д., используя свойства`FieldMergeField` объект.

#### В: Как я могу проверить, успешно ли вставлено поле слияния в документ Word с помощью Aspose.Words для .NET?

 О: Чтобы проверить, успешно ли было вставлено поле слияния, вы можете просмотреть содержимое документа и выполнить поиск экземпляров поля слияния. Вы можете использовать методы и свойства`Document` object для доступа к абзацам, полям и другим элементам документа.

#### В: Влияет ли вставка поля слияния с использованием DOM на структуру документа Word с Aspose.Words для .NET?

A: Вставка поля слияния с помощью DOM не влияет напрямую на структуру документа Word. Однако он добавляет новый элемент поля к содержимому документа. Вы можете манипулировать структурой документа, добавляя, удаляя или изменяя существующие элементы в соответствии с вашими потребностями.