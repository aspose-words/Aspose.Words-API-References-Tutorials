---
title: Получить сведения о группе изменений
linktitle: Получить сведения о группе изменений
second_title: API обработки документов Aspose.Words
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

## Заключение

В этом руководстве мы узнали, как получить сведения о группе редакций в документе Word с помощью Aspose.Words для .NET. Используя цикл и соответствующие свойства, мы смогли отобразить такие детали, как тип редакции, автора, дату и исправленный текст. Aspose.Words для .NET предлагает множество мощных функций для работы с документами Word, включая управление версиями. Теперь вы можете использовать эти знания для добавления сведений о группе ревизий в свои собственные документы Word с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы

#### В: Как загрузить документ с исправлениями в Aspose.Words для .NET?

 О: Используйте`Document`класс Aspose.Words для .NET для загрузки документа из файла, содержащего редакции. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Вопрос. Как получить сведения о группе ревизий в Aspose.Words для .NET?

 A: Просмотрите ревизии документа, используя цикл, и получите доступ к свойствам каждой ревизии, чтобы получить нужные сведения. Вы можете использовать`RevisionType`, `Author`, `DateTime` и`ParentNode` свойства, чтобы получить тип редакции, автора, дату и исправленный текст соответственно.

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

#### В: Как проверить, принадлежит ли ревизия группе в Aspose.Words для .NET?

 О: Используйте`Group` собственность`Revision` объект, чтобы проверить, принадлежит ли ревизия к группе. Если`Group` собственность`null`это означает, что ревизия не принадлежит ни к одной группе.

```csharp
if (revision.Group != null)
{
      // Ревизия принадлежит группе
}
else
{
      // Ревизия не принадлежит ни к одной группе
}
```