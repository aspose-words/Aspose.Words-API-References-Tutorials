---
title: Удалить оглавление в документе Word
linktitle: Удалить оглавление в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как удалить оглавление в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/remove-content/remove-table-of-contents/
---
В этом руководстве мы расскажем, как удалить оглавление в документе Word с помощью библиотеки Aspose.Words для .NET. Оглавление иногда может быть избыточным или ненужным, и этот код поможет вам эффективно удалить его. Мы предоставим пошаговое руководство, которое поможет вам понять и реализовать код в вашем собственном проекте .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте
- Документ Word, содержащий оглавление, которое вы хотите удалить

## Шаг 1: Определите каталог документов
 Во-первых, вам нужно указать путь к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Загрузите документ
 Далее мы загрузим документ Word в экземпляр`Document` класс, используя`Load` метод.

```csharp
// Загрузите документ
Document doc = new Document(dataDir + "your-document.docx");
```

## Шаг 3. Удалите оглавление
 Чтобы удалить оглавление, мы пройдемся по типу TOC (оглавление).`FieldStart` узлы в документе. Мы будем хранить эти узлы, чтобы мы могли быстро получить к ним доступ и создать список узлов для удаления.

```csharp
// Сохраняйте узлы FieldStart полей TOC в документе для быстрого доступа.
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
     // Безопаснее хранить эти узлы и удалять их все в конце.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Когда мы сталкиваемся с узлом FieldEnd типа FieldTOC,
     //мы знаем, что находимся в конце текущей TOC, и мы останавливаемся здесь.
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

//Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Загрузите документ
Document doc = new Document(dataDir + "your-document.docx");

// Сохраните узлы FieldStart полей TOC в документе для быстрого доступа.
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
	// Безопаснее хранить эти узлы и потом удалить их все сразу.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Как только мы встречаем узел FieldEnd типа FieldTOC,
	// мы знаем, что находимся в конце текущего оглавления и останавливаемся здесь.
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
В этом руководстве мы представили пошаговое руководство по удалению оглавления из документа Word с помощью библиотеки Aspose.Words для .NET. Следуя предоставленному коду и инструкциям, вы можете легко избавиться от оглавления и улучшить макет документа. Не забудьте изменить путь к каталогу и имена файлов в соответствии с вашими потребностями.

### Часто задаваемые вопросы

#### Q: Почему я должен использовать Aspose.Words для удаления оглавления в документе Word?

О: Aspose.Words — это мощная и универсальная библиотека классов для работы с документами Word в приложениях .NET. Используя Aspose.Words, вы можете эффективно удалить оглавление из ваших документов, что может быть полезно, если оглавление является избыточным или ненужным. Это позволяет настроить содержимое вашего документа и улучшить его общее представление.

#### В: Как загрузить документ в Aspose.Words для .NET?

A: Чтобы удалить оглавление в документе Word, вы должны сначала загрузить документ в память, используя метод Load() Aspose.Words. Вот пример кода для загрузки документа из определенного каталога:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "your-document.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к вашему документу.

#### В: Как удалить оглавление в документе с помощью Aspose.Words?

 A: Чтобы удалить оглавление, вам нужно пройти через`FieldStart` типы узлов оглавления в документе. Вы можете сохранить эти узлы для быстрого доступа и создать список узлов для удаления. Вот пример кода:

```csharp
// Сохраняйте узлы FieldStart полей TOC в документе для быстрого доступа.
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
// Безопаснее хранить эти узлы и удалять их все в конце.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Когда мы сталкиваемся с узлом FieldEnd типа FieldTOC,
//мы знаем, что находимся в конце текущей TOC, и мы останавливаемся здесь.
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

#### В: Как сохранить отредактированный документ в Aspose.Words для .NET?

О: После удаления оглавления необходимо сохранить измененный документ с помощью метода Сохранить(). Укажите желаемый путь к выходному файлу и формат (например, DOCX) для редактируемого документа. Вот пример кода:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```