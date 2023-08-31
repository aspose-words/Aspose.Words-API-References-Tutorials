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

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и получите элемент управления содержимым флажка
 Загрузите документ Word, используя`Document` конструктор, передавая путь к документу в качестве параметра. Затем извлеките из документа нужный элемент управления содержимым флажка. В этом примере мы предполагаем, что флажок является первым тегом структурированного документа в документе.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Шаг 3. Установите или снимите флажок в зависимости от его текущего состояния
 Проверьте, имеет ли полученный тег структурированного документа тип`SdtType.Checkbox` . Если это так, установите`Checked` свойство элемента управления контентом`true` чтобы поставить галочку. В противном случае вы можете оставить его непроверенным.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Шаг 4. Сохраните документ
 Сохраните измененный документ в указанную директорию, используя команду`Save`метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithSdt.CurrentStateOfCheckBox.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Пример исходного кода для текущего состояния флажка с использованием Aspose.Words для .NET 

```csharp
	//Путь к каталогу ваших документов
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