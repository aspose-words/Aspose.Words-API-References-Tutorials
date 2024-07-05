---
title: Экспорт в Markdown с выравниванием содержимого таблицы
linktitle: Экспорт в Markdown с выравниванием содержимого таблицы
second_title: API обработки документов Aspose.Words
description: Узнайте, как экспортировать содержимое таблицы с различным выравниванием в файлы Markdown с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Ниже приведено пошаговое руководство, объясняющее следующий исходный код C#, который помогает экспортировать содержимое в файл Markdown с выравниванием содержимого таблицы с использованием библиотеки Aspose.Words для .NET. Прежде чем использовать этот код, убедитесь, что вы включили библиотеку Aspose.Words в свой проект.

## Шаг 1. Установите путь к каталогу документов.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Обязательно укажите правильный путь к каталогу ваших документов, в котором будет сохранен отредактированный документ.

## Шаг 2. Создайте документ и генератор документов.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Здесь мы создаем экземпляр`Document` класс и экземпляр`DocumentBuilder` класс, который позволит нам манипулировать документом и добавлять элементы.

## Шаг 3. Вставьте ячейки в таблицу с разным выравниванием абзаца.

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Мы используем Document Builder, чтобы вставлять ячейки в таблицу и устанавливать различное выравнивание абзацев для каждой ячейки.

## Шаг 4. Установите параметры экспорта Markdown и сохраните измененный документ.

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

Мы устанавливаем параметры экспорта Markdown с различными выравниваниями содержимого таблицы, а затем сохраняем измененный документ, используя каждый вариант выравнивания.

### Пример исходного кода для экспорта в Markdown с выравниванием содержимого таблицы с использованием Aspose.Words для .NET

```csharp

            
	// Путь к каталогу документов.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Выравнивает все абзацы внутри таблицы.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// Выравнивание в этом случае будет взято из первого абзаца в соответствующем столбце таблицы.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Сохраните измененный документ
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
