---
title: Доступ к исправленной версии
linktitle: Доступ к исправленной версии
second_title: Справочник по API Aspose.Words для .NET
description: Получите доступ к исправленной версии документа Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/access-revised-version/
---

В этом пошаговом руководстве мы покажем вам, как получить доступ к исправленной версии документа Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первым шагом является загрузка документа, содержащего исправления.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Шаг 2: Получите доступ к исправленной версии

Теперь мы перейдем к исправленной версии документа.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Шаг 3. Просмотрите версии

Далее мы пройдемся по ревизиям, присутствующим в документе, и отобразим конкретную информацию для абзацев, являющихся элементами списка.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Пример исходного кода для исправленной версии Access с использованием Aspose.Words для .NET

Вот полный исходный код для доступа к исправленной версии документа с помощью Aspose.Words для .NET:

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");
	doc.UpdateListLabels();

	// Перейти к исправленной версии документа.
	doc.RevisionsView = RevisionsView.Final;

	foreach (Revision revision in doc.Revisions)
	{
		 if (revision.ParentNode.NodeType == NodeType.Paragraph)
		 {
			 Paragraph paragraph = (Paragraph)revision.ParentNode;
			 if (paragraph.IsListItem)
			 {
				 Console.WriteLine(paragraph.ListLabel.LabelString);
				 Console.WriteLine(paragraph.ListFormat.ListLevel);
			 }
		 }
	}

```


