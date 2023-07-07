---
title: Укажите языковой стандарт на уровне поля
linktitle: Укажите языковой стандарт на уровне поля
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как указать локализацию на уровне поля в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/specify-locale-at-field-level/
---

Ниже приведено пошаговое руководство для объяснения следующего исходного кода C#, который позволяет указать локализацию на уровне поля с помощью функции Aspose.Words for .NET. Перед использованием этого кода убедитесь, что вы включили библиотеку Aspose.Words в свой проект.

## Шаг 1. Установите путь к каталогу документов

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Обязательно укажите правильный путь к папке с документами, в которой будет сохранен отредактированный документ.

## Шаг 2: Создайте генератор документов

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Здесь мы создаем экземпляр`DocumentBuilder` class, который позволит нам добавлять поля в документ.

## Шаг 3. Вставьте поле даты с определенным местоположением

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Мы используем генератор документов, чтобы вставить поле типа`FieldType.FieldDate` в документ. Установив`LocaleId` собственность на`1049`, указываем русскую локализацию для этого поля.

## Шаг 4: Сохраните измененный документ

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Наконец, мы сохраняем измененный документ в указанном месте в указанный файл.

### Пример исходного кода для указания локализации на уровне поля с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Это был пример исходного кода для указания локализации на уровне поля в документе с использованием Aspose.Words для .NET. Вы можете использовать этот код для вставки полей даты в определенные места в ваших документах Word.

### Часто задаваемые вопросы

#### Вопрос. Как указать языковой стандарт на уровне поля в Aspose.Words для .NET?

 О: Чтобы указать локаль на уровне поля в Aspose.Words для .NET, вы можете использовать`FieldOptions` класс и его`FieldLocale` свойство, чтобы установить желаемую локаль. Например, вы можете использовать`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` чтобы указать французский язык (Франция).

#### В: Можно ли указать разные локали для каждого поля в Aspose.Words для .NET?

 О: Да, для каждого поля в Aspose.Words for .NET можно указать разные локали. Вы можете использовать`FieldOptions.FieldLocale` свойство перед созданием или обновлением определенного поля, чтобы назначить ему другую локаль.

#### В: Как я могу получить текущую используемую локаль для поля в Aspose.Words для .NET?

 О: Чтобы получить текущую используемую локаль для поля в Aspose.Words для .NET, вы можете использовать поле`Field.LocaleId` свойство. Это позволит вам получить идентификатор локали, связанный с полем.