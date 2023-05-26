---
title: Вставить вложенные поля
linktitle: Вставить вложенные поля
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как легко вставлять вложенные поля в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-nested-fields/
---

Вот пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция «Вставить вложенные поля» Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа и DocumentBuilder

Начнем с создания нового документа и инициализации DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставка разрывов страниц

Мы используем цикл для вставки нескольких разрывов страниц в документ.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## Шаг 4: Перейдите в нижний колонтитул

 Мы используем`MoveToHeaderFooter()` метод DocumentBuilder для перемещения курсора в основной нижний колонтитул.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Шаг 5: Вставка вложенного поля

 Мы используем DocumentBuilder`InsertField()` метод для вставки вложенного поля в нижний колонтитул.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Наконец, мы вызываем`Update()` способ обновления поля.

```csharp
field. Update();
```

### Пример исходного кода для вставки вложенных полей с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте разрывы страниц.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Перейти в нижний колонтитул.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Вставить вложенное поле.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Обновите поле.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

В этом примере мы создали новый документ, вставили разрывы страниц, переместили курсор в нижний колонтитул, а затем вставили вложенное поле в нижний колонтитул.