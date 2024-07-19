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

Первым шагом является загрузка документа, содержащего изменения.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Шаг 2. Получите доступ к исправленной версии

Теперь мы перейдем к пересмотренной версии документа.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Шаг 3. Просмотрите версии

Далее мы пройдемся по редакциям, присутствующим в документе, и отобразим конкретную информацию для абзацев, которые являются элементами списка.

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

// Перейдите к исправленной версии документа.
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

В этом уроке мы узнали, как получить доступ к исправленной версии документа Word с помощью Aspose.Words для .NET. Загрузив документ, перейдя к исправленной версии и просмотрев редакции, мы смогли получить конкретную информацию для абзацев, которые являются элементами списка. Aspose.Words for .NET предлагает мощные функции для работы с документами Word, включая доступ к рецензиям. Теперь вы можете использовать эти знания для доступа к исправленной версии ваших собственных документов Word с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы

#### Вопрос: Как загрузить документ с исправлениями в Aspose.Words for .NET?

 А: Используйте`Document` класс Aspose.Words для .NET для загрузки документа из файла, содержащего версии. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Вопрос: Как мне получить доступ к исправленной версии документа в Aspose.Words для .NET?

 А: Используйте`RevisionsView` собственность`Document` возражать против доступа к исправленной версии документа. Вы можете установить значение параметра`RevisionsView`собственность`RevisionsView.Final` чтобы показать окончательную версию без доработок.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### Вопрос: Как просмотреть версии документов в Aspose.Words for .NET?

А: Используйте`foreach` цикл для перебора редакций, присутствующих в документе. Вы можете использовать`Revisions` собственность`Document` объект, чтобы получить коллекцию всех редакций документа.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Обрабатывайте каждую редакцию здесь
}
```

#### Вопрос: Как проверить, является ли абзац элементом списка в Aspose.Words for .NET?

 А: Используйте`IsListItem` собственность`Paragraph` объект, чтобы проверить, является ли абзац элементом списка.`IsListItem` возврат собственности`true` если абзац является элементом списка, в противном случае возвращается`false`.

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