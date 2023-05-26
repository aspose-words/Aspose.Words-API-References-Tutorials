---
title: Связь
linktitle: Связь
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять ссылки с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/link/
---

В этом примере мы покажем вам, как использовать функцию ссылок с Aspose.Words для .NET. Ссылки используются для создания интерактивных ссылок на веб-сайты или другие документы.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2: Вставка ссылки

 Мы можем вставить ссылку, используя`Insertlink` Метод генератора документов. Нам нужно указать текст ссылки, здесь «Aspose», а также целевой URL.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", ложь);
```

### Пример исходного кода для ссылок с Aspose.Words для .NET


```csharp
	// Используйте конструктор документов, чтобы добавить содержимое в документ.
	DocumentBuilder builder = new DocumentBuilder();

	// Вставьте ссылку.
	builder.Insertlink("Aspose", "https://www.aspose.com", ложь);
            
```
Поздравляем! Теперь вы узнали, как использовать функцию ссылок с Aspose.Words для .NET.

