---
title: Список перезапусков в каждом разделе
linktitle: Список перезапусков в каждом разделе
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как сбросить нумерованный список для каждого раздела в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-list/restart-list-at-each-section/
---

В этом пошаговом руководстве мы покажем вам, как сбросить нумерованный список для каждого раздела в документе Word с помощью Aspose.Words для .NET. Мы объясним предоставленный исходный код C# и покажем, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы еще этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Создание документа и списка

Сначала создайте новый документ и добавьте нумерованный список по умолчанию:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Шаг 2: Добавление элементов в список

 Затем используйте`DocumentBuilder` для добавления элементов в список. Вы можете использовать цикл для добавления нескольких элементов в список:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

В этом примере мы вставляем разрыв раздела после 15-го элемента списка, чтобы проиллюстрировать изменение нумерации.

## Шаг 3: Сохраните измененный документ

Наконец, сохраните измененный документ:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Так ! Вы успешно сбросили нумерованный список для каждого раздела в документе Word, используя Aspose.Words для .NET.

### Пример исходного кода для сброса списка в каждом разделе

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими потребностями.
