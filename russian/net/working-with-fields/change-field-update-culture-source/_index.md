---
title: Изменить источник культуры обновления поля
linktitle: Изменить источник культуры обновления поля
second_title: Справочник по API Aspose.Words для .NET
description: Изменить источник культуры обновления поля. Пошаговое руководство по изменению источника культуры в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/change-field-update-culture-source/
---

В этом руководстве мы проведем вас через процесс изменения источника культуры обновления поля в документах Word с помощью Aspose.Words для .NET. Изменяя источник языка и региональных параметров, вы можете управлять форматированием даты во время операций обновления поля и слияния. Мы предоставим вам необходимый исходный код C# и пошаговые инструкции для достижения этой цели.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте документ и DocumentBuilder
Для начала создайте экземпляр класса Document и объект DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставьте контент с определенной локалью
Затем установите локаль на немецкий и вставьте поля с форматированием даты:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

В приведенном выше коде мы устанавливаем локаль шрифта на немецкий язык (идентификатор локали 1031) и вставляем два поля с определенным форматированием даты.

## Шаг 3. Изменить источник культуры обновления поля
Чтобы изменить источник культуры обновления поля, используйте класс FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

В этом примере мы устанавливаем культуру, используемую во время обновления поля, для выбора из культуры, используемой полем.

## Шаг 4. Выполните слияние почты
Выполните операцию слияния почты и укажите значение даты в поле «Date2»:

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

В этом фрагменте кода мы выполняем операцию слияния почты и указываем значение DateTime для поля «Date2».

## Шаг 5: Сохраните документ
Сохраните измененный документ в файл с помощью метода Save класса Document:

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
Поздравляем! Вы успешно узнали, как изменить источник культуры обновления поля в документах Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете управлять культурой, используемой для форматирования даты во время операций обновления поля и слияния. Настройте источник культуры в соответствии с вашими требованиями, чтобы обеспечить точную и непротиворечивую дату.

### Часто задаваемые вопросы

#### Вопрос. Как изменить источник культуры обновления поля в Aspose.Words для .NET?

 О: Чтобы изменить источник культуры обновления поля в Aspose.Words для .NET, вы можете использовать`Document.FieldOptions.CultureSource` свойство и установите его значение равным`FieldCultureSource.FieldCode` или`FieldCultureSource.CurrentThread` . Например, вы можете использовать`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` использовать культуру, определенную в коде поля.

#### Вопрос: Как указать конкретную культуру для обновления полей в Aspose.Words для .NET?

 О: Чтобы указать конкретную культуру для обновления полей в Aspose.Words for .NET, вы можете использовать`Document.FieldOptions.FieldUpdateCultureInfo` свойство и установить`CultureInfo` объект, соответствующий желаемой культуре. Например, вы можете использовать`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` чтобы указать французскую (Францию) культуру.

#### В: Можно ли отключить автоматическое обновление полей в Aspose.Words для .NET?

 О: Да, в Aspose.Words для .NET можно отключить автоматическое обновление полей. Вы можете использовать`Document.FieldOptions.UpdateFields` свойство и установите его в`false` чтобы поля не обновлялись автоматически. Это позволяет вручную управлять обновлением полей по мере необходимости.

#### В: Как вручную обновить поля документа в Aspose.Words для .NET?

 О: Чтобы вручную обновить поля в документе в Aspose.Words for .NET, вы можете использовать`Field.Update` метод для каждого поля в отдельности. Например, вы можете использовать`field.Update()` для обновления определенного поля.