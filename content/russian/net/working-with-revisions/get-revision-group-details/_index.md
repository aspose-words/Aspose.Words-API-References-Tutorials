---
title: Получить информацию о группе редакций
linktitle: Получить информацию о группе редакций
second_title: API обработки документов Aspose.Words
description: Получите сведения о группе редакций в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/get-revision-group-details/
---

В этом пошаговом руководстве мы покажем вам, как получить подробную информацию о группе редакций в документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первым шагом является загрузка документа, содержащего изменения.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Шаг 2. Просмотрите версии

Далее мы пройдемся по редакциям, присутствующим в документе, и отобразим их сведения, такие как тип, автор, дата и исправленный текст.

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


### Пример исходного кода для получения сведений о группе редакций с помощью Aspose.Words для .NET

Вот полный исходный код для получения подробной информации о группе редакций в документе с использованием Aspose.Words для .NET:

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

## Заключение

В этом уроке мы узнали, как получить подробную информацию о группе редакций в документе Word с помощью Aspose.Words для .NET. Используя цикл и соответствующие свойства, мы смогли отобразить такие детали, как тип редакции, автор, дата и исправленный текст. Aspose.Words for .NET предлагает множество мощных функций для управления документами Word, включая управление версиями. Теперь вы можете использовать эти знания для добавления сведений о группах редакций в свои собственные документы Word с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы

#### Вопрос: Как загрузить документ с исправлениями в Aspose.Words for .NET?

 А: Используйте`Document`класс Aspose.Words для .NET для загрузки документа из файла, содержащего версии. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Вопрос: Как получить сведения о группе редакций в Aspose.Words для .NET?

 О: Пройдитесь по редакциям документа с помощью цикла и получите доступ к свойствам каждой ревизии, чтобы получить нужную информацию. Вы можете использовать`RevisionType`, `Author`, `DateTime` и`ParentNode` свойства, чтобы получить тип редакции, автора, дату и исправленный текст соответственно.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### Вопрос: Как проверить, принадлежит ли ревизия группе в Aspose.Words for .NET?

 А: Используйте`Group` собственность`Revision` объект, чтобы проверить, принадлежит ли ревизия группе. Если`Group` собственность`null`это означает, что ревизия не принадлежит ни одной группе.

```csharp
if (revision.Group != null)
{
      // Редакция принадлежит группе
}
else
{
      // Редакция не принадлежит ни к одной группе.
}
```