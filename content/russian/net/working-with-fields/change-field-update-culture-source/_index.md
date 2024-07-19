---
title: Изменить поле Обновить источник культуры
linktitle: Изменить поле Обновить источник культуры
second_title: API обработки документов Aspose.Words
description: Изменение источника культуры и обновления поля. Пошаговое руководство по изменению источника культуры в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/change-field-update-culture-source/
---

В этом руководстве мы проведем вас через процесс изменения источника культуры обновления полей в документах Word с использованием Aspose.Words для .NET. Изменяя источник культуры, вы можете управлять форматированием даты во время операций обновления полей и слияния почты. Мы предоставим вам необходимый исходный код C# и пошаговые инструкции для достижения этой цели.

## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- Библиотека Aspose.Words for .NET, установленная в вашей системе.

## Шаг 1. Создайте документ и DocumentBuilder
Для начала создайте экземпляр класса Document и объект DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставьте контент с определенной локалью
Затем установите немецкий язык и вставьте поля с форматированием даты:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

В приведенном выше коде мы устанавливаем немецкий языковой стандарт шрифта (идентификатор языкового стандарта 1031) и вставляем два поля с определенным форматированием даты.

## Шаг 3. Измените источник культуры обновления поля
Чтобы изменить источник культуры обновления поля, используйте класс FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

В этом примере мы устанавливаем культуру, используемую во время обновления поля, на выбор из культуры, используемой полем.

## Шаг 4. Выполните слияние почты
Выполните операцию слияния писем и укажите значение даты для поля «Дата2»:

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

В этом фрагменте кода мы выполняем операцию слияния почты и указываем значение DateTime для поля «Date2».

## Шаг 5: Сохраните документ
Сохраните измененный документ в файл, используя метод Save класса Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Пример исходного кода для изменения источника культуры обновления поля с использованием Aspose.Words для .NET
Вот полный исходный код для изменения источника культуры обновления поля в документах Word с использованием Aspose.Words для .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Заключение
Поздравляем! Вы успешно узнали, как изменить источник культуры обновления поля в документах Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, вы теперь можете управлять культурой, используемой для форматирования даты во время операций обновления полей и слияния почты. Настройте источник культуры в соответствии со своими требованиями, чтобы обеспечить точную и последовательную дату.

### Часто задаваемые вопросы

#### Вопрос: Как изменить источник культуры обновления полей в Aspose.Words для .NET?

 О: Чтобы изменить источник культуры обновления поля в Aspose.Words for .NET, вы можете использовать`Document.FieldOptions.CultureSource` свойство и установить его значение`FieldCultureSource.FieldCode` или`FieldCultureSource.CurrentThread` . Например, вы можете использовать`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` использовать культуру, определенную в коде поля.

#### Вопрос: Как указать конкретную культуру для обновления полей в Aspose.Words для .NET?

 О: Чтобы указать конкретную культуру для обновления полей в Aspose.Words for .NET, вы можете использовать`Document.FieldOptions.FieldUpdateCultureInfo` свойство и установить`CultureInfo` объект, соответствующий желаемой культуре. Например, вы можете использовать`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` указать французскую (Французскую) культуру.

#### Вопрос: Можно ли отключить автоматическое обновление полей в Aspose.Words для .NET?

 О: Да, в Aspose.Words для .NET можно отключить автоматическое обновление полей. Вы можете использовать`Document.FieldOptions.UpdateFields` свойство и установите его в`false` чтобы предотвратить автоматическое обновление полей. Это позволяет вручную контролировать обновление полей по мере необходимости.

#### Вопрос: Как вручную обновить поля документа в Aspose.Words для .NET?

 О: Чтобы вручную обновить поля в документе в Aspose.Words for .NET, вы можете использовать`Field.Update` метод для каждого поля индивидуально. Например, вы можете использовать`field.Update()` чтобы обновить конкретное поле.