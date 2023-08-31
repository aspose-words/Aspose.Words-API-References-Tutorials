---
title: Вставка поля с помощью построителя полей
linktitle: Вставка поля с помощью построителя полей
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставлять настраиваемые поля в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-field-using-field-builder/
---

Ниже приведено пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция «Вставка поля с помощью FieldBuilder» Aspose.Words для .NET. Обязательно внимательно выполняйте каждый шаг, чтобы получить желаемые результаты.

## Шаг 1. Настройка каталога документов

В предоставленном коде вы должны указать каталог ваших документов. Замените значение «КАТАЛОГ ВАШЕГО ДОКУМЕНТА» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа

Начнем с создания нового документа.

```csharp
Document doc = new Document();
```

## Шаг 3. Создание поля ЕСЛИ с помощью FieldBuilder

Мы используем класс FieldBuilder для создания поля IF с двумя вложенными полями MERGEFIELD. В этом примере поле ЕСЛИ отображает имя и фамилию в зависимости от условия.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Шаг 4. Вставка поля ЕСЛИ в документ

 Мы используем`BuildAndInsert()` метод для создания и вставки поля IF в определенное место документа.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Пример исходного кода для вставки поля с помощью FieldBuilder с Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа.
Document doc = new Document();

// Построение поля IF с помощью FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Вставьте поле ЕСЛИ в документ.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

В этом примере мы создали новый документ, создали поле IF с вложенными полями MERGEFIELD, а затем вставили это поле в документ в указанном месте. Затем документ сохраняется с определенным именем файла.

### Часто задаваемые вопросы

#### Вопрос: Что такое конструктор полей в Aspose.Words?

О: Построитель полей в Aspose.Words — это мощный инструмент для создания полей в документе Word и управления ими. Он предлагает расширенные функции для создания и настройки полей, включая вставку кодов полей и управление параметрами форматирования.

#### Вопрос: Какие типы полей можно вставлять с помощью конструктора полей?

О: Конструктор полей в Aspose.Words позволяет вам вставлять поля разных типов в документ Word. Вот несколько примеров часто используемых типов полей:

- MERGEFIELD: используется для объединения данных из внешних источников.
- ДАТА: отображает текущую дату.
- СТРАНИЦА: отображает номер текущей страницы.
- ЕСЛИ: позволяет настроить отображение контента в соответствии с условием.
- TOC: автоматически генерирует оглавление на основе стилей заголовков документов.

#### Вопрос: Как настроить поля, вставленные с помощью конструктора полей?

О: Конструктор полей предлагает параметры настройки вставленных полей. Вы можете использовать методы и свойства конструктора полей для установки таких параметров, как форматирование поля, аргументы, переключатели и значения по умолчанию. Например, вы можете установить формат даты, формат чисел, разделитель тысяч и т. д.
  