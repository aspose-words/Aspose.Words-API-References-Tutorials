---
title: Автоссылка
linktitle: Автоссылка
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить автоссылку с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/autolink/
---

В этом примере мы объясним, как использовать функцию «Автоссылка» с Aspose.Words для .NET. Эта функция позволяет автоматически вставлять гиперссылки в документ.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Вставка гиперссылки

 Мы можем вставить гиперссылку, используя`InsertHyperlink` Метод генератора документов. Мы указываем URL-адрес и текст, который будет отображаться для ссылки.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
```

## Шаг 3. Вставка адреса электронной почты в качестве ссылки

Мы также можем вставить адрес электронной почты в качестве ссылки, используя префикс «mailto:». Это позволит пользователям щелкнуть ссылку, чтобы открыть почтовый клиент по умолчанию.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Шаг 4: Сохранение документа

Наконец, мы можем сохранить документ в нужном формате.

### Пример исходного кода для Autolink с использованием Aspose.Words для .NET


```csharp
	// Используйте конструктор документов, чтобы добавить содержимое в документ.
	DocumentBuilder builder = new DocumentBuilder();

	//Вставить гиперссылку.
	builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
	builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
            
```


Поздравляем! Теперь вы узнали, как использовать функцию «Автоссылка» с Aspose.Words для .NET.

