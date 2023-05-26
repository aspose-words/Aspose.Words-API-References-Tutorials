---
title: Документ владельца
linktitle: Документ владельца
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как использовать документ владельца в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-node/owner-document/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором показано, как использовать проприетарные функции документа с Aspose.Words для .NET.

## Шаг 1. Импортируйте необходимые ссылки
Прежде чем начать, убедитесь, что вы импортировали в свой проект необходимые ссылки для использования Aspose.Words for .NET. Сюда входит импорт библиотеки Aspose.Words и добавление необходимых пространств имен в исходный файл.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## Шаг 2: Создайте новый документ
 На этом шаге мы создадим новый документ, используя`Document` сорт.

```csharp
Document doc = new Document();
```

## Шаг 3: Создайте узел с документом владельца
 Когда вы создаете новый узел любого типа, вы должны передать документ в конструктор. В этом примере мы создаем новый узел абзаца, используя документ`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## Шаг 4: Проверьте родительский узел и документ владельца
 Теперь, когда мы создали узел абзаца, мы можем проверить, есть ли у него родительский узел и является ли документ-владелец таким же, как`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## Шаг 5: Измените свойства узла с данными документа
Отношения между узлом и документом позволяют получать доступ и изменять свойства, которые относятся к данным документа, таким как стили или списки. В этом примере мы устанавливаем имя стиля абзаца как «Заголовок 1».

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## Шаг 6: Добавьте абзац в документ
Теперь мы можем добавить узел абзаца в основной раздел документа.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Шаг 7: Проверьте родительский узел после добавления
После добавления абзаца в документ мы снова проверяем, есть ли у него теперь родительский узел.

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### Пример исходного кода для документа владельца с Aspose.Words для .NET

```csharp
	Document doc = new Document();

	// Для создания нового узла любого типа требуется документ, переданный в конструктор.
	Paragraph para = new Paragraph(doc);

	// Новый узел абзаца еще не имеет родителя.
	Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

	// Но узел абзаца знает свой документ.
	Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

	// Тот факт, что узел всегда принадлежит документу, позволяет нам получать доступ и изменять
	// свойства, которые ссылаются на данные всего документа, такие как стили или списки.
	para.ParagraphFormat.StyleName = "Heading 1";

	// Теперь добавьте абзац к основному тексту первого раздела.
	doc.FirstSection.Body.AppendChild(para);

	//Узел абзаца теперь является дочерним элементом узла Body.
	Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
            
```



