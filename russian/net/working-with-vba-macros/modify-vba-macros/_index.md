---
title: Изменить макросы Vba
linktitle: Изменить макросы Vba
second_title: Справочник по API Aspose.Words для .NET
description: Из этого руководства вы узнаете, как редактировать макросы VBA документа Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-vba-macros/modify-vba-macros/
---
В этом руководстве мы объясним, как изменить макросы VBA документа Word с помощью библиотеки Aspose.Words для .NET. Редактирование макросов VBA позволяет обновлять существующий код VBA в документе Word. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте
- Документ Word, содержащий макросы VBA, которые вы хотите изменить.

## Шаг 1: Определите каталог документов
 Во-первых, вам нужно указать путь к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ, содержащий макросы VBA.
Далее мы загрузим документ Word, содержащий макросы VBA, которые мы хотим изменить.

```csharp
// Загрузите документ, содержащий макросы VBA
Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
```

## Шаг 3. Измените исходный код макроса.
 Теперь мы собираемся изменить исходный код первого макроса проекта VBA. Заменить`newSourceCode` переменная с новым исходным кодом, который вы хотите использовать.

```csharp
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
```

## Шаг 4: Сохраните измененный документ
Наконец, мы сохраним измененный документ с обновленными макросами VBA в файл.

```csharp
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");
```

### Пример исходного кода для изменения макросов Vba с использованием Aspose.Words для .NET
 
```csharp

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");

```

## Заключение
В этом руководстве мы увидели, как редактировать макросы VBA в документе Word с помощью Aspose.Words для .NET. Редактирование макросов VBA позволяет обновить существующий код VBA в документе, чтобы внести изменения или улучшения. Не стесняйтесь использовать эту функцию для дальнейшей настройки и автоматизации документов Word.