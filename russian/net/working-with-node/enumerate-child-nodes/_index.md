---
title: Перечислить дочерние узлы
linktitle: Перечислить дочерние узлы
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как перечислить дочерние узлы в абзаце с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-node/enumerate-child-nodes/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором показано, как перечислять дочерние узлы с помощью Aspose.Words для .NET.

## Шаг 1. Импортируйте необходимые ссылки
Прежде чем начать, убедитесь, что вы импортировали в свой проект необходимые ссылки для использования Aspose.Words for .NET. Сюда входит импорт библиотеки Aspose.Words и добавление необходимых пространств имен в исходный файл.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.NodeTypes;
```

## Шаг 2: Создайте новый документ
 На этом шаге мы создадим новый документ, используя`Document` сорт.

```csharp
Document doc = new Document();
```

## Шаг 3: Доступ к абзацу и его дочерним узлам
 Чтобы перечислить дочерние узлы абзаца, нам сначала нужно получить доступ к самому абзацу. Использовать`GetChild` метод с`Paragraph` тип узла, чтобы получить первый абзац документа.

```csharp
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
```

Затем мы извлекаем коллекцию дочерних узлов абзаца, используя метод`ChildNodes` свойство.

```csharp
NodeCollection children = paragraph. ChildNodes;
```

## Шаг 4: Просмотрите дочерние узлы
 Теперь, когда у нас есть коллекция дочерних узлов, мы можем пройтись по ним, используя`foreach` петля. Мы проверяем тип каждого дочернего узла и выполняем определенные операции в зависимости от типа.

```csharp
foreach (Node child in children)
{
     // Абзац может содержать дочерние элементы различных типов, таких как прогоны, фигуры и другие.
     if (child. NodeType == NodeType.Run)
     {
         Run run = (Run)child;
         Console.WriteLine(run.Text);
     }
}
```

 В этом примере мы проверяем, относится ли дочерний узел к типу`Run` (например, фрагмент текста). Если это так, мы преобразуем узел в`Run` и отображать текст с помощью`run.Text`.

## Пример исходного кода для перечисления дочерних узлов с Aspose.Words для .NET


```csharp
Document doc = new Document();
Paragraph paragraph = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);

NodeCollection children = paragraph.ChildNodes;
foreach (Node child in children)
{
	// Абзац может содержать дочерние элементы различных типов, таких как прогоны, формы и другие.
	if (child.NodeType == NodeType.Run)
	{
		Run run = (Run) child;
		Console.WriteLine(run.Text);
	}
}
```

Это полный пример кода для перечисления дочерних узлов абзаца с помощью Aspose.Words для .NET. Обязательно импортируйте ссылки

