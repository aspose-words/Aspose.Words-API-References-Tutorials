---
title: Получить сведения о группе изменений
linktitle: Получить сведения о группе изменений
second_title: Справочник по API Aspose.Words для .NET
description: Получите сведения о группе ревизий в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/get-revision-group-details/
---

В этом пошаговом руководстве мы покажем вам, как получить сведения о группе редакций в документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первым шагом является загрузка документа, содержащего исправления.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Шаг 2. Просмотрите версии

Затем мы пройдемся по ревизиям, присутствующим в документе, и отобразим их детали, такие как тип, автор, дата и исправленный текст.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Пример исходного кода для получения сведений о группе изменений с использованием Aspose.Words для .NET

Вот полный исходный код для получения сведений о группе редакций в документе с использованием Aspose.Words для .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

