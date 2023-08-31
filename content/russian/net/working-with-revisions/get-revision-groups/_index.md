---
title: Получить группы редакций
linktitle: Получить группы редакций
second_title: API обработки документов Aspose.Words
description: Получите группы редакций в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/get-revision-groups/
---

В этом пошаговом руководстве мы расскажем вам, как получить группы редакций в документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первым шагом является загрузка документа, содержащего изменения.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Шаг 2. Просмотрите группы редакций

Далее мы пройдемся по группам редакций, присутствующим в документе, и отобразим их данные, такие как автор, тип редакции и исправленный текст.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Пример исходного кода для получения групп редакций с помощью Aspose.Words для .NET

Вот полный исходный код для получения групп редакций в документе с помощью Aspose.Words для .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Заключение

В этом уроке мы узнали, как получить группы редакций в документе Word с помощью Aspose.Words для .NET. Мы выполнили шаги, чтобы загрузить документ и просмотреть группы рецензий, отображая такие детали, как автор и тип рецензии. Теперь вы можете применить эти знания для анализа версий вашего собственного документа Word с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы

#### Вопрос: Как загрузить документ в Aspose.Words для .NET?

 А: Используйте`Document` класс Aspose.Words для .NET для загрузки документа из файла. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Вопрос: Как просмотреть группы редакций в документе в Aspose.Words for .NET?

 А: Используйте`Groups` свойство документа`Revisions` объект, чтобы получить коллекцию групп редакций. Затем вы можете использовать цикл для обхода каждой группы отзывов.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Здесь обрабатывается каждая группа отзывов.
}
```

#### Вопрос: Как узнать автора группы обзора в Aspose.Words for .NET?

 А: Используйте`Author` собственность`RevisionGroup` объект, чтобы получить автора группы редакций.

```csharp
string author = group.Author;
```

#### Вопрос: Как получить тип ревизии группы ревизий в Aspose.Words для .NET?

 А: Используйте`RevisionType` собственность`RevisionGroup`объект, чтобы получить тип редакции группы.

```csharp
string revisionType = group.RevisionType;
```