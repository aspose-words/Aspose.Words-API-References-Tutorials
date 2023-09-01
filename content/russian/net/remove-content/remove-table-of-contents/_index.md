---
title: Удалить оглавление в документе Word
linktitle: Удалить оглавление в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как удалить оглавление в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/remove-content/remove-table-of-contents/
---
В этом уроке мы покажем вам, как удалить оглавление в документе Word с помощью библиотеки Aspose.Words для .NET. Оглавление иногда может быть избыточным или ненужным, и этот код поможет вам эффективно удалить его. Мы предоставим пошаговое руководство, которое поможет вам понять и реализовать код в вашем собственном .NET-проекте.

## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Практическое знание языка программирования C#.
- Библиотека Aspose.Words для .NET, установленная в вашем проекте.
- Документ Word, содержащий оглавление, которое вы хотите удалить.

## Шаг 1. Определите каталог документов.
 Во-первых, вам нужно установить путь к каталогу, соответствующий местоположению вашего документа Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ
 Далее мы загрузим документ Word в экземпляр`Document` класс, используя`Load` метод.

```csharp
// Загрузите документ
Document doc = new Document(dataDir + "your-document.docx");
```

## Шаг 3. Удалите оглавление
 Чтобы удалить оглавление, мы пройдемся по типу TOC (оглавление).`FieldStart` узлы в документе. Мы сохраним эти узлы, чтобы иметь возможность быстрого доступа к ним и создать список узлов для удаления.

```csharp
// Сохраните узлы FieldStart полей оглавления в документе для быстрого доступа.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Это список для хранения узлов, найденных внутри указанного TOC. Они будут удалены в конце этого метода.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Проверьте, существует ли указанный индекс TOC.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Безопаснее сохранить эти узлы и удалить их все в конце.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Когда мы встречаем узел FieldEnd типа FieldTOC,
     //мы знаем, что находимся в конце текущего содержания, и останавливаемся на этом.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Пример исходного кода для удаления оглавления с помощью Aspose.Words для .NET 
```csharp

// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Загрузите документ
Document doc = new Document(dataDir + "your-document.docx");

// Сохраните узлы FieldStart полей оглавления в документе для быстрого доступа.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Это список для хранения узлов, найденных внутри указанного TOC. Они будут удалены в конце этого метода.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Убедитесь, что оглавление, указанное переданным индексом, существует.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Безопаснее сохранить эти узлы и позже удалить их все сразу.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Как только мы встретим узел FieldEnd типа FieldTOC,
	// мы знаем, что находимся в конце текущего содержания и останавливаемся на этом.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Заключение
В этом уроке мы представили пошаговое руководство по удалению оглавления из документа Word с помощью библиотеки Aspose.Words для .NET. Следуя предоставленному коду и инструкциям, вы можете легко удалить оглавление и улучшить макет вашего документа. Не забудьте адаптировать путь к каталогу и имена файлов в соответствии с вашими конкретными потребностями.

### Часто задаваемые вопросы

#### Вопрос: Почему мне следует использовать Aspose.Words для удаления оглавления в документе Word?

О: Aspose.Words — это мощная и универсальная библиотека классов для управления документами Word в приложениях .NET. Используя Aspose.Words, вы можете эффективно удалить оглавление из ваших документов, что может быть полезно, если оглавление избыточно или ненужно. Это позволяет вам настроить содержимое вашего документа и улучшить его общее представление.

#### Вопрос: Как загрузить документ в Aspose.Words для .NET?

О: Чтобы удалить оглавление в документе Word, необходимо сначала загрузить документ в память с помощью метода Load() класса Aspose.Words. Вот пример кода для загрузки документа из определенного каталога:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "your-document.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к вашему документу.

#### Вопрос: Как удалить оглавление документа с помощью Aspose.Words?

 О: Чтобы удалить TOC, вам нужно перебрать`FieldStart` введите узлы оглавления в документе. Вы можете сохранить эти узлы для быстрого доступа и создать список узлов для удаления. Вот пример кода:

```csharp
// Сохраните узлы FieldStart полей оглавления в документе для быстрого доступа.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Это список для хранения узлов, найденных внутри указанного TOC. Они будут удалены в конце этого метода.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Проверьте, существует ли указанный индекс оглавления.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// Безопаснее сохранить эти узлы и удалить их все в конце.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Когда мы встречаем узел FieldEnd типа FieldTOC,
//мы знаем, что находимся в конце текущего содержания, и останавливаемся на этом.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### Вопрос: Как сохранить отредактированный документ в Aspose.Words for .NET?

О: После удаления оглавления необходимо сохранить измененный документ методом Save(). Укажите желаемый путь и формат выходного файла (например, DOCX) для редактируемого документа. Вот пример кода:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```