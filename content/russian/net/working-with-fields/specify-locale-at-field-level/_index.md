---
title: Укажите локаль на уровне поля
linktitle: Укажите локаль на уровне поля
second_title: API обработки документов Aspose.Words
description: Узнайте, как указать локализацию на уровне полей в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/specify-locale-at-field-level/
---

Вот пошаговое руководство, объясняющее следующий исходный код C#, который позволяет указать локализацию на уровне поля с помощью функции Aspose.Words for .NET. Прежде чем использовать этот код, убедитесь, что вы включили библиотеку Aspose.Words в свой проект.

## Шаг 1. Установите путь к каталогу документов.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Обязательно укажите правильный путь к каталогу ваших документов, в котором будет сохранен отредактированный документ.

## Шаг 2. Создайте генератор документов

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Здесь мы создаем экземпляр`DocumentBuilder` класс, который позволит нам добавлять поля в документ.

## Шаг 3. Вставьте поле даты с указанием конкретного местоположения.

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Мы используем генератор документов для вставки поля типа`FieldType.FieldDate` в документ. Установив`LocaleId`собственность`1049`, для этого поля указываем русскую локализацию.

## Шаг 4. Сохраните измененный документ.

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

Это был пример исходного кода для указания локализации на уровне поля в документе с использованием Aspose.Words для .NET. Вы можете использовать этот код для вставки полей даты в определенные места в документах Word.

### Часто задаваемые вопросы

#### Вопрос: Как указать локаль уровня поля в Aspose.Words для .NET?

 О: Чтобы указать локаль на уровне поля в Aspose.Words for .NET, вы можете использовать`FieldOptions` класс и его`FieldLocale` свойство для установки желаемой локали. Например, вы можете использовать`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` чтобы указать французский язык (Франция).

#### Вопрос: Можно ли указать разные локали для каждого поля в Aspose.Words for .NET?

 О: Да, для каждого поля в Aspose.Words for .NET можно указать разные локали. Вы можете использовать`FieldOptions.FieldLocale` перед созданием или обновлением определенного поля, чтобы назначить ему другой языковой стандарт.

#### Вопрос: Как получить текущую локаль для поля в Aspose.Words для .NET?

 О: Чтобы получить используемый в данный момент языковой стандарт для поля в Aspose.Words for .NET, вы можете использовать`Field.LocaleId` свойство. Это позволит вам получить идентификатор локали, связанный с полем.