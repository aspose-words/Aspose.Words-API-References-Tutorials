---
title: Удалить строку по закладке в документе Word
linktitle: Удалить строку по закладке в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как удалить строку таблицы на основе определенной закладки в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/delete-row-by-bookmark/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию «Удалить строку по закладке» в библиотеке Aspose.Words для .NET. Эта функция позволяет удалить строку таблицы на основе определенной закладки в документе Word.

## Предварительные условия

- Базовые знания языка C#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1. Получение закладки

 Мы используем`Bookmarks` свойство диапазона документа, чтобы получить конкретную закладку, которую мы хотим использовать для удаления строки таблицы:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Шаг 2. Удалите строку таблицы.

 Мы используем`GetAncestor` метод получения`Row` введите родительский элемент закладки. Далее мы используем`Remove` метод удаления строки таблицы:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Пример исходного кода для удаления строки по закладке с использованием Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий удаление строки таблицы на основе определенной закладки с помощью Aspose.Words для .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию «Удалить строку по закладке» Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы удалить строку таблицы на основе определенной закладки в документе.

### Часто задаваемые вопросы по удалению строки по закладке в документе Word

#### Вопрос: Могу ли я удалить несколько строк, используя одну и ту же закладку?

О: Да, вы можете удалить несколько строк, используя одну и ту же закладку. Однако вам необходимо обработать логику вашего кода, чтобы определить количество удаляемых строк и внести необходимые изменения в предоставленный фрагмент кода.

#### Вопрос: Что произойдет, если закладки не существует в документе?

О: Если указанная закладка не существует в документе, фрагмент кода вернет нулевое значение для объекта закладки. Поэтому вам необходимо обработать этот сценарий в своем коде, добавив соответствующие проверки перед попыткой удалить строку таблицы.

#### Вопрос: Можно ли использовать библиотеку Aspose.Words бесплатно?

 О: Библиотека Aspose.Words является коммерческой библиотекой, и вам может потребоваться действующая лицензия для ее использования в ваших проектах. Вы можете посетить[Ссылки на Aspose.Words для .NET API](https://reference.aspose.com/words/net/) чтобы узнать больше о вариантах лицензирования и ценах.

#### Вопрос: Могу ли я удалить строки из таблицы в определенном разделе документа Word?

О: Да, вы можете удалять строки из таблицы в определенном разделе документа Word. Вы можете изменить предоставленный фрагмент кода для ориентации на определенный раздел, используя соответствующий диапазон или закладку в этом разделе.