---
title: Текущее состояние флажка
linktitle: Текущее состояние флажка
second_title: API обработки документов Aspose.Words
description: Узнайте, как получить и установить текущее состояние элемента управления содержимым флажка в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/current-state-of-check-box/
---

В этом руководстве объясняется, как получить и установить текущее состояние элемента управления содержимым флажка в документе Word с помощью Aspose.Words для .NET. Вы можете установить или снять флажок в зависимости от его текущего состояния.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и Word Processing с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и извлеките элемент управления содержимым флажка.
 Загрузите документ Word с помощью`Document` конструктор, передавая путь к документу в качестве параметра. Затем извлеките нужный элемент управления содержимым флажка из документа. В этом примере мы предполагаем, что флажок является первым тегом структурированного документа в документе.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Шаг 3. Установите или снимите флажок в зависимости от его текущего состояния.
 Проверьте, относится ли извлеченный тег структурированного документа к типу`SdtType.Checkbox` . Если это так, установите`Checked` свойство элемента управления содержимым`true` чтобы установить флажок. В противном случае вы можете оставить его неотмеченным.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Шаг 4: Сохраните документ
 Сохраните измененный документ в указанную директорию с помощью`Save`метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithSdt.CurrentStateOfCheckBox.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Пример исходного кода для текущего состояния флажка с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Получите первый элемент управления содержимым из документа.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Вот и все! Вы успешно получили и установили текущее состояние элемента управления содержимым флажка в документе Word с помощью Aspose.Words для .NET.