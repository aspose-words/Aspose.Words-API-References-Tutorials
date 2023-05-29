---
title: Использовать источник предупреждений
linktitle: Использовать источник предупреждений
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как использовать источник предупреждений с Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/use-warning-source/
---

В этом примере мы покажем вам, как использовать источник предупреждений с Aspose.Words для .NET. Источник предупреждения указывает источник предупреждения при использовании функции обратного вызова.

## Шаг 1: Загрузка документа

 Мы загрузим существующий документ, содержащий предупреждения, используя метод`Load` метод`Document` сорт.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Шаг 3: Использование источника предупреждений

 Мы будем использовать источник предупреждения, установив документ`WarningCallback` собственность в коллекцию`WarningInfo` объекты.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Шаг 4: Сохранение документа

Наконец, мы можем сохранить документ в нужном формате.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Пример исходного кода для использования источника предупреждений с Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Поздравляем! Теперь вы узнали, как использовать источник предупреждений с Aspose.Words для .NET.