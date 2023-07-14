---
title: Доступ к исправленной версии
linktitle: Доступ к исправленной версии
second_title: API обработки документов Aspose.Words
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

## Заключение

В этом руководстве мы узнали, как получить доступ к исправленной версии документа Word с помощью Aspose.Words для .NET. Загрузив документ, перейдя к исправленной версии и просматривая исправления, мы смогли получить конкретную информацию для абзацев, являющихся элементами списка. Aspose.Words для .NET предлагает мощные функции для работы с документами Word, включая доступ к рецензиям. Теперь вы можете использовать эти знания для доступа к исправленной версии ваших собственных документов Word с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы

#### В: Как загрузить документ с исправлениями в Aspose.Words для .NET?

 О: Используйте`Document`класс Aspose.Words для .NET для загрузки документа из файла, содержащего редакции. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### В: Как получить доступ к исправленной версии документа в Aspose.Words для .NET?

 О: Используйте`RevisionsView`собственность`Document` объект для доступа к исправленной версии документа. Вы можете установить значение параметра`RevisionsView` собственность на`RevisionsView.Final` чтобы показать окончательный вариант без правок.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### В: Как просмотреть версии документов в Aspose.Words для .NET?

 О: Используйте`foreach` цикл для перебора ревизий, присутствующих в документе. Вы можете использовать`Revisions`собственность`Document` объект, чтобы получить коллекцию всех ревизий документа.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Здесь обрабатывается каждая ревизия
}
```

#### В: Как проверить, является ли абзац элементом списка в Aspose.Words для .NET?

 О: Используйте`IsListItem`собственность`Paragraph` объект, чтобы проверить, является ли абзац элементом списка.`IsListItem` недвижимость возвращается`true` если абзац является элементом списка, в противном случае возвращается`false`.

```csharp
if (paragraph.IsListItem)
{
     // Абзац является элементом списка
}
else
{
     // Абзац не является элементом списка
}
```