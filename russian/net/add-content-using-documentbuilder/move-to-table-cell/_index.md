---
title: Переместить в ячейку таблицы
linktitle: Переместить в ячейку таблицы
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по использованию функции «Переместить в ячейку таблицы» в Aspose.Words для .NET
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/move-to-table-cell/
---

В этом примере мы пошагово покажем вам, как использовать функцию «Переместить в ячейку таблицы» Aspose.Words для .NET, используя предоставленный исходный код C#. Эта функция позволяет вам перемещаться и управлять определенными ячейками внутри таблицы в документе Word. Выполните следующие шаги, чтобы интегрировать эту функцию в ваше приложение.

## Шаг 1: Загрузите документ, содержащий таблицу

Во-первых, нам нужно загрузить документ, содержащий таблицу, в которую мы хотим переместить ячейку. Используйте следующий код для выполнения этого шага:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Этот код загружает указанный документ (замените «MyDir +» Tables.docx"" с фактическим путем вашего документа, содержащего таблицу).

## Шаг 2. Переместите DocumentBuilder в определенную ячейку таблицы.

Далее мы переместим DocumentBuilder в определенную ячейку таблицы. Используйте следующий код для выполнения этого шага:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

 Этот код создает DocumentBuilder из существующего документа, а затем перемещает курсор из DocumentBuilder в указанную ячейку таблицы. Наконец, он добавляет содержимое в эту ячейку, используя DocumentBuilder.`Write()` метод.

## Шаг 3: Проверьте результат

Теперь вы можете убедиться, что перемещение в ячейку таблицы прошло успешно. Используйте следующий код для выполнения этого шага:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Этот код проверяет, что указанная ячейка действительно является текущей ячейкой DocumentBuilder. Он также проверяет, что содержимое, добавленное DocumentBuilder, было правильно сохранено в ячейке таблицы.

Вот и все ! Теперь вы поняли, как использовать функцию перемещения в ячейку таблицы Aspose.Words для .NET, используя предоставленный исходный код. Теперь вы можете интегрировать эту функцию в свое собственное приложение и управлять определенными ячейками таблицы в документах Word.


### Пример исходного кода для перемещения в ячейку таблицы с помощью Aspose.Words for .NET


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Переместите построитель в строку 3, ячейку 4 первой таблицы.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```
