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

## Заключение

В этом руководстве мы узнали, как получить группы ревизий в документе Word с помощью Aspose.Words для .NET. Мы выполнили шаги, чтобы загрузить документ и просмотреть группы рецензирования, отображая такие сведения, как автор и тип рецензии. Теперь вы можете применить эти знания для анализа версий вашего собственного документа Word с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы

#### В: Как загрузить документ в Aspose.Words для .NET?

 О: Используйте`Document` класс Aspose.Words для .NET для загрузки документа из файла. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### В: Как просматривать группы ревизий в документе в Aspose.Words для .NET?

 О: Используйте`Groups` свойство документа`Revisions` объект, чтобы получить коллекцию групп ревизий. Затем вы можете использовать цикл для просмотра каждой группы обзора.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Обработка каждой группы обзора здесь
}
```

#### В: Как получить авторскую группу отзывов в Aspose.Words для .NET?

 О: Используйте`Author` собственность`RevisionGroup` объект, чтобы получить автора ревизионной группы.

```csharp
string author = group.Author;
```

#### В: Как получить тип ревизии группы ревизий в Aspose.Words для .NET?

 О: Используйте`RevisionType` собственность`RevisionGroup`объект, чтобы получить тип ревизии группы.

```csharp
string revisionType = group.RevisionType;
```