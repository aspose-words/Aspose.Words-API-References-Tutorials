---
title: Изменить элементы управления содержимым
linktitle: Изменить элементы управления содержимым
second_title: API обработки документов Aspose.Words
description: Узнайте, как изменять текст, раскрывающиеся списки и изображения в элементах управления содержимым в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/modify-content-controls/
---

В этом руководстве объясняется, как изменить различные типы элементов управления содержимым в документе Word с помощью Aspose.Words для .NET. Вы можете обновить текст, выбранное значение раскрывающегося списка или заменить изображение в элементах управления содержимым.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и перебирайте элементы управления содержимым
 Загрузите документ Word, используя`Document`конструктор, передавая путь к документу в качестве параметра. Перебрать все теги структурированного документа в документе, используя`foreach` петля.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Выполнять действия в зависимости от типа контроля контента
}
```

## Шаг 3. Измените элемент управления содержимым в виде простого текста
 Для элементов управления содержимым типа`SdtType.PlainText`, удалите все существующие дочерние элементы, создайте новый абзац и добавьте фрагмент с нужным текстом.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Шаг 4. Измените элемент управления содержимым раскрывающегося списка
 Для элементов управления содержимым типа`SdtType.DropDownList` , обновите выбранное значение, установив для него определенное значение`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Шаг 5. Измените элемент управления содержимым изображения
 Для элементов управления содержимым типа`SdtType.Picture`, извлеките фигуру из элемента управления содержимым и замените ее изображение новым.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Шаг 6. Сохраните измененный документ
 Сохраните измененный документ в указанную директорию, используя команду`Save` метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithSdt.ModifyContentControls.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Пример исходного кода для изменения элементов управления содержимым с помощью Aspose.Words для .NET 

```csharp
	//Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

Вот и все! Вы успешно изменили различные типы элементов управления содержимым в своем документе Word с помощью Aspose.Words для .NET.