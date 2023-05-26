---
title: Изменить язык
linktitle: Изменить язык
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как изменить языковой стандарт для форматирования даты и числа в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/change-locale/
---

В этом руководстве мы проведем вас через процесс изменения локали в документах Word с помощью Aspose.Words для .NET. Изменяя языковой стандарт, вы можете управлять форматированием дат и чисел во время операций слияния. Мы предоставим вам необходимый исходный код C# и пошаговые инструкции для достижения этой цели.

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

## Шаг 2. Вставьте поле
Затем вставьте в документ поле слияния с помощью метода InsertField:

```csharp
builder.InsertField("MERGEFIELD Date");
```

В приведенном выше коде мы вставляем в документ поле слияния с именем «Дата».

## Шаг 3. Измените локаль
Чтобы изменить языковой стандарт для форматирования даты и числа, вы можете изменить текущий язык и региональные параметры потока. В этом примере мы установим немецкий язык ("de-DE"):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

В приведенном выше коде мы сохраняем текущую культуру, а затем устанавливаем культуру текущего потока на немецкую.

## Шаг 4. Выполните слияние почты
Выполните операцию слияния почты и укажите значение даты в поле «Дата»:

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

В этом фрагменте кода мы выполняем операцию слияния почты и указываем текущую дату в качестве значения поля «Дата».

## Шаг 5. Восстановите исходную локаль
После завершения слияния восстановите исходную культуру для цепочки:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

В приведенном выше коде мы восстанавливаем исходную культуру потока.

## Шаг 6: Сохраните документ
Сохраните измененный документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Пример исходного кода для изменения локали с использованием Aspose.Words для .NET
Вот полный исходный код для изменения локали в документах Word с помощью Aspose.Words для .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Заключение
Поздравляем! Вы успешно научились изменять языковой стандарт в документах Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете управлять форматированием дат и чисел во время операций слияния. Настройте языковой стандарт в соответствии с вашими требованиями, чтобы обеспечить точное и согласованное форматирование в ваших документах.
