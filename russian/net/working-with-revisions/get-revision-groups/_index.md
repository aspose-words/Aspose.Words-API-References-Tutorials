---
title: Получить группы изменений
linktitle: Получить группы изменений
second_title: Справочник по API Aspose.Words для .NET
description: Получите группы ревизий в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/get-revision-groups/
---

В этом пошаговом руководстве мы расскажем вам, как получить группы ревизий в документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первым шагом является загрузка документа, содержащего исправления.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Шаг 2. Просмотр групп редакций

Далее мы пройдемся по группам редакций, присутствующим в документе, и отобразим их данные, такие как автор, тип редакции и исправленный текст.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Пример исходного кода для получения групп изменений с использованием Aspose.Words для .NET

Вот полный исходный код для получения групп ревизий в документе с использованием Aspose.Words для .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```


