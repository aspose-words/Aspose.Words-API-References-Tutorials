---
title: Клонировать модуль Vba
linktitle: Клонировать модуль Vba
second_title: Справочник по API Aspose.Words для .NET
description: В этом руководстве вы узнаете, как клонировать модуль VBA из документа Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-vba-macros/clone-vba-module/
---

В этом уроке мы расскажем вам, как клонировать модуль VBA из документа Word с помощью макросов, используя библиотеку Aspose.Words для .NET. Клонирование модуля VBA позволяет повторно использовать или копировать код VBA из одного исходного документа в другой документ. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте
- Документ Word, содержащий проект VBA с модулем, который вы хотите клонировать.

## Шаг 1: Определите каталог документов
 Во-первых, вам нужно указать путь к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Загрузите исходный документ
Далее мы загрузим исходный документ Word, содержащий проект VBA и модуль, который мы хотим клонировать.

```csharp
// Загрузите исходный документ
Document doc = new Document(dataDir + "VBA project.docm");
```

## Шаг 3: Создайте новый документ с проектом VBA и клонируйте модуль.
Мы создадим новый документ с пустым проектом VBA и клонируем указанный модуль из исходного документа.

```csharp
// Создайте новый документ с пустым проектом VBA
Document destDoc = new Document { VbaProject = new VbaProject() };

// Клонировать модуль
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## Шаг 4: Сохраните целевой документ
Наконец, мы сохраним конечный документ с клонированным модулем VBA в файл.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Пример исходного кода для модуля Clone Vba с использованием Aspose.Words для .NET 
```csharp

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Заключение
В этом руководстве мы увидели, как клонировать модуль VBA из документа Word с помощью макросов, используя Aspose.Words для .NET. Клонирование модулей VBA позволяет легко повторно использовать код VBA из одного исходного документа в другом документе. Не стесняйтесь использовать эту функцию для организации и управления вашими макросами в разных документах.
