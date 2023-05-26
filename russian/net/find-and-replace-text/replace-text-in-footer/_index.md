---
title: Заменить текст в нижнем колонтитуле
linktitle: Заменить текст в нижнем колонтитуле
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как заменить текст в нижнем колонтитуле документов Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/find-and-replace-text/replace-text-in-footer/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию «Заменить текст в нижнем колонтитуле» в библиотеке Aspose.Words для .NET. Эта функция позволяет находить и заменять определенный текст в нижних колонтитулах документов Word.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1. Загрузите документ

Прежде чем мы начнем использовать замену текста в нижнем колонтитуле, нам нужно загрузить документ в Aspose.Words для .NET. Это можно сделать с помощью`Document` class и указав путь к файлу документа:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Footer.docx");
```

## Шаг 2: доступ к нижнему колонтитулу

 После загрузки документа нам нужно получить доступ к нижнему колонтитулу, чтобы выполнить замену текста. В нашем примере мы используем`HeadersFooters` свойства первого раздела документа, чтобы получить коллекцию верхних/нижних колонтитулов. Затем мы выбираем основной нижний колонтитул, используя`HeaderFooterType.FooterPrimary` индекс:

```csharp
HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];
```

## Шаг 3. Настройте параметры поиска и замены

 Теперь мы настроим параметры поиска и замены, используя`FindReplaceOptions` объект. В нашем примере мы установили`MatchCase` к`false` игнорировать регистр при поиске и`FindWholeWordsOnly` к`false` чтобы разрешить поиск и замену частей слов:

```csharp
FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };
```

## Шаг 4: Замените текст в нижнем колонтитуле

 Мы используем`Range.Replace` метод замены текста в нижнем колонтитуле. В нашем примере мы заменяем фразу «(C) 2006 Aspose Pty Ltd.» «Авторское право (C) 2020 от Aspose Pty Ltd.» :

```csharp
footer

.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
```

## Шаг 5: Сохраните отредактированный документ

 Наконец, мы сохраняем измененный документ в указанный каталог, используя`Save` метод:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
```

### Пример исходного кода для замены текста в нижнем колонтитуле с использованием Aspose.Words для .NET

Вот полный образец исходного кода, демонстрирующий использование замены текста нижнего колонтитула с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Footer.docx");

	HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
	HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

	FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };

	footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
            
        
```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию «Заменить текст в нижнем колонтитуле» Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы загрузить документ, получить доступ к нижнему колонтитулу, настроить параметры поиска и замены, выполнить замену текста и сохранить отредактированный документ.
