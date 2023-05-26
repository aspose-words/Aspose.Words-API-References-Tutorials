---
title: Создать проект VBA
linktitle: Создать проект VBA
second_title: Справочник по API Aspose.Words для .NET
description: Из этого руководства вы узнаете, как создать проект VBA в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-vba-macros/create-vba-project/
---

В этом уроке мы расскажем вам, как создать проект VBA в документе Word, используя библиотеку Aspose.Words для .NET. Создание проекта VBA позволяет добавить в документ Word собственный код VBA. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

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

## Шаг 2: Создайте новый документ и проект VBA
 Далее мы создадим новый документ, создав экземпляр`Document` класс и пустой проект VBA, создав экземпляр`VbaProject` сорт.

```csharp
// Создать новый документ
Document doc = new Document();

// Создайте новый проект VBA
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
```

## Шаг 3: Создайте новый модуль и укажите исходный код макроса
 Мы создадим новый модуль, создав экземпляр`VbaModule` class и указав имя макроса, тип (процедурный модуль) и исходный код.

```csharp
// Создать новый модуль
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New Source Code";

// Добавьте модуль в проект VBA
doc.VbaProject.Modules.Add(module);
```

## Шаг 4: Сохраните документ
Наконец, мы сохраним документ с проектом VBA, созданным в файле.

```csharp
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");
```

### Пример исходного кода для создания проекта Vba с использованием Aspose.Words для .NET 

```csharp

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
// Создайте новый модуль и укажите исходный код макроса.
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";
// Добавьте модуль в проект VBA.
doc.VbaProject.Modules.Add(module);
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");

```

## Заключение
В этом руководстве мы увидели, как создать проект VBA в документе Word, используя Aspose.Words для .NET. Создание проекта VBA позволяет добавлять и настраивать код VBA в документе Word. Не стесняйтесь использовать эту функцию для автоматизации задач или добавления пользовательских функций в документы Word.
