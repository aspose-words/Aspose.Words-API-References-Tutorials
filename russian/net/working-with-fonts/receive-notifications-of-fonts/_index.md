---
title: Получать уведомления о шрифтах
linktitle: Получать уведомления о шрифтах
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как получать уведомления об отсутствующих или замененных шрифтах при использовании Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/receive-notifications-of-fonts/
---

В этом руководстве мы расскажем, как получать уведомления о шрифтах при использовании Aspose.Words для .NET. Уведомления о шрифтах позволяют обнаруживать отсутствующие или замененные шрифты в документах и управлять ими. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте

## Шаг 1: Определите каталог документов
 Во-первых, вам нужно указать путь к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ и настройте параметры шрифта.
 Далее мы загрузим документ с помощью`Document` class и настройте параметры шрифта с помощью`FontSettings` сорт. Мы установим шрифт по умолчанию для использования в случае отсутствия шрифтов.

```csharp
//Загрузите документ и настройте параметры шрифта
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## Шаг 3. Установите обработчик уведомлений
 Далее мы определим обработчик уведомлений, реализуя`IWarningCallback` интерфейс. Это позволит нам собирать предупреждения о шрифтах при сохранении документа.

```csharp
// Определите обработчик уведомлений
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## Шаг 4: Примените настройки шрифта и сохраните документ
Наконец, мы применим настройки шрифта к документу и сохраним его. Любые предупреждения о шрифтах будут перехвачены обработчиком уведомлений, который мы определили ранее.

```csharp
// Примените настройки шрифта и сохраните документ
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### Пример исходного кода для получения уведомлений о шрифтах с использованием Aspose.Words для .NET 
```csharp

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Мы можем выбрать шрифт по умолчанию для использования в случае отсутствия шрифтов.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
// Для тестирования мы настроим Aspose.Words на поиск шрифтов только в несуществующей папке. Поскольку Aspose.Words не будет
// найти любые шрифты в указанном каталоге, тогда при рендеринге шрифты в документе будут подставлены под стандартные
//шрифт, указанный в разделе FontSettings.DefaultFontName. Мы можем подобрать это подзапрос, используя наш обратный вызов.
fontSettings.SetFontsFolder(string.Empty, false);
// Создайте новый класс, реализующий IWarningCallback, который собирает все предупреждения, созданные во время сохранения документа.
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## Заключение
В этом руководстве мы увидели, как получать уведомления о шрифтах при использовании Aspose.Words для .NET. Уведомления о шрифтах позволяют обнаруживать отсутствующие или замененные шрифты в документах и управлять ими. Используйте эту функцию, чтобы обеспечить согласованность шрифтов в ваших документах и принять соответствующие меры в случае отсутствия шрифтов.
