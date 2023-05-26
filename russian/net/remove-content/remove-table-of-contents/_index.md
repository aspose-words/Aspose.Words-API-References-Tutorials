---
title: Удалить оглавление
linktitle: Удалить оглавление
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как удалить оглавление из документа Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/remove-content/remove-table-of-contents/
---

В этом руководстве мы расскажем, как удалить оглавление из документа Word с помощью библиотеки Aspose.Words для .NET. Оглавление иногда может быть избыточным или ненужным, и этот код поможет вам эффективно удалить его. Мы предоставим пошаговое руководство, которое поможет вам понять и реализовать код в вашем собственном проекте .NET.

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
//Загрузите документ
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
     // мы знаем, что находимся в конце текущей TOC, и мы останавливаемся здесь.
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

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
//Загрузите документ
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