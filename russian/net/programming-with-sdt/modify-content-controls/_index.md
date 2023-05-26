---
title: Изменить элементы управления содержимым
linktitle: Изменить элементы управления содержимым
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как изменить текст, раскрывающиеся списки и изображения в элементах управления содержимым в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/modify-content-controls/
---

В этом руководстве объясняется, как изменить различные типы элементов управления содержимым в документе Word с помощью Aspose.Words для .NET. Вы можете обновить текст, выбранное значение в раскрывающемся списке или заменить изображение в элементах управления содержимым.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и работы с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и повторите элементы управления содержимым
 Загрузите документ Word с помощью`Document`конструктор, передавая путь к документу в качестве параметра. Перебрать все теги структурированного документа в документе, используя`foreach` петля.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Выполнение действий в зависимости от типа управления содержимым
}
```

## Шаг 3: Изменить элемент управления содержимым обычного текста
 Для элементов управления содержимым типа`SdtType.PlainText`, удалите все существующие дочерние элементы, создайте новый абзац и добавьте нужный текст.

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

## Шаг 4: Изменить элемент управления содержимым раскрывающегося списка
 Для элементов управления содержимым типа`SdtType.DropDownList` , обновите выбранное значение, установив его на определенное`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Шаг 5: Изменить элемент управления содержимым изображения
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

## Шаг 6: Сохраните измененный документ
 Сохраните измененный документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithSdt.ModifyContentControls.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Пример исходного кода для изменения элементов управления содержимым с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
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

Вот и все! Вы успешно изменили различные типы элементов управления содержимым в документе Word с помощью Aspose.Words для .NET.