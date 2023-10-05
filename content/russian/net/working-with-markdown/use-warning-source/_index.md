---
title: Использовать источник предупреждений
linktitle: Использовать источник предупреждений
second_title: API обработки документов Aspose.Words
description: Узнайте, как использовать источник предупреждений с Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/use-warning-source/
---

В этом примере мы покажем вам, как использовать источник предупреждений с Aspose.Words для .NET. Источник предупреждения указывает источник предупреждения при использовании функции обратного вызова.

## Шаг 1: Загрузка документа

 Мы загрузим существующий документ, содержащий предупреждения, используя`Load` метод`Document` сорт.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Шаг 3. Использование источника предупреждения

 Мы будем использовать источник предупреждения, установив для документа`WarningCallback` имущество в коллекцию`WarningInfo` объекты.

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

### Пример исходного кода для использования источника предупреждения с Aspose.Words для .NET

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

### Часто задаваемые вопросы

#### Вопрос: Можно ли настроить внешний вид тега «Внимание»?

 О: Форматирование тега «Предупреждение» зависит от используемого средства визуализации Markdown. В большинстве случаев вы можете настроить внешний вид, используя CSS для ориентации на`blockquote` тег в вашем документе.

#### Вопрос: Можно ли добавить значки в тег «Внимание»?

О: Да, к тегу «Предупреждение» можно добавить значки с помощью HTML-кода в вашем документе Markdown. Вы можете вставить`span` тег с соответствующим классом для отображения значка рядом с текстом предупреждения.

#### Вопрос: Совместим ли тег «Предупреждение» со всеми программами чтения Markdown?

 О: Совместимость тега «Предупреждение» зависит от используемого рендеринга Markdown. Большинство читателей Markdown поддержат`blockquote` тег для отображения выделенного текста, но точный внешний вид может отличаться.