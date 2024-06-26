---
title: Связь
linktitle: Связь
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставлять ссылки с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/link/
---

В этом примере мы покажем вам, как использовать функцию ссылок в Aspose.Words для .NET. Ссылки используются для создания интерактивных ссылок на веб-сайты или другие документы.

## Шаг 1. Использование генератора документов

Сначала мы воспользуемся генератором документов, чтобы добавить контент в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Вставка ссылки

 Мы можем вставить ссылку, используя`InsertHyperlink` метод генератора документов. Нам нужно указать текст ссылки, здесь «Aspose», а также целевой URL.

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com", false);
```

### Пример исходного кода для ссылок с Aspose.Words для .NET


```csharp
// Используйте конструктор документов, чтобы добавить содержимое в документ.
DocumentBuilder builder = new DocumentBuilder();

// Вставьте ссылку.
builder.InsertHyperlink("Aspose", "https://www.aspose.com", false);
```
Поздравляем! Теперь вы узнали, как использовать функцию ссылок в Aspose.Words для .NET.


### Часто задаваемые вопросы

#### Вопрос: Как я могу создать ссылку на URL-адрес в Aspose.Words?

 О: Чтобы создать ссылку на URL-адрес в Aspose.Words, вы можете использовать команду`<a>` тег с`href` атрибут, содержащий URL-адрес. Например, вы можете использовать`<a href="https://www.aspose.com">Click Here</a>` для гиперссылки на URL-адрес «https://www.example.com» с отображаемым текстом «Нажмите здесь».

#### Вопрос: Можно ли сделать ссылку на внутреннюю закладку в Aspose.Words?

 О: Да, в Aspose.Words можно создать ссылку на внутреннюю закладку. Вы можете использовать`<a>` тег с`href` Атрибут содержит имя закладки, которому предшествует решетка (#). Например,`<a href="#bookmark1">Go to bookmark 1</a>` будет ссылаться на закладку с именем «bookmark1» в документе.

#### Вопрос: Как настроить отображение текста ссылки в Aspose.Words?

О: Чтобы настроить отображаемый текст ссылки в Aspose.Words, вы можете изменить содержимое между`<a>` теги. Например,`<a href="https://www.aspose.com">Click here</a>` отобразит текст «Нажмите здесь» в виде гиперссылки.

#### Вопрос: Могу ли я указать цель для ссылки в Aspose.Words?

 О: Да, вы можете указать цель для ссылки в Aspose.Words, используя`target` атрибут`<a>` ярлык. Например,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` откроет ссылку в новом окне или вкладке.